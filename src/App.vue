<template>
  <div>
  <h2>{{text}}</h2>
  <InputVue v-model="text"/>

    <ApartmentsList :items="apartments">
      <template v-slot:apartment="{apartment}">
          <ApartmentItem
            :key="apartment.id"
            :description="apartment.descr"
            :rating="apartment.rating"
            :price="apartment.price"
            :imgUrl="apartment.imgUrl"
            @click="handleItemClick"
        />
      </template>
    </ApartmentsList>
    </div>
</template>

<script>
import ApartmentsList from './components/ApartmentsList/ApartmentsList.vue' ;
import apartments from './components/ApartmentsList/apartments';
import ApartmentItem from './components/Apartment/ApartmentItem.vue';
import InputVue from './components/IndividualComponents/InputVue.vue';

export default {
  name: 'App',
  components: {
      ApartmentsList,
      ApartmentItem,
      InputVue,
      },
    data(){
      return{
        text: "",
        apartments,
      }
      
    },
    methods: {
        handleItemClick (){
          console.log('click')
        }
      },
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
