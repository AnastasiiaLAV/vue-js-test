<template lang="">
    <ContainerVue>
        <!-- <ApartmentFilterForm @submit='searchApartments'/> -->
        <h1 class="apartments-title">Details about the selection</h1>
        <div class="apartments-list">
            <template v-for="apartment in items">
                <slot name="apartment" :apartment="apartment"></slot>
            </template>
        </div>
    </ContainerVue>
</template>

<script>
import ContainerVue from '../IndividualComponents/Container.vue';
// import ApartmentFilterForm from './ApartmentFilterForm.vue';

export default {
    name: 'ApartmentsList',
    components:{
        ContainerVue,
        // ApartmentFilterForm,
    },
    props:{
        items:{
            type: Array,
            default: () => [],
        }
    },
    methods: {
        searchApartments(value){
            return('value', value)
        }
    },
}
</script>
<style lang="scss" scoped>
    .apartments-title{
        font-weight: 700;
        font-size: 20px;
        line-height: 24px;
        display: flex;
        align-items: center;

        color: #000000;

        margin-top: 40px;
        margin-bottom: 20px;
    }
    
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