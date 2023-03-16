<template>

    <ApartmentsList :items="apartments"/>

</template>

<script>
import ApartmentsList from './components/ApartmentsList/ApartmentsList.vue' ;
import apartments from './components/ApartmentsList/apartments';


export default {
  name: 'App',
  components: {
      ApartmentsList,
      },
    data(){
      return{
        apartments,
      }
      
    }
  }
</script>

<style>
#app {
  font-family: Montserrat, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #1a065d;
  margin-top: 60px;
}
</style>
