<template>
    <section>
        <div class="container">
            <div class="row">
                <CardAlbum class="col my-1" v-for="album in albums" :key="album.title" :album="album"/>
            </div>
        </div>
    </section>
</template>

<script>
    import axios from 'axios';
    import CardAlbum from '../common/CardAlbum.vue';

    export default{
        name: 'AlbumSection',
        data() {
            return {
                albums: [],
            };
        },

        components: {
            CardAlbum,
        },

        created() {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((response)=> {
                // handle success
                this.albums = response.data.response;
            })
            .catch((error) => {
                // handle error
                console.log(error);
            });
        }
    }
</script>

<style lang="scss" scoped>

.container {
    padding: 50px;
    margin: auto;
}
</style>