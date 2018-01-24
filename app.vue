<template>
    <div>
        <div class="header">
            <!-- <router-link class="header-title" to="list">电商网站示例</router-link> -->
            <div class="header-title" @click="toPage">电商网站示例</div>
            <div class="header-menu">
                <router-link to="/cart" class="header-menu-cart">
                    购物车
                    <span v-if="cartList.length">{{ cartList.length }}</span>
                </router-link>
            </div>
        </div>
        <router-view></router-view>
    </div>
</template>
<script>
    export default {
        computed: {
            cartList () {
                return this.$store.state.cartList;
            }
        },
        methods:{
            toPage:function(){
                if(this.$store.state.logins){
                    this.$router.push("list");
                }else{
                    this.$router.push("login")
                }
            }
        }
    }
</script>
