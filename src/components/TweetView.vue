<script setup lang="ts">
import { ref } from "vue";

const tweets = ref([
  { id: 0, description: 'Hellow, world!' },
  { id: 1, description: 'Hellow, hi!' },
  { id: 2, description: 'good, evening!' },
]);

const inputingDescription = ref<string>('');

const postTweet = () => {
  console.log(inputingDescription.value)
  const tweet = {
    id: Math.random(),
    description: inputingDescription.value,
  };
  tweets.value.push(tweet);
  inputingDescription.value = '';
}

const deleteTweet = (id: number) => {
  tweets.value = tweets.value.filter(v => v.id != id)
}

</script>
<template>
  <div class="container">
    <h1>Tweeter</h1>
    <div class="form-container">
      <input v-model="inputingDescription"/>
      <button class="save-button" @click="postTweet()">post</button>
    </div>
    <div class="tweet-container">
      <p v-if ="tweets.length <= 0">No tweets hav been added.</p>
      <ul v-else>
        <li v-for="tweet in tweets" :key="tweet.id" class="tweet-list">
          <span>{{ tweet.description }}</span>
          <button class="delete-button" @click="deleteTweet(tweet.id)">delete</button>
        </li>
      </ul>
    </div>
  </div>
  
</template>
<style scoped>
.container {
  display:flex;
  flex-direction: column;
  align-items: center;
}

.form-container {
  display:flex;
  flex-direction: column;
  align-items: center;
  background-color: aliceblue;
  padding: 24px 0;
  width: 60%;
  margin-bottom: 12px;
  border-radius: 4px;
  gap: 8px;
}
.save-button {
  color: #fff;
  font-weight: bold;
  background-color: #68c9c9;
  border-radius: 2px;
  border: none;
  width: 60px;
  height: 22px;
}
.delete-button {
  color: #fff;
  font-weight: bold;
  background-color: #d28383;
  border-radius: 2px;
  border: none;
  width: 60px;
  height: 22px;
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