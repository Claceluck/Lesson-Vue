<template>
<v-app >
    <v-row class="fill-height">
        <!--неизменная часть-->
        <!-- <div>
            <p>Всего задач: {{tasks.length}}</p>
            <nav>
                <router-link to="/add/task">
                    Создать задачу
                </router-link>
                <router-link to="/show/tasks">
                    Просмотр задач
                </router-link>
            </nav>
        </div> -->
        <v-navigation-drawer
                    v-resize="onResize"
                    v-model="drawer"
                    :mini-variant.sync="mini"
                    permanent>

                <v-list-item>
                    <v-list-item-avatar>
                        <v-img :src="src"></v-img>
                    </v-list-item-avatar>

                    <v-list-item-content>
                        <v-list-item-title>LOGIN</v-list-item-title>
                        <v-list-item-subtitle>Всего задач: {{tasks.length}}</v-list-item-subtitle>
                    </v-list-item-content>
                </v-list-item>

                <v-divider></v-divider>

                <v-list>
                    <v-list-item>
                        <v-list-item-action>
                            <v-icon>mdi-movie</v-icon>
                        </v-list-item-action>

                        <v-list-item-content>
                            <v-list-item-title>
                                <router-link class="text-uppercase text--secondary" to="/add/task">
                                    Создать задачу
                                </router-link>
                            </v-list-item-title>
                        </v-list-item-content>
                    </v-list-item>

                    <v-list-item>
                        <v-list-item-action>
                            <v-icon>mdi-movie</v-icon>
                        </v-list-item-action>

                        <v-list-item-content>
                            <v-list-item-title>
                                <router-link class="text-uppercase text--secondary" to="/show/tasks">
                                    Просмотр задач
                                </router-link>
                            </v-list-item-title>
                        </v-list-item-content>
                    </v-list-item>


                </v-list>

            </v-navigation-drawer>

       <!--подгружаемый контент-->
            <v-content>
                <v-container class="fill-height">
                    <router-view class="offset-xl-3 col-xl-6 offset-lg-2 col-lg-8"></router-view>
                </v-container>
            </v-content>
        </v-row>
    </v-app>
</template>

<script>
    import {allTasks} from "./tmp/taskArr";
    export default {
        name: "App", //имя файла без расширения
        data: function () {
            return {
                tasks: allTasks,
                drawer: null,
                mini: false,
                // src: "https://picsum.photos/id/237/300"
                src: "./static/img/cat-pic.png"
            }
        },
        mounted(){
            this.onResize()
        },
        methods: {
            onResize: function () {
                console.log(window.innerWidth)
                this.mini = window.innerWidth < 850;
            }
        }
    }
</script>

<style lang="scss">
</style>