<template>
  <div v-on:click="this.obj.isDel = !this.obj.isDel">
      <h3>{{obj.title.toUpperCase()}} | До: {{obj.date}}</h3>
      <p>{{obj.description}}</p>
      <hr>
  </div>
</template>

<script>
    export default {
        name: "TaskCard",
        props: {
            obj: Object
        }
    }
</script>

<style scoped>

</style>