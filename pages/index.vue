<template>
  <ul>
    <li v-for="content in contents" :key="content.id">
      <nuxt-link :to="`/${content.id}`">{{ content.title }}</nuxt-link>
    </li>
  </ul>
</template>
<script>
import axios from "axios";
export default {
  async asyncData() {
    const { data } = await axios.get(
      // your-service-id部分は⾃分のサービスidに置き換えてください
      "https://youland_n.microcms.io/api/v1/blog",
      {
        // your-api-key部分は⾃分のapi-keyに置き換えてください
        headers: { "X-API-KEY": "ccd5db1e-2746-40a4-b11d-c42a246357e2" },
      }
    );
    return data;
  },
};
</script>
