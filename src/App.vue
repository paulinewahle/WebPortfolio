<script>
import { RouterLink, RouterView } from 'vue-router'
import WorkView from './views/WorkView.vue'
import Sphere from './components/Sphere.vue'
import LoadingScreen from './components/LoadingScreen.vue'
import Cursor from './components/Cursor.vue'
import SideNav from './components/SideNav.vue'
import CaseNav from './components/CaseNav.vue'
import HomeView from './views/HomeView.vue'
import Header from './components/Header.vue'

export default {
    props:{
    caseNav: false
    },
	components: {
    Cursor,
    SideNav,
    CaseNav,
    HomeView,
    WorkView,
    Header,
    },
    data(){
        return{
            links: [],
            sideNav: [],
            caseNav: []
        }
    },
    mounted(){
    }
}

</script>

<template>
    
    <body>

        <!-- consitional rendering deactivated maouse effect -->
        <!-- <SideNav :links="links" v-if="this.sideNav.length >= 1" /> -->
        <Header> </Header>
        <SideNav :links="links" :caseNav="caseNav"/>
        
        <!-- <SideNav  /> -->
        <Cursor :links="links"/>

        <!-- <Transition name="slide-fade"> -->
        <RouterView :sideNav="sideNav" :caseNav="caseNav">
           
        </RouterView>
        <!-- </Transition> -->
        
    </body>
</template>

<style scoped>
</style>
