<template>
    <div>
        <!--неизменная часть-->
        <div>
            <p>Всего задач: {{tasks.length}}</p>
            <nav>
                <router-link to="/add/task">
                    Создать задачу
                </router-link>
                <router-link to="/show/tasks">
                    Просмотр задач
                </router-link>
            </nav>
        </div>

        <!--подгружаемый контент-->
        <div>
            <router-view></router-view>
        </div>
    </div>
</template>

<script>
    import {allTasks} from "./tmp/taskArr";
    export default {
        name: "App",
        data: function () {
            return {
                tasks: allTasks
            }
        }
    }
</script>

<style lang="scss">

</style>
