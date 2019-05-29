<template>
	<div class="home_h">
		 <header class="m_header">
                <div class="m_header_box" id="my_search">
                    <a href="#" class="icon_logo"></a>
                    <form action="#">
                        <span class="icon_search"></span>
                        <input type="search" class="search" placeholder="点击搜索" @click="goSearch($event)">
                    </form>
                    <div class="logo_btn" v-if='this.$store.getters.getUserInfo.user_name'>
                        {{this.$store.getters.getUserInfo.user_name}}
                        <span >退出</span>
                    </div>
                    <router-link to="/login" class="logo_btn" v-else>登录</router-link>
                </div>
            </header>
	</div>
</template>
<script>
    export default{
        created(){
            // console.log(this.$store)
        },
        methods:{
            goSearch(event){
                this.$router.push('/search');
                window.event? window.event.returnValue = false : event.preventDefault();
            }
        }
    }
</script>