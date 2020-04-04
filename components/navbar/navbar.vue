<template>
    <div class="upper_navbar">
        <div class="container">
            <b-navbar toggleable="lg" type="dark">
                <b-navbar-brand href="#">
                    <b-img src="../../assets/img/logo.png"/>
                </b-navbar-brand>

                <b-navbar-toggle target="nav-collapse" class="hamburger">
                    <span></span><span></span><span></span>
                </b-navbar-toggle>

                <b-collapse id="nav-collapse" is-nav>

                <!-- Right aligned nav items -->
                <b-navbar-nav class="mx-auto search_bar">
                    <b-nav-form>
                        <b-form-input size="sm" class="mr-sm-2 search_input" placeholder="Search"></b-form-input>
                        <b-button size="sm" class="my-2 my-sm-0 search" type="submit">
                            Search
                            <i class="fas fa-search"></i>
                        </b-button>
                    </b-nav-form>
                    <a href="#">
                        <i id="cart" class="fas fa-shopping-cart fa-2x text-danger my-1 ml-lg-5"></i>
                        <b-tooltip target="cart" triggers="hover" placement='right'>Check Your Cart</b-tooltip>
                    </a>
                    </b-navbar-nav>
                    <b-navbar-nav class="login_menu">
                        <!-- <button @click="removeClass" id="rem1" class="class1">btn1</button> -->
                        <button v-click-outside="hide" id="dropdown_btn" class="btn menu my-1" @click="toggle">
                            <i class="fas fa-user"></i>
                            <span class="d-none d-lg-inline-block">
                                Login / Signin
                            </span>
                            <span id="caret" class="caret_up"></span>
                        </button>
                        <transition-group name="slide">
                            <div key="login_body" class="login_body" v-if="opened">
                                <p class="title">Log In</p>
                                <input type="text" placeholder="username or email" class="w-100 username1" required>
                                <input type="password" placeholder="password" class="w-100 password1" required>
                                <input type="submit" class="btn w-75 d-block mx-auto login1" value="Log In">
                                <p class="other_login text-center my-2 h6">or login with</p>
                                <div class="other_login_icons w-75 mx-auto">
                                    <a href=""><img src="../../assets/img/facebook.png" alt="facebook"></a>
                                    <a href=""><img src="../../assets/img/google.png" alt="google"></a>
                                    <a href=""><img src="../../assets/img/linkedin.png" alt="linkedin"></a>
                                </div>
                                <p class="other_login text-center mt-5 h6">Don't Have Account?</p>
                                <input type="submit" class="btn btn-primary w-75 d-block mx-auto mb-3 sign_up" value="Sign Up">
                            </div>
                        </transition-group>
                    </b-navbar-nav>
                </b-collapse>
            </b-navbar>
        </div>
    </div>
</template>

<script>
import ClickOutside from 'vue-click-outside'

export default {
    data(){
        return{
            opened: false
        }
}, 
    directives: {ClickOutside},
    methods:{
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
    }      
  },
 
  mounted () {
    // prevent click outside event with popupItem.
    this.popupItem = this.$el
  }
}
</script>

<style src='./navbar.scss' scoped lang='scss'/>

<style>
@import url('https://fonts.googleapis.com/css?family=Josefin+Sans&display=swap');

    .class1{background-color: #de3;}

    .slide-enter-active, .slide-leave-active {
    transition: opacity .5s;
    }
    .slide-enter, .slide-leave-to /* .slide-leave-active below version 2.1.8 */ {
    opacity: 0;
    }
</style>
