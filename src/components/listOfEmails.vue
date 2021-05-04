<template>
  <div v-if="emails.length">
    <h3>List of Emails</h3>

    <div class="list-wrapper">
      <div v-for="(email, index) in emails" :key="index">
        <span>{{ email }}</span>
        <button @click="removeEmail(email)">Remove Email</button>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: "ListOfEmails",
  props: ["emails"],
  methods: {
    removeEmail(email) {
      this.$emit('removeEmail', email)
    },
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3{
  margin-top:20px;
  margin-bottom:20px;
}
.list-wrapper div {
  display: flex;
  margin-bottom: 20px;
}
.list-wrapper div span {
  flex-basis: 5%;
}
</style>
