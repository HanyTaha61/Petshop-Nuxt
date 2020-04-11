<template>
    <div class="sale w-100">
        <nuxt-link class="" to="/sale"><h4 class="my-2 py-2 text-center mx-auto">sale</h4></nuxt-link>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
    .sale{

        a{
            text-decoration: none;

            h4{
                font-size: 1em;
                color: var(--secondary-color);
                transition: background-color 0.4s;
                padding: 3px 5px;
            
                &:hover{
                    background-color: #ccc;
                    color: var(--third-color);
                }
            }
        }
    }
</style>
