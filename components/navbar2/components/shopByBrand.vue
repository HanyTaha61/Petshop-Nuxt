<template>
    <b-row class="contains">
        <b-col class="my-1" :class="`menu-item_${i+1}`" v-for="(img, i) in images" :key="i">
            <nuxt-link to="/">
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
    
    @for $x from 0 to 19{              
        .menu-item_#{$x}{
            list-style: none;

            a{
                
                img{
                    border: 1px solid #000;
                    transition: box-shadow 0.3s;
                    
                    &:hover{
                        border: 2px solid #000;
                        box-shadow: 5px 5px 25px #123;
                    }
                }
            }
        }
    }
}
</style>
