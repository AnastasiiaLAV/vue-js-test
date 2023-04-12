<template lang="">
    <form class="form" @submit.prevent="handleSubmit">
        <Selector 
            v-model="city"
            :items="cities"
            class="form__select"
        />
        <InputVue 
            v-model="price"
            placeholder='Price, from'
        />
        <ButtonVue 
            type="submit" 
            class="form__submit">
            Apartment search
        </ButtonVue>
    </form>
</template>

<script>
import Selector from '../IndividualComponents/Selector';
import InputVue from '../IndividualComponents/InputVue.vue';
import ButtonVue from '../IndividualComponents/ButtonVue.vue';

export default {
    name: 'ApartmentFilterForm',
    components:{
        Selector,
        InputVue,
        ButtonVue,
    },
    data(){
        return{
            city:'',
            price:'',
        }
    },
    computed:{
        cities(){
            return [
        {value:'', label:"City", selected:true},
        'Kyiv',
        'Odesa',
        'Poltava',
        'Kharkiv',
        'Dnipro',
        'Lviv',
        'Kherson',
        'Mariupol',]
        },
        
    },
    methods:{
        handleSubmit(){
            this.$emit('submit', 
            {
                city: this.city,
                price: this.price,
            },
            )
        }
    }
}
</script>
<style lang="scss" scoped>
    .form {
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        justify-content: space-evenly;
        &__select {
            margin-right: 30px;
        }
        &__submit {
            margin-left: auto;
        }
    }
</style>