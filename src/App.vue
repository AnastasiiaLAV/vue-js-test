<template>
  <div>
    <ContainerVue>
      <ApartmentFilterFormVue 
        @submit="filter"
      />
    </ContainerVue>
    <ApartmentsList :items="filtersApartments">
      <template v-slot:apartment="{apartment}">
          <ApartmentItem
            :key="apartment.id"
            :id="apartment.id"
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
        filters:{
          city:'',
          price:0,
        }
      }
    },

    computed:{
      filtersApartments(){
              console.log('APART-ARRAY-FILTER--', this.filtersByCityName(this.filtersByPrice(this.apartments)))
        
        return this.filtersByCityName(this.filtersByPrice(this.apartments))
      }
    },

    methods: {
      filter({city, price}){
            console.log('filter-city-', this.filters.city)
            console.log('filter-price-', this.filters.price)
        this.filters.city = city
        this.filters.price = price
      },
      filtersByCityName(){
                console.log('submit---', this.filters)

                console.log('this.filters.city===', this.filters.city)

        // if(!this.filters.city) return this.apartments;
    
                console.log('!!!!!submit-apart===', this.apartments)

        return this.apartments.filter(apartment=>{
                console.log('filtersByCityName()--', apartment.location.city)
          return apartment.location.city === this.filters.city;
        });
      },
      filtersByPrice(){
                console.log('submit-price--', this.filters)

                console.log('this.filters.price===', this.filters.city)
        // if(!this.filters.price) return this.apartments;

        return this.apartments.filter(apartment=>{
          console.log('filtersByPrice()---', apartment.price)
          return apartment.price >= this.filters.price;
        });
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
