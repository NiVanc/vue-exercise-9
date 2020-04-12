<template>
  <div class="container">
    <form class="signup" v-if="!isSubmitted">
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <!-- Exercise 1 -->
          <!-- Create a Signup Form where you retrieve the following Information -->
          <!-- Full Name (First Name + Last Name) -->
          <!-- Mail -->
          <!-- Password -->
          <!-- Store Data? Yes/No -->
          <div class="panel panel-default">
            <div class="panel-heading">
              <h4>Signup</h4>
            </div>
            <div class="panel-body">
              <div class="form-group">
                <label for="email">First Name</label>
                <input type="text" id="firstname" class="form-control" v-model="userData.firstName" />
              </div>
              <div class="form-group">
                <label for="email">Last Name</label>
                <input type="text" id="lastname" class="form-control" v-model="userData.lastName" />
              </div>
              <div class="form-group">
                <label for="email">Email</label>
                <input type="text" id="email" class="form-control" v-model="userData.email" />
              </div>
              <div class="form-group">
                <label for="email">Password</label>
                <input type="text" id="password" class="form-control" v-model="userData.password" />
              </div>
              <div class="form-group">
                <label for="email">Store data?</label>
                <br />
                <label for="Yes">
                  <input type="radio" id="yes" value="true" v-model="userData.storeData" /> Yes
                </label>
                <label for="No">
                  <input type="radio" id="no" value="false" v-model="userData.storeData" /> No
                </label>
              </div>
              <div class="forrm-group">
                <button class="btn btn-primary" @click.prevent="submitted">Submit!</button>
              </div>
            </div>
          </div>

          <!-- Exercise 2 -->
          <!-- Only display the Form if it has NOT been submitted -->
          <!-- Display the Data Summary ONCE the Form HAS been submitted -->

          <!-- Exercise 3 -->
          <!-- Edit the Example from above and create a custom "Full Name" Control -->
          <!-- which still holds the First Name and Last Name Input Field -->
        </div>
      </div>
    </form>
    <div class="your-data" v-if="isSubmitted">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h4>Your Data</h4>
          </div>
          <div class="panel-body">
            <p>Full Name: {{ userData.firstName }} {{ userData.lastName }}</p>
            <p>Mail: {{ userData.email }}</p>
            <p>Password: {{ userData.password }}</p>
            <p>Store in Database?: {{ userData.storeData }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      userData: {
        firstName: "",
        lastName: "",
        email: "",
        password: "",
        storeData: true
      },
      isSubmitted: false
    };
  },
  methods: {
    submitted() {
      this.isSubmitted = true;
    }
  }
};
</script>

<style scoped>
form.signup,
.your-data {
  margin-top: 55px;
}
</style>
