<template>
    <div class="login-html" id="login-html">
        <div class="login-header">
            <div>
                <input type="text" class="login-text" placeholder="请输入账号" v-model="text">
            </div>
            <div> 
                <input type="password" class="login-password" placeholder="请输入密码" v-model="psd">
            </div>
            <button @click="handlelogin" class="login-button">
                登陆
            </button>
        </div>
    </div>
</template>
<script>
export default {
    data:function(){
        return {
            text:'',
            psd:""
        }
    },
    mounted () {
        let windowH = window.innerHeight;
        document.getElementById("login-html").style.height = (windowH - 48) + "px";
    },
    methods: {
        handlelogin:function(){  
            // 登陆
            if(this.text != "" && this.psd != ""){
                setTimeout(() => {
                    consol.log("验证成功，可以登录");
                    resolve();
                },1000);
                this.$router.push("list");
            }else{
                alert("请输入正确的账号密码")
            }
        }
    }
}
</script>
<style scoped>
    .login-html{
        width:100%;
        background:url("http://bpic.588ku.com/back_pic/04/46/88/095857a5447a645.jpg")  center  center;
        color:#000;
        display:flex;
        justify-content:center;
        background-size: cover;
        align-items:center;
    }
    .login-header{
        width:20%;
        height:240px;
        display:flex;
        flex-direction:column;
        justify-content:space-around;
    }
    .login-button{
        background:#fff;
        color:rgb(26, 160, 77);
        border:0;
        cursor:pointer;
    }
    .login-text,.login-password,.login-button{
        width:100%;
        height:30px;
        text-align:center;
        border:1px solid #ccc;
        border-radius:6px;
        background:#fff;
    }
</style>


