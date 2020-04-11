<template>
  <b-container>
    <b-carousel
        id="carousel-1"
        no-hover-pause
        :interval="4000"
        controls
        indicators
        img-height="300"
        background="#ababab">

        <nuxt-link v-for="(slide, i) in 4" :key="i" :to="`/slide${i+1}`">
            <b-carousel-slide
                caption=""
                text=""
                :img-src="require(`../../assets/img/carousel/slide${i+1}.jpeg`)"
            ></b-carousel-slide>
        </nuxt-link>

    </b-carousel>
  </b-container>
</template>

<script>
  export default {
    data() {
      return {

      }
    }
  }
</script>

<style lang="scss">
.container{

    .carousel{
        .sr-only{display: none !important;}

        .carousel-inner{

            .carousel-item{

                img{
                    display: block;
                    width: 50%;
                    height: 100%;
                }
            }
        }

        .carousel-indicators{
            z-index: 1;
            margin-bottom: 5px;
            bottom: -35px;

            @media (max-width: 991px) {
                display: none;
            }

            li {
                box-sizing: content-box;
                width: 15px;
                height: 15px;
                border-radius: 50%;
                margin-right: 3px;
                margin-left: 3px;
                text-indent: -999px;
                cursor: pointer;
                background-color: var(--secondary-color);
                background-clip: padding-box;
                border-top: 10px solid transparent;
                border-bottom: 10px solid transparent;
                opacity: 0.5;
                transition: 0.4s;
                outline: none;
                border: 1px solid #000;

                @media (min-width: 576px) and (max-width: 767px) {
                    left: -50px;
                }

                &:hover{
                    background-color: var(--primary-color);
                }
            }

            li.active{
                background-color: var(--third-color);
            }
        }
        .carousel-control-prev{

            @media (max-width: 575px) {
                left: 0;    
            }

            @media (min-width: 576px) and (max-width: 610px) {
                left: -35px;

            }

            span{
                background-color: #000;
                padding: 10px;
                position: relative;
                width: 30px !important;
                height: 30px !important;
                border-radius: 50%;
                display: block;

                @media (max-width: 991px) {
                    left: -10px;
                    padding: 5px !important;
                }
            }

        }

        .carousel-control-next{

            @media (max-width: 576px) {
                right: 0;    
            }

            @media  (min-width: 576px) and(max-width: 610px) {
                right: -35px;
            

            }

            span{
                background-color: #000;
                padding: 10px;
                position: relative;
                width: 30px !important;
                height: 30px !important;
                border-radius: 50%;

                @media (max-width: 991px) {
                    right: -10px;
                    width: 20px;
                    height: 20px;
                }
            }


        }
    }
}
</style>
