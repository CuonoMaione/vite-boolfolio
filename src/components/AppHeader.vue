<template >
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
        
        <ul v-for="link in links">
            <li>
                <router-link :to="{ name: link.route }">
                    {{ link.name }}
                </router-link>
            </li>
        </ul>
    </nav>
</template>
<script>
export default {
    name: 'AppHeader',
    
    data() {
        return {
            links : [
                {
                    route: 'homepage',
                    name: 'Homepage'
                },
                {
                    route: 'about',
                    name: 'About Us'
                },
                {
                    route: 'projects.index',
                    name: 'Projects'
                },
            ]
        }
    },
}
</script>
<style lang="scss">
    
</style>