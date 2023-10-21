<template>
    <div class="content-wrapper">
      <!-- <PageTitle msg="User List" /> -->
        <section class="content">
            <div class="container-fluid">
                <div class="row">
                    <div class="col-12">
                        <div class="card">
                        <div class="card-header">
                            <h3 class="card-title">User List</h3>
                            <div class="card-tools">
                            <div class="input-group input-group-sm" style="width: 150px;">
                                <input type="text" name="table_search" class="form-control float-right" placeholder="Search">

                                <div class="input-group-append">
                                <button type="submit" class="btn btn-default"><i class="fas fa-search"></i></button>
                                </div>
                            </div>
                            </div>
                        </div>
                        <!-- /.card-header -->
                        <div class="card-body table-responsive p-0">
                            <table class="table table-hover text-nowrap">
                            <thead>
                                <tr>
                                <th>ID</th>
                                <th>Name</th>
                                <th>Email</th>
                                <th>IsBan</th>
                                <th>Action</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr v-for="item in this.results.admins" :key="item">
                                <td>{{ item.id }}</td>
                                <td>{{ item.name }}</td>
                                <td>{{ item.email }}</td>
                                <td>{{ item.is_ban }}</td>
                                <td>
                                <router-link to="/user-edit"  class="nav-link">
                                    <span class="text-info">Edit</span>
                                </router-link>
                                <span class="text-danger">Delete</span>
                                </td>
                                </tr>
                            </tbody>
                            </table>
                        </div>
                        <!-- /.card-body -->
                        </div>
                        <!-- /.card -->
                    </div>
                </div>
            </div>
        </section>
    </div>
  </template>
<script>
//import PageTitle from '../components/PageTitle.vue';
import axios from 'axios';

export default {
    data() {
        return {
            results: {
                "success": true,
                "admins": [
                    {
                        "id": 1,
                        "name": "Admin",
                        "email": "admin@admin.com",
                        "email_verified_at": null,
                        "phone": "123456789",
                        "is_ban": 0,
                        "user_type": 1,
                        "created_at": "2023-10-20T16:18:45.000000Z",
                        "updated_at": "2023-10-20T16:18:45.000000Z"
                    },
                    {
                        "id": 4,
                        "name": "Admin",
                        "email": "admin@sagar.com",
                        "email_verified_at": null,
                        "phone": "9621024997",
                        "is_ban": 1,
                        "user_type": 1,
                        "created_at": "2023-10-20T16:30:02.000000Z",
                        "updated_at": "2023-10-20T16:30:02.000000Z"
                    }
                ]
            }
        }
    },
    // mounted() {
    //     axios.get('https://991e-203-115-91-36.ngrok-free.app/api/admin/all')
    //     .then((response) => {
    //         if(response.status === 200){
    //             console.log('find data');
    //             console.log(response);
    //             //this.results = response.data
    //         }
            
    //     })
    // }
}
</script>
  