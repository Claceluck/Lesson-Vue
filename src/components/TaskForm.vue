<template>
   <div>
       <p>{{outside}}</p>

       <form @submit.prevent="addTask">
           <input type="text" name="title" v-model.trim="title">
           <input type="datetime-local" name="date" v-model="date">
           <textarea name="description" v-model.trim="description"></textarea>
           <input type="submit" value="Добавить">
       </form>

   </div>
</template>

<script>
    import {allTasks} from "../tmp/taskArr";
    export default {
        name: "TaskForm",
        props:{
            outside: String
        },
        data: function() {
            return {
                title: "",
                date: "",
                description: "",
                tasks: allTasks
            }
        },
        methods: {
            addTask: function () {
                // console.log("Добавление задачи", allTasks);
                console.log(this.title, this.date, this.description);
                this.tasks.push({
                    title: this.title,
                    date: this.date,
                    description: this.description,
                    isDel: false
                });
            }
        }
    }
</script>

<style scoped>

</style>