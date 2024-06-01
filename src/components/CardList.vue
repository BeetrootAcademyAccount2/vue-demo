<template>
  <div>
    <LoginForm />
    <hr />
    <button @click="toggleAlertMessage">Toggle</button>
    <div v-if="isShown" class="alert">{{ message }}</div>
    <p v-else>Server is running</p>
    <CardItem
      v-for="person in people"
      :key="person.id"
      :person="person"
      @deletePerson="deletePerson"
    />
  </div>
</template>

<script>
import CardItem from "./CardItem.vue";
import LoginForm from "./LoginForm.vue";

export default {
  name: "CardList",
  data() {
    return {
      message: "Server not available",
      isShown: true,
      people: [
        {
          id: 1,
          name: "Jim",
          job: "Seller",
        },
        {
          id: 2,
          name: "Jack",
          job: "Marketer",
        },
        {
          id: 3,
          name: "Joe",
          job: "Architect & Engineer",
        },
      ],
    };
  },
  methods: {
    toggleAlertMessage() {
      this.isShown = !this.isShown;
    },
    deletePerson(personId) {
      this.people = this.people.filter((person) => person.id !== personId);
    },
  },
  components: {
    CardItem,
    LoginForm,
  },
};
</script>

<style scoped>
.alert {
  padding: 20px;
  background-color: #f44336;
  color: white;
}

p {
  color: red;
}
</style>
