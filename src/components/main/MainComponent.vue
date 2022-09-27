<template>
<main>

</main>
</template>

<script>
import axios from 'axios';



export default {
    name: "MainComponent",
    data(){
        return{
            url: 'https://flynn.boolean.careers/exercises/api/array/music',
            albums: []
        }
    },
    created(){
        this.getAlbumsData();

    },
    methods:{
        getAlbumsData(){
            axios.get(this.url)
            .then((response) =>{
                if (this.idResponseOk(response)){
                    console.log(response.data);
                    response.data = this.albums;
                }
                
            })
        },
        idResponseOk({status}){
            return status === 200;
        }
    },
    
}
</script>

<style lang="scss" scoped>
@import '@/assets/main.scss';
main{
    height: 93vh;
    width: 100%;
    background-color: $app-dark;
    padding: 5% 10%;
}

</style>