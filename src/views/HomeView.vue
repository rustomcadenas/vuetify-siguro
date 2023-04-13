<template>
    <v-app>
        <SideBar />

        <v-main> 
            
        </v-main>
    </v-app>
</template>

<script>
import SideBar from '../components/SideBar.vue'

export default{
    components:{
        SideBar
    },
    data(){
        return{
            msg: "Hello WOrld"
        }
    }, 

    methods:{
        
    }
}

</script> 