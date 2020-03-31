<template>
    <div class="lower_navbar">
        <div class="outer_container" >
            <b-container>
                <b-navbar toggleable="lg">
                    <b-navbar-toggle target="nav-collapse2" class="hamburger">
                        <span></span><span></span><span></span>
                    </b-navbar-toggle>
                    <b-collapse id="nav-collapse2" is-nav>
                        <ul class="list">
                            <li :class="`button_${i+1}`" v-for="(item,i) in menu_items" :key="i" class="btn btn-warning py-2 ml-1 d-none d-lg-inline-block">
                                <nuxt-link to="#" class="title">{{item.title}}</nuxt-link>
                                <b-row :key="`img-cont_${i+1}`" tag="ul" :class="`img-cont_${i+1}`" class="bg-light mt-2">

                                <!-- menu components -->

                                    <shop-by-brand :is='item.name'  tag="li" lg="2" :class="`menu-item_${i2}`" class="ml-0 my-1 py-2" v-for="(img, i2) in images" :key="i2" :img='img'/>
                                
                                <!-- menu components -->

                                </b-row>
                            </li>
                            <!-- Show for small, medium screen devices -->
                            <li class="d-lg-none mini-menu">
                                <div class="tablist" role="tablist">
                                    <b-card no-body class="mb-1 card-main" v-for="(item,i) in menu_items" :key="i">
                                        <b-card-header header-tag="header" class="p-1 card_header_main" role="tab">
                                            <b-button class="btn_main" block href="#" v-b-toggle ="`accordion-${i+1}`" variant="warning">{{item.title}}</b-button>
                                        </b-card-header>
                                        <b-collapse class="collapse_main" :id="`accordion-${i+1}`" accordion="my-accordion" role="tabpanel">
                                            <b-card-body class="card_body_main">
                                                <nuxt-link to="./host">
                                                    <b-img thumbnail rounded class="border" v-for="(img,i) in images" :key="i" :src="require(`../../assets/img/brands/${img.src}`)" alt="img"/>
                                                </nuxt-link>
                                            </b-card-body>
                                        </b-collapse>
                                    </b-card>
                                </div>                                
                            </li>
                        </ul>
                    </b-collapse>
                </b-navbar>
            </b-container>
        </div>
    </div>
</template>


<script>
import ClickOutside from 'vue-click-outside'
import shopByBrand from './components/shopByBrand'
import shopByPet from './components/shopByPet'
import petServices from './components/petServices'
import sale from './components/Sale'
import help from './components/Help'
import findAStore from './components/findAStore'

export default {
    components: {shopByBrand, shopByPet, petServices, sale ,help, findAStore},
    directives: {ClickOutside},
    computed:{
        // menu_components(item) {
        //     if(this.menu_items[item.title]){
        //        return this.menu_items[item.name]
        //     }
        // },
    },
    methods:{
        toggle_div(){
            return this.show_div = !this.show_div
        },
        toggle () {
            this.opened = !this.opened;
            let selected_span = document.getElementById('caret')

            if(selected_span.classList.contains('caret_up')){
                selected_span.classList.remove('caret_up')
                selected_span.classList.add('caret_down')

            }else{
                selected_span.classList.add('caret_up')
                selected_span.classList.remove('caret_down')
            }
        },

    hide () {
        this.opened = false
    },
    hover(){
        return this.show_div = !this.show_div
    }
},    
    data(){
        return{
            text: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus eius repellat natus similique laudantium vero consectetur ea quos, optio fugit nam laboriosam vel eaque adipisci. Omnis illo officia fugit dolorum.`,
            opened: false,
            show_div: false,
            images:[
                {src: 'Authority.jpeg'},
                {src: 'All-Living-Things.jpeg'},
                {src: 'Blue Buffalo.jpeg'},
                {src: 'Dentleys.jpeg'},
                {src: 'Great Choice.jpeg'},
                {src: 'Greenies.jpeg'},
                {src: 'Hills Science Diet.jpeg'},
                {src: 'Merrick.jpeg'},
                {src: 'Nutro.jpeg'},
                {src: 'Purina Pro Plan.jpeg'},
                {src: 'Royal Canin Vet.jpeg'},
                {src: 'Royal Canin.jpeg'},
                {src: 'Simply Nourish.jpeg'},
                {src: 'Thrive.jpeg'},
                {src: 'Top Fin.jpeg'},
                {src: 'Top Paw.jpeg'},
                {src: 'Wellness.jpeg'},
                {src: 'Whisker City.jpeg'},
            ],
            menu_items:[
                {title: 'Shop By Brand', name: 'shopByBrand'},
                {title: 'Shop By Pet', name: 'shopByPet'},
                {title: 'Pet Services', name: 'petServices'},
                {title: 'Sale', name: 'sale'},
                {title: 'Help', name: 'help'},
                {title: 'Find A Store', name: 'findAStore'}
            ]
      // shopByBrand, shopByPet, petServices, sale ,help
        }
    },
  mounted () {
      // prevent click outside event with popupItem.
    this.popupItem = this.$el
  }
}
</script>


<style scoped lang='scss'>

    .list{
        list-style: none;
        margin-top: 0;
        margin-bottom: 0;

        @for $i from 1 to 7{
        
            .button_#{$i}{
                width: 165px;
                position: relative;

                @media (max-width: 1199px) {
                    width: 135px;
                }

                &:hover .img-cont_#{$i}{
                    display: flex;
                    justify-content: flex-start;

                }
                

                .img-cont_#{$i}{
                    list-style: none;
                    position: absolute;
                    top: 35px;
                    left: 60px - ($i*140);
                    width: 1000px;
                    border-radius: 5px;
                    display: none;

                        &::after{
                            content: "";
                            position: absolute;
                            top: -8px;
                            left: 30px + ($i*140);
                            z-index: 1;
                            margin-left: -10px;
                            width: 0;
                            height: 0;
                            border-left: 10px solid transparent;
                            border-right: 10px solid transparent;
                            border-bottom: 10px solid #fff;
                            // display: none;
                            display: block;

                            @media (max-width: 1199px) {
                                left: 30px + ($i*140);
                            }   
                        }
                    @for $x from 0 to 19{
                        
                        .menu-item_#{$x}{
                            list-style: none;
                            a{
                                
                                img{
                                    border: 1px solid #000;
                                    transition: 0.1s;
                                    
                                    &:hover{
                                        border: 2px solid #000;
                                        box-shadow: 5px 5px 25px #123;
                                    }
                                }
                            }
                        }
                    }
                }

                .title{
                    color: var(--secondary-color);
                    font-size: 1.1em;
                    text-decoration: none;

                    @media (max-width:1199px) {
                        font-size: 1em;

                    }
                }
            }
        }
        
        .mini-menu{

            .tablist{

                .card-main{

                    .card_header_main{

                        .btn_main{


                        }
                    }

                    .collapse_main{

                        .card_body_main{

                            a{

                                img{
                                    transition: 0.2s;

                                    &:hover{
                                        transform: scale(1.05);
                                        border: 1px solid #000;
                                        box-shadow: 5px 5px 20px #111;
                                    }
                                }
                            }
                        }
                    }
                }
            }
        }
    }
    .slide-enter-active, .slide-leave-active {
    transition: opacity 0.5s;
    }
    .slide-enter, .slide-leave-active /* .slide-leave-active below version 2.1.8 */ {
    opacity: 0;
    }
</style>
    

<style src='./navbar2.scss' lang="scss"/>
