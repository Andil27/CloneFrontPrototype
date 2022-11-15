<template>
  <div>
    <button @click="getPosts">Load Posts</button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "PagePost",
  data() {
    return {
      posts: [],
    };
  },
  methods: {
    getPosts() {
      console.log("inna as-sidq yahdi ila abirr");
      axios
        .get("https://jsonplaceholder.typicode.com/posts/1")
        .then((response) => {
          console.log(response.data);
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style></style>
