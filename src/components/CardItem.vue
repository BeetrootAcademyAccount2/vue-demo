<template>
  <div class="card">
    <img src="../assets/logo.png" alt="Avatar" style="width: 100%" />
    <div class="container">
      <h4>
        <b>{{ person.name }}</b>
      </h4>
      <p>{{ person.job }}</p>
      <button class="delBtn" @click="deletePerson">Delete</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardItem",
  props: ["person"],
  methods: {
    deletePerson() {
      const personId = this.person.id;
      this.$emit("deletePerson", personId);
    },
  },
};
</script>

<style>
.card {
  width: 300px;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}

.container {
  padding: 2px 16px;
}

.delBtn {
  margin-bottom: 10px;
  background-color: red;
}
</style>
