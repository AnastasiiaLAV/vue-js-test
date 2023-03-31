<template lang="">
    <div>
        <input 
            v-model="text"
            type="text"  
            v-on="listeners"
            v-bind="$attrs"
            class="custom-input"/>
    </div>
</template>

<script>
export default {
    name: "InputVue",
    data(){
        return{
            text: "",
        }
    },
    computed:{
        listeners(){
            return{
                ...this.$attrs,
                input: event => this.$emit('input', event.target.value)
            }
        }
    },
}
</script>
<style lang="scss" scoped>
@import '../../assets/scss/variables';
    .custom-input {
        height: 44px;
        max-width: 220px;
        width: 100%;
        border: 2px solid $main-color;
        font-size: 18px;
        outline: none;
        line-height: inherit;
        padding: 8px 15px;
        &::placeholder {
            color: inherit;
        }
        &--error {
            border-color: red;
        }
        &__error {
            position: absolute;
            top: 100%;
            right: 0;
            width: 100%;
            font-size: 12px;
            color: red;
            line-height: 1.3;
        }
    }
</style>