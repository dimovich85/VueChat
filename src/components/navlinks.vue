<template>
    <nav id="nav">
        <ul>
            <li 
                v-for="(value, key) in links"
                :key="key"
            >
                <a :href="value.url"> {{value.name}} </a>
            </li>
        </ul>
    </nav>
</template>

<script>
export default {
    props: {
        links: Array
    }
}
</script>

<style>
    #nav a{
        color: green;
    }
</style>