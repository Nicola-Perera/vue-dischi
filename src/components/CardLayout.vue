<template>
    <div id="CardLayout">
        <div class="poster">
            <img :src="poster" alt="">
        </div>

        <h2> {{ title }} </h2>
        <h3> {{ author }} </h3>
        <h3> {{ year }} </h3>
    </div>
</template>

<script>

export default {
    name: 'CardLayout',
}
</script>

<style lang="scss">

</style>
