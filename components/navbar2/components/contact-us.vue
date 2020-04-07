<template>
    <div class="main w-100">
        <nuxt-link to="/contact"><h4 class=" my-2 py-2 text-center mx-auto">Contact Us</h4></nuxt-link>
        <nuxt-link to="/track-order"><h4 class=" my-2 py-2 text-center mx-auto">Track Your Order</h4></nuxt-link>
    </div>
</template>

<script>
export default {
    head(){
        return{
            link: [

            ],
            script: [

            ]
        }
    }
}
</script>

<style lang="scss" scoped>
    .main{
        
        a{
            text-decoration: none;

            h4{
                color: var(--secondary-color);
                transition: background-color 0.4s;
                width: 100%;
            
                &:hover{
                    background-color: #ccc;
                    color: var(--third-color);
                }
            }
        }
    }

</style>


