<template>
    <div id="footer">
        FOOTER
        <button @click="toggleNavLinks">Hide links</button>
        <h2>
            {{ alertText }}
        </h2>
        <footer-links v-if="areNavVisible" />
    </div>
</template>

<script>
import FooterLinks from './footer-links.vue';
export default {
    components: {
        FooterLinks
    },
    data(){
        return {
            areNavVisible: true
        }
    },
    computed: {
        alertText(){
            return this.areNavVisible ? 'Links will be closed' : 'Links will be opened';
        }
    },
    methods: {
        toggleNavLinks(e){
            this.areNavVisible = !this.areNavVisible;
            this.info(e);
        },
        info(e){
            alert( this.alertText );
            window.console.log(e);
        }
    }
}
</script>

<style>
    #footer{
        color: blueviolet;
    }
</style>