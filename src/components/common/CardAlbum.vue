<template>
    <div class="album">
        <img :src="album.poster" alt="">
        <h2>{{album.title}}</h2>
        <h3>{{album.author}}</h3>
        <h4>{{album.year}}</h4>
    </div>
</template>

<script>
    export default {
        name: 'CardAlbum',
        props: {
            album: Object,
        }
    }
</script>

<style lang="scss" scoped>
    

    .album {
        background-color: rgb(46, 58, 70);
        margin-right: 20px;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 20px;
        color: white;
    }

    img {
        width: 150px;
        height: 150px;
    }

    h4 {
        font-size: 15px;
    }

    h3 {
        font-size: 16px;
    }

    h2 {
        margin-top: 10px;
        font-size: 18px;
    }
    
</style>