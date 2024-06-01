<template>
  <form @submit.prevent="submitHandle">
    <label for="fname">First name:</label><br />
    <input
      type="text"
      id="fname"
      name="fname"
      v-model="fname"
      ref="fnameRef"
    /><br />
    <label for="lname">Last name:</label><br />
    <input
      type="text"
      id="lname"
      name="lname"
      v-model="lname"
      ref="lnameRef"
    /><br /><br />
    <p>First Name: {{ fname }}</p>
    <p>Lat Name: {{ lname }}</p>
    <input type="submit" value="Submit" />
    <button @click="focus">Focus</button>
  </form>
</template>

<script>
export default {
  name: "LoginForm",
  data() {
    return {
      fname: "Jon",
      lname: "Doe",
      currentFocus: "lname",
    };
  },
  methods: {
    submitHandle() {
      console.log(this.fname, this.lname);
    },
    focus() {
      this.currentFocus = this.currentFocus === "fname" ? "lname" : "fname";
      this.currentFocus === "fname"
        ? this.$refs.lnameRef.focus()
        : this.$refs.fnameRef.focus();
    },
  },
};
</script>
