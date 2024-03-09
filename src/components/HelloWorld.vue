<script setup>
import { ref } from 'vue'
import axios from 'axios'
defineProps({
  msg: String,
})

const count = ref(0)
const sendRequest = ()=>{
  axios.get('https://cdn.privacy-mgmt.com/wrapper/v2/meta-data?hasCsp=true&accountId=229&env=prod&metadata=%7B%22gdpr%22%3A%7B%7D%2C%22ccpa%22%3A%7B%7D%7D&propertyId=3632&ch=null&scriptVersion=4.18.0&scriptType=unified').then(res=>{
    console.log(res,1111)
  })
}
</script>

<template>
  <button @click="sendRequest">发送请求</button>

</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
