<template>
  <div>
    <p v-for="menu in menufactuer" : key="menu.id">
      {{ menu.id }} - {{ menu.Title }}
    </p>
    <input placeholder="id" v-model="id" />
    <input placeholder="Title" v-model="Title" />
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      text: "test",
      menufactuer: [{ id: 1, Title: "test1" }],
    };
  },
  created() {
    this.get();
  },
  methods: {
    get() {
      axios.get("https://localhost:7148/api/menufacturers").then((Response) => {
        this.menufacturer = respone.data;
      });
    },
  },
};
</script>>