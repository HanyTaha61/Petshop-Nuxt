<template>
    <div class="main">
        <b-col>
            <nuxt-link to="/">
                <img :src="require(`../../../assets/img/brands/${img.src}`)" alt="img">
            </nuxt-link>
        </b-col>
    </div>
</template>

<script>
export default {
props: ['img']
}
</script>

<style>

</style>
