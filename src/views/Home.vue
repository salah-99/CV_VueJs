<template>
  <div class="home">
    <div class="container">
      <div class="form-group">
        <label for="name">Name</label>
        <input type="text" class="form-control" id="name" aria-describedby="emailHelp" v-model="name" />
      </div>
  

      <div class="form-group">
        <label for="email">Email</label>
        <input type="email" class="form-control" id="email" v-model="email" />
      </div>
      <div class="form-group">
        <label for="phone">Phone</label>
        <input type="text" class="form-control" id="phone" v-model="phone" />
      </div>
      <div class="form-group">
        <label for="address">Address</label>
        <input type="text" class="form-control" id="address" v-model="adress" />
      </div>
      <div class="form-group">
        <label for="github">Github</label>
        <input type="text" class="form-control" id="github" v-model="github" />
      </div>

      <h1>EXPÉRIENCES PROFESSIONNELLE</h1>
      <div v-for="(experince, index) in experinceList" :key="index">
        <div class="form-group">
          <label for="COMPANY">COMPANY</label>
          <input type="text" class="form-control" id="COMPANY" v-model="experince.COMPANY" />
        </div>
        <div class="form-group">
          <label for="POST">POST</label>
          <input type="text" class="form-control" id="POST" v-model="experince.POST" />
        </div>
      
        <div class="row">
          <div class="col-md">
            <div class="form-group">
              <label for="FROM">FROM</label>
              <input type="number" class="form-control" id="FROM" v-model="experince.FROM" />
            </div>
          </div>
          <div class="col-md">
            <div class="form-group">
              <label for="TO">TO</label>
              <input type="number" class="form-control" id="TO" v-model="experince.TO" />
            </div>
          </div>
        </div>

        <div class="line"></div>
      </div>


      <h1>FORMATIONS</h1>
      <div v-for="(education, index) in educationList" :key="index">
        <div class="form-group">
          <label for="COMPANY">UNIVERSITY</label>
          <input type="text" class="form-control" id="COMPANY" v-model="education.UNIVERSITY" />
        </div>
        <div class="form-group">
          <label for="POST">Branch</label>
          <input type="text" class="form-control" id="POST" v-model="education.BRANCH" />
        </div>

        <div class="row">
          <div class="col-md">
            <div class="form-group">
              <label for="FROM">FROM</label>
              <input type="number" class="form-control" id="FROM" v-model="education.FROM" />
            </div>
          </div>
          <div class="col-md">
            <div class="form-group">
              <label for="TO">TO</label>
              <input type="number" class="form-control" id="TO" v-model="education.TO" />
            </div>
          </div>
        </div>

        <div class="line"></div>
      </div>




      <div class="form-group">
        <h1 for="about">CENTRE D’INTÉRET</h1>
        <textarea class="form-control" id="about" rows="3" v-model="about"></textarea>
      </div>

      <button class="btn btn-danger" @click.prevent="submitNameAndDesc">register </button>

    </div>
  </div>
</template>

<script>
  export default {
    name: "Home",
    data() {
      return {
        experinceList: [{
          COMPANY: "",
          POST: "",
          POST_DESC: "",
          FROM: "",
          TO: "",
        }, ],
        educationList: [{
          UNIVERSITY: "",
          BRANCH: "",
          FROM: "",
          TO: "",
        }, ],
        skills: [],
      };
    },
    computed: {
      name: {
        get() {
          return this.$store.state.name;
        },
        set(value) {
          this.$store.commit("setName", value);
        },
      },
      desc: {
        get() {
          return this.$store.state.desc;
        },
        set(value) {
          this.$store.commit("setDesc", value);
        },
      },
      email: {
        get() {
          return this.$store.state.email;
        },
        set(value) {
          this.$store.commit("setEmail", value);
        },
      },
      phone: {
        get() {
          return this.$store.state.phone;
        },
        set(value) {
          this.$store.commit("setPhone", value);
        },
      },
      adress: {
        get() {
          return this.$store.state.adress;
        },
        set(value) {
          this.$store.commit("setAdress", value);
        },
      },
      github: {
        get() {
          return this.$store.state.github;
        },
        set(value) {
          this.$store.commit("setGitHub", value);
        },
      },
      about: {
        get() {
          return this.$store.state.about;
        },
        set(value) {
          this.$store.commit("setAbout", value);
        },
      },
    },
    methods: {
      addExperience: function () {
        this.experinceList.push({
          COMPANY: "",
          POST: "",
          POST_DESC: "",
          FROM: "",
          TO: "",
        });
      },
      addEducation: function () {
        this.educationList.push({
          UNIVERSITY: "",
          BRANCH: "",
          FROM: "",
          TO: "",
        });
      },
      submitNameAndDesc: function () {
        this.$store.dispatch("setExperience", this.experinceList);
        this.$store.dispatch("setEducation", this.educationList);
        this.$router.push({
          path: "cv"
        });
      },
    },
  };
</script>
<style>
  .container {
    width: 50px;
  }
</style>