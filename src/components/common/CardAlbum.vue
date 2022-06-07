<template>
    <div class="album">
        <img :src="album.poster" alt="">
        
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
    img {
        width: 200px;
        height: 200px;
    }
</style>