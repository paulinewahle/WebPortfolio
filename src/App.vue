<script>
import { RouterLink, RouterView } from 'vue-router'
import WorkView from './views/WorkView.vue'
import Sphere from './components/Sphere.vue'
import LoadingScreen from './components/LoadingScreen.vue'
import Cursor from './components/Cursor.vue'
import SideNav from './components/SideNav.vue'
import HomeView from './views/HomeView.vue'

export default {

	components: {
    Cursor,
    SideNav,
    HomeView,
    WorkView
},
    data(){
        return{
            links: [],
            sideNav: [],
        }
    },
    mounted(){
    }
}

</script>

<template>
    
    <body>
        

        <!-- consitional rendering deactivated maouse effect -->
        <!-- <div v-if="this.sideNav.length == 1"> -->
        <SideNav :links="links"> </SideNav>
        <!-- </div> -->

        <Cursor :links="links"></Cursor>

        <!-- <router-view v-slot="{ HomeView }">
        <transition>
            <component :is="HomeView" />
        </transition>
        </router-view> -->

        <Transition name="slide-fade">
        <RouterView :sideNav="sideNav">
           
        </RouterView>
        </Transition>
        
    </body>
</template>

<style scoped>
</style>
