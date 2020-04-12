<template>
    <div class="brands">
        <div class="all_brands" v-for="(brand, i) in brand_names" :key="i">
            <h1>{{brand.name}}</h1>
            <div v-for="(product, ii) in brand.product" :key="ii">
                <h2>{{product.name}}</h2>
                <p>Price: ${{product.price}}</p>
                <p>Rating: {{product.rating}}</p>
                <p>{{product.promo1}}</p>
                <p>{{product.promo2}}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            brand_names:[
                {
                    name:'Top Pow',
                    product:[
                        {
                            name: 'product1',
                            price: 30,
                            image: '',
                            rating: 3.5,
                            promo1: 'SAVE 10% With Buy Online, Pickup in Store or Curbside Pickup!',
                            promo2: 'Sign In & Enjoy Free Shipping Over $49'
                        }
                    ]
                },
                {
                    name:'blue Bufallo',
                    product:[
                        {
                            name: 'product1',
                            price: 30,
                            image: '',
                            rating: 3.5,
                            promo1: 'SAVE 10% With Buy Online, Pickup in Store or Curbside Pickup!',
                            promo2: 'Sign In & Enjoy Free Shipping Over $49'
                        }
                    ]
                },
                {
                    name:'Pro Plan',
                    product:[
                        {
                            name: 'product1',
                            price: 30,
                            image: '',
                            rating: 3.5,
                            promo1: 'SAVE 10% With Buy Online, Pickup in Store or Curbside Pickup!',
                            promo2: 'Sign In & Enjoy Free Shipping Over $49'
                        }
                    ]
                },
                {
                    name:'Hell\'s Science Diet',
                    product:[
                        {
                            name: 'product1',
                            price: 30,
                            image: '',
                            rating: 3.5,
                            promo1: 'SAVE 10% With Buy Online, Pickup in Store or Curbside Pickup!',
                            promo2: 'Sign In & Enjoy Free Shipping Over $49'
                        }
                    ]
                },
                {
                    name:'Top Fin',
                    product:[
                        {
                            name: 'product1',
                            price: 30,
                            image: '',
                            rating: 3.5,
                            promo1: 'SAVE 10% With Buy Online, Pickup in Store or Curbside Pickup!',
                            promo2: 'Sign In & Enjoy Free Shipping Over $49'
                        }
                    ]
                },
                {
                    name:'Great Choice',
                    product:[
                        {
                            name: 'product1',
                            price: 30,
                            image: '',
                            rating: 3.5,
                            promo1: 'SAVE 10% With Buy Online, Pickup in Store or Curbside Pickup!',
                            promo2: 'Sign In & Enjoy Free Shipping Over $49'
                        }
                    ]
                },
                {
                    name:'Royal Canin',
                    product:[
                        {
                            name: 'product1',
                            price: 30,
                            image: '',
                            rating: 3.5,
                            promo1: 'SAVE 10% With Buy Online, Pickup in Store or Curbside Pickup!',
                            promo2: 'Sign In & Enjoy Free Shipping Over $49'
                        }
                    ]
                },
                {
                    name:'Whisker City',
                    product:[
                        {
                            name: 'product1',
                            price: 30,
                            image: '',
                            rating: 3.5,
                            promo1: 'SAVE 10% With Buy Online, Pickup in Store or Curbside Pickup!',
                            promo2: 'Sign In & Enjoy Free Shipping Over $49'
                        }
                    ]
                },
                {
                    name:'All Living Things',
                    product:[
                        {
                            name: 'product1',
                            price: 30,
                            image: '',
                            rating: 3.5,
                            promo1: 'SAVE 10% With Buy Online, Pickup in Store or Curbside Pickup!',
                            promo2: 'Sign In & Enjoy Free Shipping Over $49'
                        }
                    ]
                },
                {
                    name:'Nutro',
                    product:[
                        {
                            name: 'product1',
                            price: 30,
                            image: '',
                            rating: 3.5,
                            promo1: 'SAVE 10% With Buy Online, Pickup in Store or Curbside Pickup!',
                            promo2: 'Sign In & Enjoy Free Shipping Over $49'
                        }
                    ]
                },
                {
                    name:'Authority',
                    product:[
                        {
                            name: 'product1',
                            price: 30,
                            image: '',
                            rating: 3.5,
                            promo1: 'SAVE 10% With Buy Online, Pickup in Store or Curbside Pickup!',
                            promo2: 'Sign In & Enjoy Free Shipping Over $49'
                        }
                    ]
                },
                {
                    name:'Simply Nourish',
                    product:[
                        {
                            name: 'product1',
                            price: 30,
                            image: '',
                            rating: 3.5,
                            promo1: 'SAVE 10% With Buy Online, Pickup in Store or Curbside Pickup!',
                            promo2: 'Sign In & Enjoy Free Shipping Over $49'
                        }
                    ]
                },
                {
                    name:'Dentley\'s',
                    product:[
                        {
                            name: 'product1',
                            price: 30,
                            image: '',
                            rating: 3.5,
                            promo1: 'SAVE 10% With Buy Online, Pickup in Store or Curbside Pickup!',
                            promo2: 'Sign In & Enjoy Free Shipping Over $49'
                        }
                    ]
                },
                {
                    name:'Greenies',
                    product:[
                        {
                            name: 'product1',
                            price: 30,
                            image: '',
                            rating: 3.5,
                            promo1: 'SAVE 10% With Buy Online, Pickup in Store or Curbside Pickup!',
                            promo2: 'Sign In & Enjoy Free Shipping Over $49'
                        }
                    ]
                },
                {
                    name:'Wellness',
                    product:[
                        {
                            name: 'product1',
                            price: 30,
                            image: '',
                            rating: 3.5,
                            promo1: 'SAVE 10% With Buy Online, Pickup in Store or Curbside Pickup!',
                            promo2: 'Sign In & Enjoy Free Shipping Over $49'
                        }
                    ]
                },
                {
                    name:'Merrick',
                    product:[
                        {
                            name: 'product1',
                            price: 30,
                            image: '',
                            rating: 3.5,
                            promo1: 'SAVE 10% With Buy Online, Pickup in Store or Curbside Pickup!',
                            promo2: 'Sign In & Enjoy Free Shipping Over $49'
                        }
                    ]
                },
                {
                    name:'Thrive',
                    product:[
                        {
                            name: 'product1',
                            price: 30,
                            image: '',
                            rating: 3.5,
                            promo1: 'SAVE 10% With Buy Online, Pickup in Store or Curbside Pickup!',
                            promo2: 'Sign In & Enjoy Free Shipping Over $49'
                        }
                    ]
                },
                {
                    name:'Royal Canin Veterinary Diet',
                    product:[
                        {
                            name: 'product1',
                            price: 30,
                            image: '',
                            rating: 3.5,
                            promo1: 'SAVE 10% With Buy Online, Pickup in Store or Curbside Pickup!',
                            promo2: 'Sign In & Enjoy Free Shipping Over $49'
                        }
                    ]
                },
            ]
        }
    }
}
</script>

<style>

</style>
