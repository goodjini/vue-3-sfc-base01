<script setup lang="ts">
import { ref } from 'vue';

const inputingDescription = ref<string>('');

const postTweet = () => {

}
</script>
<template>
  <div class="form-container">
    <input v-model="inputingDescription"/>
    <button class="save-button" @click="postTweet()">post</button>
  </div>
</template>
<style scope>
.form-container {
  display:flex;
  flex-direction: column;
  align-items: center;
  background-color: rgb(128, 212, 138);
  padding: 24px 0;
  width: 60%;
  margin-bottom: 12px;
  border-radius: 4px;
  gap: 8px;
}
.save-button {
  color: #fff;
  font-weight: bold;
  background-color: #57ba69;
  border-radius: 2px;
  border: none;
  width: 60px;
  height: 22px;
}
.save-button:hover {
  background-color: #37bdbd;
}
</style>