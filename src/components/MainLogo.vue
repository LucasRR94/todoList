<template>
  <div class="main-logo">
    <h1>{{titleLogo}}</h1>
  </div>
</template>

<script>
export default {
  name: 'MainLogo',
  props: ['titleLogo']

}
</script>

<style scoped>
  *{
    font-family: 'Roboto', sans-serif;
  }
  @media (min-width:1026px){
    .main-logo{
      background-color:rgb(58, 3, 146);
      width: 100%;
      height:7rem;
    }
    .main-logo h1{
      font-size: 4rem;
      text-align: center;
      margin-top:1rem;
      color:white;
    }
  }
  @media (max-width:1025px){
    .main-logo{
      background-color:rgb(58, 3, 146);
      width: 100%;
      height:6rem;
    }
    .main-logo h1{
      font-family: 'Roboto', sans-serif;
      font-size: 3rem;
      text-align: center;
      margin-top:1rem;
      color:white;
    }
  }
  @media (max-width:759px){
    .main-logo{
      background-color:rgb(58, 3, 146);
      width: 100%;
      height:4rem;
    }
    .main-logo h1{
      font-family: 'Roboto', sans-serif;
      font-size: 2rem;
      text-align: center;
      margin-top:0.8rem;
      color:white;
    }
  }
  @media (max-width:492px){
    .main-logo{
      background-color:rgb(58, 3, 146);
      width: 100%;
      height:3.3rem;
    }
    .main-logo h1{
      font-family: 'Roboto', sans-serif;
      font-size: 1.5rem;
      text-align: center;
      margin-top:0.8rem;
      color:white;
    }
  }
  @media (max-width:302px){
    .main-logo{
      background-color:rgb(58, 3, 146);
      width: 100%;
      height:2rem;
    }
    .main-logo h1{
      font-family: 'Roboto', sans-serif;
      font-size: 1.1rem;
      text-align: center;
      margin-top:0.3rem;
      color:white;
    }
  }
</style>
