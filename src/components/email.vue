<template>
  <div class="app-wrapper">
    <input type="text" v-model="email" placeholder="Enter Email" />
    <button @click="addEmail()">Add Email</button>
    <EmailsList @removeEmail="removeEmail" :emails="emails" />
    <EmailsCSV :emails="emails" />
  </div>
</template>

<script>
import EmailsList from "@/components/listOfEmails";
import EmailsCSV from "@/components/EmailsCSV";

export default {
  name: "Email",
  components: {
    EmailsList,
    EmailsCSV,
  },
  data() {
    return {
      email: "",
      emails: [],
    };
  },
  methods: {
    addEmail() {
      if (!this.email) {
        alert("Email cannot be empty");
        return;
      }
      if (!this.emails.includes(this.email)) {
        this.emails.push(this.email);
        this.email = "";
      } else {
        alert("Email cannot be duplicated!");
        return;
      }
    },
    removeEmail(email) {
      this.emails = this.emails.filter((item) => item !== email);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
button {
  margin-left: 20px;
}
</style>
