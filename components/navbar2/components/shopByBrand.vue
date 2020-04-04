<template>
    <b-row class="contains my-3">
        <b-col class="my-1" :class="`menu-item_${i+1}`" v-for="(img, i) in images" :key="i">
            <nuxt-link to="/comp">
                <img :src="require(`../../../assets/img/brands/${img.src}`)" alt="img">
            </nuxt-link>
        </b-col>
    </b-row>
</template>

<script>
export default {
props: ['images']
}
</script>

<style lang='scss' scoped>
.contains{
    @media (min-width: 992px) {
        margin-left: -50px;
    }
    
    @for $x from 0 to 19{              
        .menu-item_#{$x}{
            list-style: none;
            margin-top: -40px;

            a{
                
                img{
                    border: 1px solid #000;
                    transition: box-shadow 0.3s;

                    @media (max-width: 991px) {
                        width: 75px;
                    }
                    
                    &:hover{
                        border: 2px solid #000;
                        box-shadow: 5px 5px 25px #123;
                    }
                }
            }
            a:not(:first-child){
                margin-left: -20px;

            }
        }
    }
}
</style>
