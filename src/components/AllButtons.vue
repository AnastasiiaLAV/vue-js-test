<template lang="">
    <div>
        <button 
        @click='$listener'
        :type='type'
        class="btn">
            <slot></slot>
        </button>
    </div>
</template>
<script>
export default {
    name: 'AllButton',
    props:{
        type: {
            type: String,
            default: 'button',
        }
    }
}
</script>
<style lang="scss" scoped>
    .btn{
        display: inline-block;
        min-width: 349px;
        height: 48.56px;
        border: 1px solid transparent;

        background: #FF662D;

        color: #fff;
        font-family: 'Montserrat Medium';
        font-size: 18px;
        line-height: 21px;
        align-items: center;
        text-align: center;

        cursor: pointer;

        padding: 8px 15px;
    }
</style>