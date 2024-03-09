<script setup>
import { ref } from 'vue'
import axios from 'axios'
defineProps({
  msg: String,
})
const apiUrl = 'https://api.permutive.com/v2.0/watson';
const apiKey = '6c1a38c7-5ed9-4ac8-b4dc-ff261fe14746';
// 请求头配置
const headers = {
  'Content-Type': 'application/json',
};

// POST 请求数据
const postData = {
  classify:true,
  url: "https://www.marketwatch.com/tools/markets/rates"
};
const count = ref(0)
const sendGetRequest = ()=>{
  axios.get('https://cdn.privacy-mgmt.com/wrapper/v2/meta-data?hasCsp=true&accountId=229&env=prod&metadata=%7B%22gdpr%22%3A%7B%7D%2C%22ccpa%22%3A%7B%7D%7D&propertyId=3632&ch=null&scriptVersion=4.18.0&scriptType=unified').then(res=>{
    console.log(res,1111)
  })
};
const sendPostRequest = ()=>{
// 发送 POST 请求
  axios.post(apiUrl + `?k=${apiKey}`, postData, { headers })
      .then(response => {
        console.log(response.data);
      })
      .catch(error => {
        console.error(error);
      });
}
</script>

<template>
  <button @click="sendGetRequest">发送请求1</button>
  <button @click="sendPostRequest">发送请求2</button>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
