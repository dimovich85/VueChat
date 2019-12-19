<template>
    <div id="header">
        HEADER
        <br>
        <button @click="isModalOpen = !isModalOpen">+</button>
        <Modal 
            title="New link" 
            v-if="isModalOpen" 
            @newLink="onNewLink"
            @modalClose="data => isModalOpen = !data"
        />
        <Navigation :links="links"/>
    </div>
</template>

<script>
import Navigation from './navlinks.vue';
import Modal from './Modal.vue';
export default {
    components: {
        Navigation,
        Modal
    },
    data(){
        return {
            links: [
                { url: '#1', name: 'First link' },
                { url: '#2', name: 'Second link' },
                { url: '#3', name: 'Third link' }
            ],
            isModalOpen: false
        }
    },
    methods: {
        onNewLink(data){
            this.links.push(data);
            this.isModalOpen = false;
        }
    }
}
</script>

<style>
    #header{
        color: red;
    }
</style>