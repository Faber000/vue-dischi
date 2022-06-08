<template>
    <section>
        <div class="container">
            <SelectBar/>
            <div class="row">
                <CardAlbum class="col my-1" v-for="album in genreFiltered" :key="album.title" :album="album"/>
            </div>
        </div>
    </section>
</template>

<script>
    import axios from 'axios';
    import SelectBar from '../common/SelectBar.vue'
    import CardAlbum from '../common/CardAlbum.vue';
    import select from '../../shared/select';

    export default{
        name: 'AlbumSection',
        data() {
            return {
                select,
                albums: [],
            };
        },

        components: {
            SelectBar,
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
        },

        computed: {
            genreFiltered() {
                if(this.select.selectedText.toLowerCase()=="all") {
                    return this.albums;
                } else 
                {
                    return this.albums.filter((elm)=> {
                        return elm.genre.toLowerCase()==(this.select.selectedText.toLowerCase());
                    })
                }
            }
        }
    }
</script>

<style lang="scss" scoped>

.container {
    padding: 50px;
    margin: auto;
}

section {
    min-height: calc(100vh - 60px);
}
</style>