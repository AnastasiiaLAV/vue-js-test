<template lang="">
    <ContainerVue>
        <div class="apartments-list">
        <h1>Details about the selection</h1>
        <ApartmentItem
            v-for="{id, descr, rating, price, imgUrl} in items" 
            :key="id"
            :description="descr"
            :rating="rating"
            :price="price"
            :imgUrl="imgUrl"
        />
    </div>
    </ContainerVue>
    
</template>
<script>
import ApartmentItem from '../Apartment/ApartmentItem.vue';
import ContainerVue from '../IndividualComponents/Container.vue';

export default {
    name: 'ApartmentsList',
    components:{
        ApartmentItem,
        ContainerVue
    },
    props:{
        items:{
            type: Array,
            default: () => [],
        }
    }
}
</script>
<style lang="scss" scoped>
    .apartments-list {
    /* display: flex;
    flex-wrap: wrap;
    margin-left: -15px;
    margin-right: -15px; */
    grid-gap: 20px;
    max-width: calc(100vw - 80px);
    grid-template-columns: 350px 350px 350px;
    justify-items: center;
    /* margin: 0 auto 30px; */
    padding: 0;
    list-style: none;
    display: grid;
    }
</style>