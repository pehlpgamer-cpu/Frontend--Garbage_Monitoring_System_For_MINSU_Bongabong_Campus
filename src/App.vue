<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios';


const trasbinsData = ref({});
const DisplayData = ref('');

async function GetAllTrashins() {
const options = {method: 'GET', url: 'https://localhost:7123/api/Trashbin/'};
try {
  const { data } = await axios.request(options);
  console.log(data);
  DisplayData.value = data[0].trashbinId;
  
  } catch (error) {
    console.error(error);
  }
}

onMounted(() => {
  console.log(`the component is now mounted.`)
  //might use this method...
})

</script>

<template>
  <h1>You did it!</h1>
  <p>
    Visit <a href="https://vuejs.org/" target="_blank" rel="noopener">vuejs.org</a> to read the
    documentation
  </p>
  <br><button @click="testFetch"> btn</button>
  <h1 v-if="data !== null">{{ DisplayData }}</h1>
</template>

<style scoped></style>
