<template>
  <div v-if="emails.length">
    <h3>Emails CSV</h3>
    <div>
      {{emails.toString()}}
    </div>

  </div>
</template>

<script>
export default {
  name: "ListOfEmails",
  props: ["emails"],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3{
  margin-top:20px;
  margin-bottom:20px;
}
</style>
