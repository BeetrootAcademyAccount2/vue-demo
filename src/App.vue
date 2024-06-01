<!-- Html code -->
<template>
  <div>
    <h1>Vue Demo</h1>
    <CardList />
  </div>
</template>

<!-- JavaScript code -->
<script>
import CardList from "./components/CardList.vue";

export default {
  name: "App",
  components: {
    CardList,
  },
};
</script>
