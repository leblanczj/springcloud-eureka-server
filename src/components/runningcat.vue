<template>

    <!--右上角查看规则--弹窗开关-->
    <div class="righttop">
        <div><a class="rule" href="javascript:" @click="showpopup">Play</a></div>
        <div v-show="popup">
            <!--这里是要展示的内容层-->
            <div class="login" ref="login" >
                <div style="height: 100px;padding-top: 50%;">
                    <button v-on:click="closepopup">喵</button>
                </div>
            </div>
            <!--这里是半透明背景层-->
            <div class="over"></div>
        </div>
    </div>

</template>

    <script>

       export default {
           data(){
               return {
                   popup: 0,
                   top:0,
                   left:0
               };
           },
           methods:{
               showpopup(){
                   this.popup = 1;
               },
               closepopup(){
                   //this.popup = 0;
                   this.top = parseInt(Math.round(Math.random()*95) )+'%';
                   this.left =parseInt(Math.round(Math.random()*95) )+'%';
                   this.$refs.login.style.setProperty("--top",this.top);
                   this.$refs.login.style.setProperty("--left",this.left);
                   },
           }
       };
</script>

<style>
    .rule {
        position: absolute;
        width:auto;
        height: auto;
        top: 50%;
        right: 50%;
        background: #a0cfff;
    }
    .login {
        --top:50%;
        --left:50%;
        position: fixed;
        font-size: 24px;
        height: 100px;
        width: 100px;
        background-color: #fbc4c4;
        border-radius: 0.25rem;
        left: var(--top);
        top: var(--left);
        transform: translate(-50%, -50%);
        z-index: 1000;
    }
    .over {
        position: fixed;
        width: 100%;
        height: 100%;
        opacity: 0.7;
    filter: alpha(opacity=70);
        top:0;
        left: 0;
        z-index: 999;
        background-color: #111111;
    }
</style>
