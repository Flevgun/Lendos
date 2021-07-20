<template>
  <button class="btn" :type="btnType">{{btnText}}</button>
</template>

<script>
export default {
    name: 'Button',
    props: {
        btnType: {
            type: String,
            required: true
        },
        btnText: {
            type: String,
            required: true
        }
        
    },
    data() {
        return {}
    },
}
</script>
  
<style>
    .btn {
        border-radius: 4px;
        padding: 8px 16px;
        border-color: #007bff;
        cursor: pointer;
    }
</style>