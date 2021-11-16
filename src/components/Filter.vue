<template>
    <div id="filter_box">
        
        <select name="genre_filter" id="genre_filter">
            <option value="all">all</option>
            <option value="rock">rock</option>
            <option value="pop">pop</option>
            <option value="jazz">jazz</option>
            <option value="metal">metal</option>
        </select>

    </div>
</template>

<script>
    export default {
        data() {
            return {
                filterGenre:'',
            };
        },
    };
</script>

<style lang="scss">

</style>
