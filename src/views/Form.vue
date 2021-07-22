<template>
<div class ="form">
  <input type ="text" v-model="zipCode"  placeholder="000-0000"/>
  <button @click="searchAddress">住所自動入力</button>
  <input type ="text" v-model="address" />
  </div>
</template>

<script>
import axios from "axios";
export default {
  props:["zipcode"],
  data() {
    return {
      zipcode: '',
      address: '',
    };
  },
  methods: {
    async created() {
      const item = await axios.get(
        https://apis.postcode-jp.com/api/v4/postcodes/string?string
      )
      then.((response)=>{
        this.address =""})
      })
    }
  

</script>
<style scoped>
.form{
  width
}
