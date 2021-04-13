<template>
  <div class="container">
    <div class="cv">
      <div class="card">

        <h1 id="br">Information de contact </h1>
        <h2 class="title"> name : {{ name }}</h2>
        <h2 class="title">email : {{ email }}</h2>
        <h2 class="title">adress :{{ adress }}</h2>
        <h2 class="title">phone : {{ phone }}</h2>
        <h2 class="title">Github : {{ github }}</h2>

      </div>
      <div class="card">
        <h1 id="br">EXPERIENCE PROFESSIONNEL </h1>
        <div v-for="(experience, index) in experiences" :key="index">
          <div class="contents">
            <h4 class="title"> Company : {{ experience.COMPANY }}</h4>
            <h5 class="title">Post: {{ experience.POST }} <br>
              <span> from: {{ experience.FROM }} - To :{{ experience.TO }} </span>
            </h5>
            <!-- <p>POST_DESC :{{experience.POST_DESC }}</p> -->
          </div>
          <br />
        </div>
      </div>

      <div class="card">
        <h1 id="br">FORMATIONS</h1>
        <div v-for="(education, index) in educations" :key="index">
          <div class="contents">
            <h4 class="title">University :{{ education.UNIVERSITY }}</h4>
            <h5 class="title">Branch: {{ education.BRANCH }} <br>
              <span>from :{{  education.FROM }} - To:{{ education.TO }}</span>
            </h5>
          </div>
          <br />
        </div>
      </div>

      <div class="card">
        <h1>CENTRE D'INTÉRET</h1>
        <p class="aboutMe">{{ about }}</p>
        </div>
      <button class="btn btn-danger" @click.prevent="downloadPDF"> Imprimer PDF </button>
    </div>
  </div>

</template>
<script>
  import jsPDF from 'jspdf'
  export default {
    name: "About",
    data() {
      return {
        name: this.$store.state.name,
        email: this.$store.state.email,
        phone: this.$store.state.phone,
        adress: this.$store.state.adress,
        github: this.$store.state.github,

        experiences: this.$store.state.experinceList[0],
        educations: this.$store.state.educationList[0],
        about: this.$store.state.about,
      };
    },
    methods: {
      downloadPDF: function () {
        var pdf = new jsPDF();
        pdf.html(window.document.getElementsByClassName("cv")[0], {
          callback: function (pdf) {
            pdf.save();
          },
          x: 100,
          y: 100
        });
      }
    }
  }
</script>
<style>
  h1 {
    margin-top: 10px  !important;
    color: #d40606 !important;
  
  }

.title {
        margin-left: -20%;
    
  }

  .card {

    border: 0px solid #c7957e;
     margin-bottom: 20px; 
    background-color: #e6e3e1 !important;
    margin-top: 10px;
  }

  .btn {
    width: 100%;
  }

  .cv {
    background-color: rgb(224, 217, 217);
    border-radius: 10px;
  }
</style>