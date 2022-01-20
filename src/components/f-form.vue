<template>
  <form @submit="handleLogin">
    <div class="form-control">
      <label for="username">Username</label>
      <input
        name="username"
        type="text"
        placeholder="Enter Username"
        v-model="username"
        @input="handleValidateUsername"
        @blur="handleValidateUsername"
      />
      <!-- <fText :inputName="'username'" :inputType="'text'" :place="'Enter Username'" :handleValidate="handleValidateUsername"/> -->
      <fError :errorString="errorUsername" />
    </div>
    <div class="form-control">
      <label for="username">Password</label>
      <input
        name="password"
        type="password"
        placeholder="Enter Password"
        v-model="password"
        @input="handleValidatePassword"
        @blur="handleValidatePassword"
      />
      <!-- <fText :inputName="'password'" :inputType="'password'" :place="'Enter Password'" :handleValidate="handleValidatePassword"/> -->
      <fError :errorString="errorPassword" />
    </div>
    <div class="form-control">
      <fButton/>
    </div>
    <div class="form-control">
      <fCheckbox/>
    </div>
  </form>
</template>

<script>
import fError from './f-error.vue';
import fCheckbox from './f-checkbox.vue';
import fButton from './f-button.vue';
// import fText from './f-text.vue';

export default {
  name: "LoginForm",
  components: {
    fError,
    fCheckbox,
    fButton,
    // fText
  },
  data() {
    return {
      username: '',
      password: '',
      errorUsername: [],
      errorPassword: [],
    }
  },
  methods: {
    handleValidateUsername() {
      //check empty username
      this.errorUsername = [];
      if (!this.username.trim()) {
        this.errorUsername.push("username is required");
      }
    },
    checkHasNumber(myPass) {
      return /\d/.test(myPass);
    },
    checkSpecialCharacter(myPass) {
      return /[ `!@#$%^&*()_+\-=[\]{};':"\\|,.<>/?~]/.test(myPass);
    },
    handleValidatePassword() {
      //check empty password
      this.errorPassword = [];
      if (!this.password.trim()) {
        this.errorPassword.push("password is required");
      }

      //check password more than 8 characters
      if (this.password.length && this.password.length < 8) {
        this.errorPassword.push("password must be at least 8 characters");
      }

      //check password included number
      if (!this.checkHasNumber(this.password)) {
        this.errorPassword.push("password must contain number");
      }

      //check password include spec characters
      if (!this.checkSpecialCharacter(this.password)) {
        this.errorPassword.push("password must contain special character");
      }
    },
    handleLogin(e) {
      e.preventDefault();
      this.handleValidateUsername();
      this.handleValidatePassword();
      if (!this.errorUsername.length && !this.errorPassword.length) {
        alert('Login successully!');
        this.username = '';
        this.password = '';
      }
    }
  }
}
</script>

<style scoped>
form {
  width: 96%;
}
.form-control {
  margin-top: 10px;
  display: flex;
  flex-direction: column;
}
.form-control:last-child {
  flex-direction: row;
}

label {
  font-weight: bold;
  margin-bottom: 10px;
}
input {
  padding: 10px;
}


</style>