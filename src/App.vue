<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Curriculum Vitae</router-link> 
    </div>
    <router-view />
  </div>
</template>

<style>
      #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
      }
      #nav {
        background-color: #c7957e !important;
        /* opacity: 0.5; */
        height: 65px;
        display: flex;

      }
      a{
      color: white !important;
      float: left;
      margin-top: 10px;
      font-size: 30px;
      margin-left: 15px;

      }

      label {
        color: rgb(250, 243, 243);
        font-size: 20px;
        font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
      }

      .form-control {
          display: block;
          width: 100%;
          height: calc(2.5em + 0.75rem + 2px) !important;
          padding: 0.375rem 0.75rem;
      }
      .home {
        background-image: url('https://www.radiorafaela.com.ar/wp-content/uploads/2020/09/ciencia.jpg');
        background-size: cover;
      }

      .btn.btn-danger{
        background-color: #b17e67;
        border-color: #c7957e;
        margin-bottom: 20px;
        padding: 20px;
      }
      .btn.btn-danger:hover {
        color: white;
        background-color: #c7957e;
          border-color: #c7957e;

      }
      h1 {
        color: #d40606;
      }

</style>
