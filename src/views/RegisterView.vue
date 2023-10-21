<template>
  <div class="content-wrapper">
    <PageTitle msg="User Register" />
    <!-- Main content -->
    <section class="content">
      <div class="container-fluid">
        <div class="row">
          <div class="col-md-12">
            <!-- general form elements -->
            <div class="card card-primary">
              <div class="card-header">
                <h3 class="card-title">Quick Example</h3>
              </div>
              <!-- form start -->

              <form role="form" @submit.prevent="submitForm" novalidate>
                <div class="card-body">
                  <span class="text-green-600 text-success" v-if="success">{{ success }}</span>
                  <div class="form-group">
                    <label for="exampleInputName">User Name:</label>
                    <input type="text" class="form-control" name="name" v-model="form.name" placeholder="Enter user name">
                    <span class="text-red-600 text-danger" v-if="errors?.name">{{ errors.name[0] }}</span>
                  </div>
                  <div class="form-group">
                    <label for="exampleInputEmail1">Email ID:</label>
                    <input type="email" class="form-control" name="email" v-model="form.email" placeholder="Enter email">
                    <span class="text-danger" v-if="errors?.email">{{ errors.email[0] }}</span>
                  </div>
                  <div class="form-group">
                    <label for="exampleInputPhone">Phone:</label><br>
                    <span class="text-info" >This is optional field!</span>
                    <input type="text" class="form-control" name="phone" v-model="form.phone" placeholder="Enter phone number">
                    <span class="text-red-600 text-danger" v-if="errors?.phone">{{ errors.phone[0] }}</span>
                  </div>
                  <div class="form-group">
                    <label for="exampleInputPassword1">Password:</label>
                    <input type="password" class="form-control" name="password" v-model="form.password" placeholder="Password">
                    <span class="text-red-600 text-danger" v-if="errors?.password">{{ errors.password[0] }}</span>
                  </div>
                  <div class="form-check">
                    <input type="checkbox" class="form-check-input" name="is_ban" true-value="on" false-value="off" v-model="form.is_ban">
                    <label for="exampleInputBan" class="form-check-label">Do you want ban</label>
                  </div>
                </div>

                <div class="card-footer">
                  <button type="submit" class="btn btn-primary">Submit</button>
                </div>
              </form>
            </div>
            <!-- /.card -->

          </div>
        </div>
      </div>
    </section>
    <!-- /.content -->
  </div>
</template>
<script>
import PageTitle from '../components/PageTitle.vue';
import axios from 'axios';

    export default {
      data(){
          return{
              form: {
                  name: '',
                  email: '',
                  phone: '',
                  is_ban: '',
                  password: ''
              },
              errors: {
                    name: null,
                    email: null,
                    password: null
              },
              success: ''
          }
      },
      methods:{
          submitForm(){
              console.log(this.form);
              axios.post('https://3edc-203-115-91-36.ngrok-free.app/api/admin/create', this.form)
                  .then((res) => {
                    console.log('success');
                    console.log(res);
                    if (res.status === 201){
                      this.success = 'User saved successfully!';
                      //console.log(res);
                      //Perform Success Action
                    }
                  })
                  .catch((error) => {
                    console.log('error');
                    if (error.response.status === 422) {
                      this.errors.name = error.response.data.errors.name;
                      this.errors.email = error.response.data.errors.email;
                      this.errors.phone = error.response.data.errors.phone;
                      this.errors.password = error.response.data.errors.password;
                      console.log(error.response.data.errors.name);
                    }
                      // error.response.status Check status code
                  }).finally(() => {
                      //Perform action in always
                  });
          }
      }
    }
</script>
