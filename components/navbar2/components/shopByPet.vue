<template>
    <div class="main w-100">
        <b-card no-body class="ml-4">
            <b-tabs card vertical>
                <b-tab :title="tab.name" v-for="(tab,i) in cols" :key="i">
                    <b-card-text class="content">
                        <b-row class="inner-row">
                            <b-col lg="6" v-for="(column1234, ii) in tab.links" :key="ii">
                                <a v-for="(piece,i4) in column1234" :key="i4" class="d-block" href="">{{piece}}</a>
                            </b-col>
                            <div :class="`tab-image_${i+1}`"></div>
                        </b-row>
                    </b-card-text>
                </b-tab>
            </b-tabs>
        </b-card>
    </div>
</template>

<script>
export default {
    data(){
        return{
            activated: false
        }
    },
props:['cols']
}
</script>

<style lang='scss' scoped>
    .main{
        margin-top: 15px;
        margin-bottom: 15px;

        @media (min-width: 992px) {
            margin-left: -30px;
            margin-top: 15px;
            margin-bottom: 15px;
        }
        .content{
            .inner-row{
                margin-bottom: 200px;
            }
            
            a{
                display: block !important;
                text-align: left;
                padding: 3px;
                margin: 3px auto;
                color: var(--secondary-color);
                text-decoration: none;
                transition: background-color 0.4s;

                @media (max-width: 991px) {
                    font-size: 0.9em;
                }
                
                &:hover{
                    background-color: #ccc;
                    border-radius: 3px;
                    color: var(--third-color);
                }
            }
            a:first-child{
                font-weight: bold;
                text-align: center;
                background-color: var(--primary-color);
                margin-bottom: 10px;
                color: #111;
                border-radius: 5px;
                display: block !important;
                padding: 10px 0;

                @media (max-width: 991px) {
                    font-size: 0.9em;
                }
            }

            @for $i from 1 to 7{
                
                .tab-image_#{$i}{
                    background: url('../../../assets/img/images/#{$i}.jpeg');
                    background-repeat: no-repeat;
                    background-size: contain;
                    position: absolute;
                    z-index: 17;
                    bottom: -32px;
                    right: 50px;
                    height: 200px;
                    width: 200px;

                    @media (max-width: 991px) {
                        height: 100px;
                        width: 100px;
                        bottom: -16px;
                    }
                }
            }
        }
    }

</style>
