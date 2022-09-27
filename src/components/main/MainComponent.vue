<template>
<main>    
    <div v-for="album in albums" :key="album.title">
    <AlbumCard :album="album"/>
    </div>
</main>
</template>

<script>
import axios from 'axios';
import AlbumCard from "@/components/main/AlbumCard.vue"



export default {
    name: "MainComponent",
    components: {AlbumCard},
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
                    this.albums = response.data.response;
                    console.log(this.albums);
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
    @include flex-row;
    justify-content: center;
    flex-wrap: wrap;
    height: 93vh;
    width: 100%;
    background-color: $app-dark;
    padding: 5% 10%;

}

</style>