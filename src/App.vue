<template>
    <div>
        <div id="app">
            <navbar></navbar>
            <h2>
                Welcome, Lets Schedule your day
            </h2>
        </div>
        <div id="Form">
            <ContentForm></ContentForm>
        </div>
        <Tasklist></Tasklist>
    </div>


</template>

<script>
    import navbar from "./components/navbar";
    import ContentForm from "./components/ContentForm";
    import Tasklist from "./components/Tasklist";

    export default {
        name: 'App',
        components: {
            navbar,
            ContentForm,
            Tasklist
        }
    }
</script>

<style scoped>
    h2 {
        padding-top: 20px;
        font-size: 30px;
        font-weight: bold;
        text-align: center;
    }

    #Form {
        margin-top: 50px;
    }


</style>