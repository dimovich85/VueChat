<template>
    <div id="modal">
        <h3>{{ title }}</h3>
        <label>
            URL: <br>
            <input type="text" v-model="url">
        </label>
        <br>
        <label>
            Name: <br>
            <input type="text" v-model="name">
        </label>
        <br>
        <button @click="onAddNewLink">SAVE</button>
        <hr>
        See what you'll get:
        <a :href="url">{{ name }}</a>
        <button class="closer" @click="$emit('modalClose', true)">X</button>
    </div>
</template>

<script>
export default {
    props: {
        title: String
    },
    data(){
        return {
            url: '',
            name: ''
        }
    },
    methods: {
        onAddNewLink(){
            let url = this.url;
            let name = this.name;
            this.$emit('newLink', {url, name});
        }
    }
}
</script>

<style scoped>
    #modal{
        position: fixed;
        background-color: rgba(0,0,0,.7);
        color: #fff;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        font-size: 30px;
        text-align: center;
        padding: 50px;
    }
    a{
        color: #fff;
    }
    .closer{
        font-size: 100px;
        position: absolute;
        top: 10px;
        right: 10px;
        background-color: transparent;
        border: none;
        color: #fff;
        cursor: pointer;
    }
</style>