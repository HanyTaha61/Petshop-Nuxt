<template>
    <b-container class="whats_new mt-5">
        <h4 class="text-danger mb-3">what's new</h4>
        <b-row>
            <b-col>
                <nuxt-link v-for="(img, i) in 5" :key="i" :to="`/whats_new/item${i+1}`">
                    <b-img class="mr-2 mb-2 image rounded" width="200" :src="require(`../assets/img/whats_new/${i+1}.jpeg`)"/>
                </nuxt-link>
            </b-col>
        </b-row>
    </b-container>
</template>

<script>
export default {
    methods:{
        
    }
}
</script>

<style lang='scss' scoped>
.whats_new{

    h4{

    }
    .row{

        .col{

            a{
                overflow: hidden;
                
                &:hover img{
                    filter: grayscale(0);
                    border: 1px solid var(--secondary-color);
                    transform: scale(1.05);
                
                }
                img{
                    transition: 0.3s;
                    filter: grayscale(80%);
                    
                }   
            }
        }
    }
}
</style>
