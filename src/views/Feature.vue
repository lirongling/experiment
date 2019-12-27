<template>
  <div>
   <div class="feature flex">
     <div class="feature-item">
       <img src="https://static.shiyanlou.com/frontend/dist/img/5940276.gif">
       <div>
         丰富全面的计算机实验课程
       </div>
     </div>
     <div class="feature-item">
       <img src="https://static.shiyanlou.com/frontend/dist/img/8b66710.gif">
       <div>
         在线编程环境，1秒启动
       </div>
     </div>
     <div class="feature-item">
       <img src="https://static.shiyanlou.com/frontend/dist/img/9600bd2.gif">
       <div>
         每天一个项目课，丰富你的项目经验
       </div>
     </div>
     <div class="feature-item">
       <img src="https://static.shiyanlou.com/frontend/dist/img/7f21af6.gif">
       <div>
         有效学习时间，真实记录你的代码生涯
       </div>
     </div>
   </div>
  </div>

</template>

<script>
    export default {
        name: "",
        components: {},
        props: {},
        data() {
            return {}
        },
        methods: {},
        mounted() {

        },
        created() {

        },
        filters: {},
        computed: {},
        watch: {},
        directives: {}
    }
</script>

<style scoped lang="scss">
.feature{
  justify-content: space-between;
  width: 100%;
  height: 202px;
  .feature-item{
    width: 262px;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;

  }
  .feature-item>img{
    width: 160px;
  }
  .feature-item>div{
    width: 90%;
    margin: 10px auto 0;
    font-size: 16px;
    text-align: center;
    color: #666;
  }
}
</style>
