<template lang="">
    <button 
        :type='type'
        class="btn">
            <slot></slot>
    </button>
</template>
<script>

export default {
    name: 'ButtonVue',
    props:{
        type: {
            type: String,
            default: 'button',
        }
    }
}
</script>
<style lang="scss" scoped>
@import '../../assets/scss/variables.scss';
    .btn{
        display: inline-block;
        height: 44px;
        max-width: 220px;
        width: 100%;
        border: 1px solid transparent;

        background: $main-color;

        color: #fff;
        font-size: 18px;
        line-height: 0.8;
        align-items: center;
        text-align: center;

        cursor: pointer;

        padding: 8px 15px;
    }
</style>