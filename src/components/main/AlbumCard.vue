<template>
  <div class="card">
    <img :src="album.poster" alt="not found" @error="replaceWrongImageUrl">
     <h1>{{ album.title}}</h1>
     <div class="author">
     <p>{{ album.author }}</p>
     <p>{{ album.year }}</p>
     </div>
     </div>
</template>

<script>
import errorImage from '@/assets/logo.png'

export default {
    name: 'AlbumCard',
    props:{
        album: Object,

    },
    methods:{
        replaceWrongImageUrl(e){
        console.log('errore');
        e.target.src = errorImage;
        }
    }

}
</script>

<style lang="scss" scoped>
@import '@/assets/main.scss';
.card{
    @include flex-col;
    background-color: $app-light;
    padding: 10px;
    margin: 10px;
    width: 120px;
    height: 180px;
    color: white;
    align-items: center;
    text-align: center;
    justify-content: space-between;
    img{
        height: 50%;
        object-fit: contain;
    }
    h1{
        font-size: 0.8rem;
    }
    p{
        font-size: 0.7rem;
        color: grey;
    }

}

</style>