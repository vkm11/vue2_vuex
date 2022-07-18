<template>
  <form @submit.prevent="onSubmit">
    <input type="text" v-model="title" placeholder="Add Product..." />
    <input type="text" v-model="price" placeholder="Add Price..." />
    <input type="submit" placeholder="Submit" />
  </form>
</template>

<script>
import { mapActions } from 'vuex'
export default {
    name:"Add-Product",
    data(){
        return{
            title:"",
            price:""
        }
    },
    methods:{
        ...mapActions(["addProduct"]),
        onSubmit(){
            this.addProduct({
                title: this.title,
                price: this.price

            })
        }
    }

}
</script>

<style>

</style>