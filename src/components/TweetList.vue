<script setup lang="ts">
type Tweet = {
  id: number,
  description: string,
};
type Props = {
  tweetsProps: Tweet[],
}
defineProps<Props>()

const deleteTweet = (id: any) => {

}
</script>

<template>
  <li v-for="tweet in tweetsProps" :key="tweet.id" class="tweet-list">
    <span>{{ tweet.description }}</span>
    <button class="delete-button" @click="deleteTweet(tweet.id)">delete</button>
  </li>
</template>

<style scope>
.delete-button {
  color: #fcfbf9;
  font-weight: bold;
  background-color: #7ee592;
  border-radius: 2px;
  border: none;
  width: 60px;
  height: 22px;
}
.delete-button:hover {
  background-color: #6fa848;
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
  background-color: rgb(148, 150, 151);
}
</style>  
