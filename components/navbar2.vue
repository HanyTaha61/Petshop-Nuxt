<template>
<div class="outer_container" >
    <b-container>
        <b-navbar>
            <b-navbar-nav>
                <!-- Navbar dropdowns -->
                <b-nav-item-dropdown text="Lang" right>
                    <b-dropdown-item href="#">EN</b-dropdown-item>
                    <b-dropdown-item href="#">ES</b-dropdown-item>
                    <b-dropdown-item href="#">RU</b-dropdown-item>
                    <b-dropdown-item href="#">FA</b-dropdown-item>
                </b-nav-item-dropdown>

                <b-nav-item-dropdown text="User" right>
                    <b-dropdown-item href="#">Account</b-dropdown-item>
                    <b-dropdown-item href="#">Settings</b-dropdown-item>
                </b-nav-item-dropdown>
            </b-navbar-nav>
        </b-navbar>
    </b-container>
</div>
</template>

<script>
export default {
    head(){
        return{
            
        }
    }
}
</script>

<style src='./navbar2.scss' scoped lang='scss'/>


