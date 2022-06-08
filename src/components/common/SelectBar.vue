<template>
    <form>
        <select value="all" name="genre" id="genre" v-model="select.selectedText">
            <option value="all">All</option>
            <option value="rock">Rock</option>
            <option value="pop">Pop</option>
            <option value="jazz">Jazz</option>
            <option value="metal">Metal</option>
        </select>
    </form>
</template>

<script>
import select from '../../shared/select.js';

export default {
    name: 'SelectBar',
    data() {
        return {
            select,
        };
    },
}
</script>

<style lang="scss" scoped>

select {
    margin: 20px;
}

</style>