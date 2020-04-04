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
                                <b-row :key="`img-cont_${i+1}`" tag="ul" :class="`img-cont_${i+1}`" class="bg-light mt-1 pr-1">

                                <!-- menu components -->
                                    <client-only>
                                        <component :is="`comp${i+1}`" :images="images" :cols='cols'/>
                                    </client-only>
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
                                <!-- mini-menu components -->
                                                <client-only>
                                                    <component :is="`comp${i+1}`" :images="images" :cols='cols'/>
                                                </client-only>
                                <!-- mini-menu components -->
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
import comp5 from './components/contact-us'
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
            ],
            cols:[
                {name: 'Dog',
                links:{
                    col1:['Food','Canned Food', 'Dry Food', 'Food Toppers', 'Shop All'],
                    col2:['Treats','Biscuits & Bakery', 'Bones & Rawhide', 'Chewy Treats', 'Dental Treats', 'Jerky', 'Training Treats'],
                    col3:['Supplies','Beds & Furniture', 'Bowls & Feeders', 'Cleaning Supplies', 'Clothing & Shoes', 'Collars, Harnesses & Leashes', 'Crates, Gates & Containments'],
                    col4:['Others','Dental Care & Wellness', 'Flea & Tick', 'Grooming Supplies', 'Toys', 'Training & Behavior'],
                }},
                {name: 'Cat',
                links:{
                    col1:['Food & Treats','Wet Food', 'Treats', 'Dry Food', 'Catnip & Grass', 'Shop All'],
                    col2:['Litter','Deodorizers & Filters', 'Litter', 'Litter Boxes', 'Mats & Liners', 'Waste Disposal'],
                    col3:['Supplies','Beds & Furniture', 'Bowls & Feeders', 'Cleaning & Repellents', 'Collars, Harnesses & Leashes', 'Crates, Gates & Containments', 'Dental Care & Wellness'],
                    col4:['Others','Flea & Tick', 'Grooming Supplies', 'Toys'],
                }},
                {name: 'Fish',
                links:{
                    col1:['Food & Care','Desease Treatment', 'Feeders', 'Food', 'Plant Care', 'Pond Care', 'Saltwater Aquarium Care'],
                    col2:['Others','Water Care & Conditioning', 'Water Quality Testers'],
                    col3:['Supplies','Decor Gravel & Substrate', 'Heating & Lighting', 'Filter & Pumps', 'Maintenance & Repair', 'Starter Kits', 'Tanks & Aquariums'],
                    col4:['Live Fish','Goldfish Betta & More'],
                }},
                {name: 'Bird',
                links:{
                    col1:['Food & Treats', 'Pet Bird Food', 'Treats', 'Wild Bird Food'],
                    col2:['Supplies', 'Bowls & Feeders', 'Cages & Stands', 'Cleaning & Odor Control', 'Grooming', 'Health Care & Vitamins', 'Litter & Nesting'],
                    col3:['Others', 'Toys, Perches & Decor', 'Wild Bird Food & Supplies'],
                    col4:['Live Birds','Conure, Parakeet & More'],
                }},
                {name: 'Reptile', 
                links:{
                    col1:['Habitats & Decor', 'Habitat Accessories', 'Habitat Decor', 'Starter Kits', 'Terrariums'],
                    col2:['Supplies', 'Cleaning & Water Care', 'Environmental Control & Lighting', 'Feeders & Food Storage', 'Food', 'Substrate & Bedding', 'Vitamins & Supplements'],
                    col3:['Live Reptiles', 'Snakes, Turtles & More'],
                    col4:['Others','Others']
                }},
                {name: 'Small Pet', 
                links:{
                    col1:['Food, Treats & Hay', 'Hay', 'Food', 'Treats'],
                    col2:['Supplies', 'Cages, Habitats & Hutches', 'Cleaning & Odor Removers', 'Harnesses & Travel Carriers', 'Health & Grooming', 'Litter & Bedding', 'Starter Kits'],
                    col3:['Others', 'Toys & Habitat Accessories'],
                    col4:['Live Small Pets','Hamsters, Guinea Pigs & More'],
                }}
            ]            
        }
    },
  mounted () {
      // prevent click outside event with popupItem.
    this.popupItem = this.$el
  }
}
</script>

<style src='./navbar2.scss' lang="scss" scoped/>
