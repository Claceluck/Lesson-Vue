<template>
    <div>
        <!--неизменная часть-->
        <div>
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
    export default {
        name: "App"
    }
</script>

<style lang="scss">

</style>
