<template id="registerTemplate">
    <form ref='form' action="" class='register-form'>
          <h2>Register</h2>
          <div class="form-group" >
               <label for="firstname">First Name</label>
               <input required type="text" id='firstname' placeholder="Enter First Name">
          </div>
          <div class="form-group">
               <label for="lastname">Last Name</label>
               <input required type="text" id='lastname' placeholder="Enter Last Name">
          </div>
          <div class="form-group">
               <label for="email">Email Address </label>
               <input required type="email" id='email' placeholder="Enter Email Address">
          </div>
          <div class="form-group">
               <label for="password">password</label>
               <input required type="password" placeholder="Enter Password" id='password'>
          </div>
          <div class="form-group">
               <label for="passwordcheck">Repeat Password</label>
               <input required type="password" placeholder="Repeat password" id='passwordcheck'>
          </div>
          <input type="submit" value='Register'>
    </form>
</template>

  