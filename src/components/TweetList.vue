<script setup lang="ts">
import { ref } from "vue";
const tweets: any = [];
const deleteTweet = (id: any) => {

}
</script>

<template>
  <li v-for="tweet in tweets" :key="tweet.id" class="tweet-list">
    <span>{{ tweet.description }}</span>
    <button class="delete-button" @click="deleteTweet(tweet.id)">delete</button>
  </li>
</template>

<style scope>
.delete-button {
  color: #fff;
  font-weight: bold;
  background-color: #d28383;
  border-radius: 2px;
  border: none;
  width: 60px;
  height: 22px;
}
.delete-button:hover {
  background-color: #b65d5d;
}

.tweet-list {
  list-style: none;
  width: 250px;
  padding: 6px 8px;
  margin-bottom: 12px;
  border-radius: 4px;
  font-size: 12px;
  display: flex;
  justify-content: space-between;
  background-color: rgb(174, 208, 238);
}
</style>  
