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
                                <tr>
                                <td>183</td>
                                <td>John Doe</td>
                                <td>user@gmail.com</td>
                                <td>yes</td>
                                <td>
                                   <a href="#"><span class="text-info">Edit</span></a> 
                                   <a href="#"><span class="text-danger">Delete</span></a>
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
</script>
  