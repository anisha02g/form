<template>

<form id="signup-form" v-on:submit.prevent="submit">
    <mdb-card-title class="mt-4 h2"><center>CONTACT US</center></mdb-card-title>

  
    <div class="row">
        <div class="col-12 form-group">
            <label class="col-form-label col-form-label-lg">Full Name <span class="text-danger"></span></label>
            <input type="text" v-model.trim="$v.fullname.$model"  :class="{'is-invalid': validationStatus($v.fullname)}" placeholder="Your name.." class="form-control form-control-lg">
            <div v-if="!$v.fullname.required" class="invalid-feedback">The full name field is required.</div>
        </div>

        <div class="col-12 form-group">
            <label class="col-form-label col-form-label-lg">Email <span class="text-danger"></span></label>
            <input type="email" v-model.trim="email" :class="{'is-invalid': validationStatus($v.email)}" placeholder="email.." class="form-control form-control-lg">
            <div v-if="!$v.email.required" class="invalid-feedback">The email field is required.</div>
            <div v-if="!$v.email.email" class="invalid-feedback">The email is not valid.</div>
        </div>

       <!--<div class="col-12 form-group">
            <label class="col-form-label col-form-label-lg">Password <span class="text-danger"></span></label>
            <input type="password" v-model.trim="password"  :class="{'is-invalid': validationStatus($v.password)}" class="form-control form-control-lg">
            <div v-if="!$v.password.required" class="invalid-feedback">The password field is required.</div>
            <div v-if="!$v.password.minLength" class="invalid-feedback">You must have atleast {{ $v.password.$params.minLength.min}} letters.</div>
            <div v-if="!$v.password.maxLength" class="invalid-feedback">You must not have greater then {{$v.password.$params.maxLength.min}} letters.</div>
        </div>-->

        <div class="col-12 form-group">
            <label class="col-form-label col-form-label-lg">Phone Number <span class="text-danger"></span></label>
            <input type="number" v-model.trim="phonenumber"  :class="{'is-invalid ': validationStatus($v.phonenumber)}" placeholder="Number.." class="form-control form-control-lg">
            <div v-if="!$v.phonenumber.required" class="invalid-feedback">The phonenumber field is required.</div>
        </div>

        <div class="col-12 form-group-1">
            <label class="col-form-label col-form-label-lg">Message<span class="text-danger"></span></label>
            <input type="text" height="100%" width="280px" v-model.trim="message"   :class="{'is-invalid': validationStatus($v.message)}" placeholder="Write.." class="form-control form-control-lg">
            <div v-if="!$v.message.required" class="invalid-feedback">The message field is required.</div>
        </div>
        <div class="col-12 form-group text-center">
            <button class="btn btn-vue btn-lg col-4">Submit</button>
        </div>

    </div>
</form>




</template>

<script>
import { required, email, minLength, maxLength } from 'vuelidate/lib/validators'
    export default {
      name: 'Signupform' ,
      data: function() {
          return {
              fullname: '',
              email: '',
              password: '',
              phonenumber: '',
              message: '',
          }
      },
      validations: {
          fullname: {required},
          email: {required, email},
          password: {required, minLength: minLength(6), maxLength: maxLength(18)},
          phonenumber: {required},
          message: {required},
      },
      
      methods: {

          validationStatus: function(validation) {
              return typeof validation != "undefined" ? validation.$error : false;
          },

          submit: function() {
              this.$v.$touch();
              if (this.$v.$pendding || this.$v.$error) return;

              alert('data Submit');

          }
      }
    }
</script>

<style>
.btn-vue{
    background: #41ad20;
    color: #ffffff;
    font-weight: bold;
    flex: 3;
}
.row{
  border: 2px solid;
   width: 100%;
  height:50%;
  resize: both;
  overflow: auto;
  text-align: left;
}

.form-group-1{
    width: 100%;
  height:50%;

}


</style>
