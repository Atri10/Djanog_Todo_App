<template>
    <div class="columns">
        <div class="column is-6">
            <p class="maintitle">
                Remaining Tasks
            </p>
            <div class="cust" v-for="task in Tasks" v-bind:key="task.id">
                <div v-if="task.done === false">
                    <template>
                        <section>
                            <div class="card" aria-id="contentIdForA11y3">
                                <div
                                        class="card-header"
                                        role="button"
                                        aria-controls="contentIdForA11y3">
                                    <p class="card-header-title">
                                        <template class="tasktitle" >{{task.title}}</template>
                                    </p>
                                </div>
                                <div class="card-content">
                                    <div class="content">
                                        <template>
                                            {{task.description}}
                                        </template>
                                    </div>
                                </div>
                                <footer class="card-footer">
                                    <a class="card-footer-item">
                                        <template>Done</template>

                                    </a>
                                    <a class="card-footer-item">
                                        <template>Delete</template>

                                    </a>

                                </footer>
                            </div>
                        </section>
                    </template>
                </div>
            </div>

        </div>
        <div class="column is-6">
            <p class="maintitle">
                Completed Tasks
            </p>
            <div class="cust" v-for="task in Tasks" v-bind:key="task.id">
                <div v-if="task.done === true">
                    <template>
                        <section>
                            <div class="card" aria-id="contentIdForA11y3">
                                <div
                                        class="card-header"
                                        role="button"
                                        aria-controls="contentIdForA11y3">
                                    <p class="card-header-title">
                                        <template class="tasktitle">{{task.title}}</template>
                                    </p>
                                </div>
                                <div class="card-content">
                                    <div class="content">
                                        <template>
                                            {{task.description}}
                                        </template>
                                    </div>
                                </div>
                                <footer class="card-footer">

                                    <a class="card-footer-item">
                                        <template>Delete</template>

                                    </a>

                                </footer>
                            </div>
                        </section>
                    </template>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    // eslint-disable-next-line no-unused-vars


    import axios from 'axios'

    export default {
        name: "Tasklist",

        data() {
            return {
                Tasks: []
            }
        },
        mounted() {
            this.fetchTasks()
        },
        methods: {
            fetchTasks() {
                axios({
                    methods: 'get',
                    url: 'http://127.0.0.1:8000/Task/',
                     auth: {
                            username: 'atri',
                            password: 'root'
                        }
                }).then(response => this.Tasks = response.data)
            }
        }
    }
</script>

<style scoped>
    .maintitle {
        margin-top: 30px;
        text-align: center;
        font-weight: bold;
        font-size: 25px;
        margin-bottom: 20px;
    }

    .cust {
        width: 70%;
        margin-left: auto;
        margin-right: auto;
        margin-top: 20px;
        text-align: justify;
        font-weight: 500;
    }





</style>