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
                                    <component :is="`comp${i+1}`" :images="images"/>
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
                                                    <b-img
                                                    thumbnail
                                                    rounded
                                                    class="border"
                                                    v-for="(img,i) in images" :key="i"
                                                    :src="require(`../../assets/img/brands/${img.src}`)"
                                                    alt="img"/>
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
import comp1 from './components/shopByBrand'
import comp2 from './components/shopByPet'
import comp3 from './components/petServices'
import comp4 from './components/Sale'
import comp5 from './components/Help'
import comp6 from './components/findAStore'

export default {
    components: {comp1, comp2, comp3, comp4 ,comp5, comp6},
    directives: {ClickOutside},
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
                {title: 'Shop By Brand'},
                {title: 'Shop By Pet'},
                {title: 'Pet Services'},
                {title: 'Sale'},
                {title: 'Help'},
                {title: 'Find A Store'}
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

<style src='./navbar2.scss' lang="scss" scoped/>
