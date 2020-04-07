<template>
    <div class="main w-100">
        <b-card no-body class='my-3'>
            <b-row>
                <b-col class="column px-4" v-for="(service, i) in petServices" :key="i">
                    <h6 class="h3_font">{{service.name}}</h6>
                    <a class="link text-left" href="" v-for="(link, ii) in service.links" :key="ii">{{link}}</a>
                </b-col>
            </b-row>
        </b-card>
    </div>
</template>

<script>
export default {
    data(){
        return{
            petServices:[
                {name: 'Pet Services', links:['Grooming Salon', 'Training Classes', 'PetsHotel Boarding', 'Doggie Day Camp', 'Banfield Pet Hospital']},
                {name: 'Adoption', links:['Pet Adoption', 'PetSmart Charities']},
                {name: 'Learning Center', links:['Dog Care', 'Cat Care', 'Fish Care', 'Bird Care', 'Reptile Care', 'Small Pet Care']}
            ]
        }
    }
}
</script>

<style lang='scss' scoped>
.main{
    margin-left: -16px;

    .column{
        
        
        .h3_font{
            text-align: center;
            background-color: var(--primary-color);
            margin: 10px auto;
            color: #111;
            border-radius: 5px;
            display: block !important;
            padding: 5px auto;
            font-weight: bold;
            padding: 10px 0;
        }
        .link{
            text-decoration: none;
            display: block !important;
            margin-bottom: 16px;
            color: var(--secondary-color);
            padding: 5px;
            margin: 5px auto;
            transition: background-color 0.4s;

            &:hover{
                background-color: #ccc;
                border-radius: 3px;
            }
        }
    }
}
</style>
