<template>
<div class ="form">
  <input type ="text" v-model="zipCode"  placeholder="000-0000"/>
  <button @click="searchAddress">住所自動入力</button>
  <p>Address：{{ addressData }}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
      return {
      zipCode: '',
      addressData: '',
      apiKey: "ACYBwUjgz3bMHqkWrG98tJf99O3RcEC0923UVU5"
    };
  },

  methods: {
    searchAddressInfo() {
      let url =
        "https://apis.postcode-jp.com/api/v3/postcodes/" +
        this.zipCode +
        "?apiKey=" +
        this.apiKey;
      axios.get(url).then((res) => {
        this.addressData = res.data.allAddress;
      });
    },
  },
};
</script>


