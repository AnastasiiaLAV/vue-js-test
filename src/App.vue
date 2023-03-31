<template>
  <div>
    <ContainerVue>
      <ApartmentFilterFormVue 
        @submit="searchApartments"
      />
    </ContainerVue>
    <ApartmentsList :items="apartments">
      <template v-slot:apartment="{apartment}">
          <ApartmentItem
            :key="apartment.id"
            :description="apartment.descr"
            :rating="apartment.rating"
            :price="apartment.price"
            :imgUrl="apartment.imgUrl"
        />
      </template>
    </ApartmentsList>
    </div>
</template>

<script>
import ApartmentsList from './components/Apartment/ApartmentsList.vue' ;
import apartments from './components/Apartment/apartments';
import ApartmentItem from './components/Apartment/ApartmentItem.vue';
import ApartmentFilterFormVue from './components/Apartment/ApartmentFilterForm.vue';
import ContainerVue from './components/IndividualComponents/Container.vue'


export default {
  name: 'App',
  components: {
      ApartmentsList,
      ApartmentItem,
      ApartmentFilterFormVue,
      ContainerVue,
      },
    data(){
      return{
        apartments,
      }
    },
    methods: {
        searchApartments(value){
            console.log('AppFormValue', value)
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
