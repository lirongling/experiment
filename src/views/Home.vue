<template>
  <div class="home">
    <!--    吸顶导航栏-->
    <div v-if="nav0Visible" class="mounting">
      <div  class="nav0">
        <div class="nav0-left">
          <div class="nav-log"><img src="https://static.shiyanlou.com/frontend/dist/img/9f43b00.svg" height="50"></div>
        </div>
        <div class="nav0-center">
          <div class="nav1-center">
            <ul>
              <li><span class="nav1-center-title">路径</span></li>
              <li><span class="nav1-center-title">路径</span></li>
              <li><span class="nav1-center-title">楼+</span></li>
              <li><span class="nav1-center-title">会员</span>
                <img src="https://static.shiyanlou.com/frontend/dist/img/02a4001.svg"
                     class="nav1-center-hot"></li>
              <li class="nav1-center-home">
                <span class="nav1-center-title">社区</span>
                <span class="nav1-center-img iconfont icon-xiajiantou"></span>
                <ul class="nav1-center-list">
                  <li>讨论</li>
                  <li>数据库</li>
                  <li>直播</li>
                  <li>比赛</li>
                </ul>
              </li>
            </ul>
          </div>
        </div>
        <div class="nav0-right">
          <div class="nav-right-title">
            <span>企业版</span>
            <span></span>
            <span>学校版</span>
          </div>
          <input type="text" placeholder="搜索 课程/问答" class="nav1-right-ip00">
          <div class="nav-right00">
            <span class="nav-right-input">注册</span>
            <span class="nav-right-register">登录</span>
          </div>

        </div>
      </div>
      <Back-top :height="100" :bottom="100">
        <div class="top000">返回顶端</div>
      </Back-top>
    </div>

    <!--    广告栏-->
    <div v-if="advertisementFlag" class="advertisement">
      <a href="#" class="advertisement-img">
        <img
            src="https://dn-simplecloud.shiyanlou.com/course/1576079545881_%E5%8F%8C12%E6%9D%A1%E5%B9%85%E6%AD%A3%E5%BC%8F.png"
            width="100%">
      </a>
      <span class="advertisement-bt iconfont icon-cha" @click="advertisementBt"></span>
    </div>
    <!--    顶部导航-->
    <div class="top">
      <div class="nav">
        <div class="nav-left">
          <div class="nav-log"><img src="https://static.shiyanlou.com/frontend/dist/img/9f43b00.svg" height="50"></div>
          <div class="nav-title">
            做实验，学编程
          </div>
        </div>
        <div class="nav-center"></div>
        <div class="nav-right">
          <div class="nav-right-title">
            <span>企业版</span>
            <span></span>
            <span>学校版</span>
          </div>
          <span class="nav-right-input">注册</span>
          <span class="nav-right-register">登录</span>
        </div>
      </div>
    </div>
    <div class="nav1">
      <div class="nav1-left">
        <span class="nav1-left-ico iconfont icon-qiapianxuanze-"></span>
        <span class="nav1-left-text ">全部课程</span>
      </div>
      <div class="nav1-center">
        <ul>
          <li><span class="nav1-center-title">路径</span></li>
          <li><span class="nav1-center-title">路径</span></li>
          <li><span class="nav1-center-title">楼+</span></li>
          <li><span class="nav1-center-title">会员</span>
            <img src="https://static.shiyanlou.com/frontend/dist/img/02a4001.svg"
                 class="nav1-center-hot"></li>
          <li class="nav1-center-home">
            <span class="nav1-center-title">社区</span>
            <span class="nav1-center-img iconfont icon-xiajiantou"></span>
            <ul class="nav1-center-list">
              <li>讨论</li>
              <li>数据库</li>
              <li>直播</li>
              <li>比赛</li>
            </ul>
          </li>
        </ul>
      </div>
      <div class="nav1-right">
        <input type="text" placeholder="搜索 课程/问答" class="nav1-right-ip">
      </div>
    </div>

    <div class="wheel" ref="wheels" :style="{background:ragb}">
      <div class="wheel-center">
        <el-carousel height="515px" @change="chang">
          <el-carousel-item v-for="(item,index) in pictures" :key="index">
            <img :src="item.picture_url">
          </el-carousel-item>
        </el-carousel>
        <div class="wheel-list">
          <ul>
            <li v-for="(item,index) in categories" :key="index">
              <ul class="wheel-list-title">
                <li>{{item.name}}</li>
                <li @click="jump(item.tags[0])">{{item.tags[0].name}}</li>
                <li @click="jump(item.tags[1])">{{item.tags[1].name}}</li>
              </ul>
              <div class="wheel-list-list">
                <div class="wheel-list-list-top">
                  <div class="categories-title">
                    <span> {{item.name}}</span>
                  </div>
                  <div class="categories-text flex">
                    <span class="categories-text___">
                       <el-divider direction="vertical" style="background: #0a0f13"></el-divider>
                    </span>
                    <div v-for="(item0,index) in item.tags" :key="index" class="flex">
                      <div class="categories-item flex" @click="jump(item0)">{{item0.name}}</div>
                      <span class="categories-text___">
                       <el-divider direction="vertical" style="background: #0a0f13"></el-divider>
                    </span>
                    </div>

                  </div>
                </div>
                <div class="wheel-list-list-top">
                  <div class="categories-title">
                    <span> 课程推荐</span>
                  </div>
                  <div class="categories-text flex">
                    <span class="categories-text___">
                       <el-divider direction="vertical" style="background: #0a0f13"></el-divider>
                    </span>
                    <div v-for="(item0,index) in item.recommend_courses" :key="index" class="flex">
                      <div class="categories-item flex" @click="jump(item0)">{{item0.name}}</div>
                      <span class="categories-text___">
                       <el-divider direction="vertical" style="background: #0a0f13"></el-divider>
                    </span>
                    </div>

                  </div>
                </div>
              </div>
            </li>
          </ul>
          <div class="wheel-bt">
            经营专区
          </div>
        </div>

      </div>

    </div>
    <div class="curriculum">
      <Curriculum></Curriculum>
    </div>
    <div class="home-feature">
      <Feature></Feature>
    </div>
    <div class="nav-bottom">
      <NavBottom></NavBottom>
    </div>

  </div>
</template>

<script>
    import Wheel from '../views/Wheel'
    import Curriculum from '../views/Curriculum'
    import Feature from '../views/Feature'
    import NavBottom from '../views/NavBottom'

    export default {
        name: "home",
        components: {
            Wheel,
            Curriculum,
            Feature,
            NavBottom
        },
        props: {},
        data() {
            return {
                advertisementFlag: true,
                nav0Visible: false,
                offsetTop1: 0,
                categories: [],
                pictures: [],
                ragb: ''


            }
        },
        mounted() {

            window.addEventListener('scroll', this.initHeight);
            this.$nextTick(() => {
                //获取对象相对于版面或由 offsetTop 属性指定的父坐标的计算顶端位置
                let a = this.$refs.wheels;
                this.offsetTop1 = a.offsetTop;
            });
            this.getCategories();
            this.getPictures()
        },
        methods: {
            chang(index, oldIndex) {
                setTimeout(()=>{
                    this.ragb = this.pictures[index].background_color;
                    },357)


            },
            // 关闭广告
            advertisementBt() {
                this.advertisementFlag = false
            },
            initHeight() {
                // 设置或获取位于对象最顶端和窗口中可见内容的最顶端之间的距离 (被卷曲的高度)
                let scrollTop = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop;
                //如果被卷曲的高度大于吸顶元素到顶端位置 的距离
                this.nav0Visible = scrollTop > this.offsetTop1 ? true : false;
            },
            getCategories() {
                this.$axios
                    .req("categories")
                    .then(res => {
                        this.categories = res
                    })
                    .catch(err => {
                        console.log(err);
                    });
            },
            jump(items) {
                window.open('https://www.shiyanlou.com' + items.html_url);
            },
            getPictures() {
                this.$axios
                    .req("banner-pictures")
                    .then(res => {
                        this.pictures = res
                        this.ragb = this.pictures[0].background_color;
                    })
                    .catch(err => {
                        console.log(err);
                    });
            },

        },
        //回调中移除监听
        destroyed() {
            window.removeEventListener('scroll', this.handleScroll)
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
  .top000{
    padding: 10px;
    background: rgba(0, 153, 229, .7);
    color: #fff;
    text-align: center;
    border-radius: 2px;
  }
  .mounting{
    top: 0;
    background: white;
    width: 100%;
    height: 63px;
    position: fixed;
    z-index: 9999;
  }
  .nav0 {
    min-width: 1080px;
    width: 1140px;
    height: 63px;
    position: fixed;
    z-index: 9999;
    left: 50%;
    transform: translateX(-50%);
    top: 0;
    background: white;

    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .nav0-left {
    width: 40px;
    height: 100%;
  }


  .nav0-center {
    width: 330px;
    height: 100%;
  }

  .nav0-right {
    width: 500px;
    height: 100%;
    display: flex;
    justify-content: space-between;
  }

  .home {
    background-color: #F9F9F9 !important;
  }

  .advertisement {
    width: 100%;
    height: auto;
    position: relative;
  }

  .advertisement-img {
    margin: 0 auto;
    height: auto;
  }

  .advertisement-bt {
    position: absolute;
    right: 10%;
    top: 50%;
    transform: translateY(-50%);
    color: #1b2731;

  }

  .advertisement-bt:hover {
    cursor: pointer;
    color: #0a0f13;
  }

  .top {
    width: 100%;
    height: 56px;
    margin: 0 auto;
  }

  .nav {
    min-width: 1080px;
    width: 1140px;
    height: 100%;

    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .nav-left {
    width: 260px;
    height: 100%;

    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .nav-title {
    font-size: 18px;
  }

  .nav-center {
    width: 550px;
    height: 100%;

  }

  .nav-right {
    width: 260px;
    height: 100%;

    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .nav-right00 {
    width:120px;
    height: 100%;

    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .nav-right-title {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .nav-right-title span:nth-child(1):hover, .nav-right-title span:nth-child(3):hover {
    color: #08bf91;
    cursor: pointer;
  }

  .nav-right-title span:nth-child(2) {
    display: block;
    height: 16px;
    width: 1px;
    margin: 0 5px 0 5px;
    background: #2f2e31;
  }

  .nav-right-input {
    color: #08bf91;
  }

  .nav-right-input:hover, .nav-right-register:hover {
    color: #044f3c;
    cursor: pointer;
  }

  .nav-right-register {
    width: 82px;
    height: 47px;
    line-height: 47px;
    text-align: center;
    background: #08bf91;
  }

  .nav1 {
    min-width: 1080px;
    width: 1140px;
    height: 63px;
    background: white;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .nav1-left {
    width: 260px;
    height: 100%;
    background: #08bf91;
    display: flex;
    justify-content: left;
    align-items: center;
  }

  .nav1-left:hover {
    cursor: pointer;
  }

  .nav1-left-ico {
    margin: 0 10px 0 10px;
    size: 20px;
    width: 16px;
    height: 16px;
    font-size: 16px;
    color: white;
  }

  .nav1-left-text {
    color: white;
  }

  .nav1-center {
    width: 540px;
    height: 100%;
  }


  .nav1-center > ul {
    display: flex;
    justify-content: left;
    align-items: center;
    height: 100%;
  }

  .nav1-center > ul > li {
    margin-right: 25px;
    position: relative;
    height: 100%;
    line-height: 63px;
  }

  .nav1-center-title:hover {
    cursor: pointer;
    color: #08bf91;

  }

  .nav1-center-hot {
    position: relative;
    top: -10px;
    left: 11px;
  }

  .nav1-center-home:hover > .nav1-center-list {
    visibility: visible;
  }

  .nav1-center-list {
    z-index: 9999;
    visibility: hidden;
    position: absolute;
    top: 63px;
    width: 150px;
    background: white;
    border-radius: 0 0 8px 8px;
    box-shadow: 0 15px 16px 0 rgba(0, 0, 0, .18);
    height: 200px !important;
    display: flex;
    flex-direction: column;

  }

  .nav1-center-list li {
    text-align: center;
    flex: 1;
    line-height: 50px;
    width: 100%;
    margin: 0 auto;
  }

  .nav1-center-list li:nth-child(4) {
    border-radius: 0 0 8px 8px;
  }

  .nav1-center-list li:hover {
    background: #f5f5f5;
    cursor: pointer;
  }

  .nav1-right {
    width: 300px;
    height: 100%;
    position: relative;
  }

  .nav1-right-ip {
    width: 197px;
    height: 31px;
    border-radius: 5px;
    padding-left: 10px;
    position: absolute;
    outline: none;
    top: 50%;
    right: 10%;
    transform: translateY(-50%);


  }

  .nav1-right-ip:focus {
    border: #08bf91 1px solid !important;
  }
  .nav1-right-ip00 {
    width: 197px;
    height: 31px;
    border-radius: 5px;
    padding-left: 10px;
    position: absolute;
    outline: none;
    top: 50%;
    right: 12%;
    transform: translateY(-50%);


  }

  .nav1-right-ip00:focus {
    border: #08bf91 1px solid !important;
  }

  .wheel {
    height: 515px;
    width: 100%;
  }

  .wheel-center {
    min-width: 1080px;
    width: 1140px;
    height: 100%;
    margin: 0 auto;
    /*display: flex;*/
    /*justify-content: space-between;*/

  }

  .wheel-list {
    position: relative;
    top: -515px;
    z-index: 999;
    width: 260px;
    height: 100%;
    background: rgba(0, 0, 0, .18);
    color: #ececec;

  }

  .wheel-list > ul {
    width: 100%;
    height: 90%;
    margin: 0 auto;
    display: flex;
    align-items: center;
    flex-direction: column;
    position: relative;

  }

  .wheel-list > ul > li {
    width: 100%;

  }

  .wheel-list-list {
    display: none;
    position: absolute;
    left: 260px;
    margin-top: -57px;
    width: 480px;
    height: 300px;
    box-shadow: 2px 0 4px 0 rgba(0, 0, 0, .2);
    background: #fff;
  }

  .wheel-list-list-top {
    width: 90%;
    margin: 20px auto;
    text-align: left;
  }

  .categories-title {
    color: #2f2e31;

  }

  .categories-title > span {
    background: #F9F9F9;
    padding: 5px 12px;
    font-size: 14px;

  }

  .categories-text {
    margin: 20px;
  }

  .categories-item {
    height: 30px;
    font-size: 13px;

  }

  .categories-item:hover {
    color: #08bf91;
  }

  .wheel-list > ul > li:hover {
    cursor: pointer;
    background: #F9F9F9;
    color: #494949;

  }


  .wheel-list > ul > li:nth-child(5) > .wheel-list-list, .wheel-list > ul > li:nth-child(6) > .wheel-list-list, .wheel-list > ul > li:nth-child(7) > .wheel-list-list, .wheel-list > ul > li:nth-child(8) > .wheel-list-list {
    bottom: -52px;
  }

  .wheel-list > ul > li:hover > .wheel-list-list {
    display: block;

  }

  .wheel-list-title {
    font-size: 14px;
    display: flex;
    width: 90%;
    height: 40px;
    margin: 8px auto;
    border-bottom: #F9F9F9 1px solid;
    align-items: center;
    line-height: 40px;
  }

  .wheel-list-title > li {
    margin-right: 10px;
  }

  .wheel-list-title > li:hover {
    color: #08bf91;
  }

  .wheel-bt {
    width: 88px;
    height: 26px;
    line-height: 26px;
    text-align: center;
    border-radius: 10px;
    margin: 5px auto;
    border: #F9F9F9 1px solid;


  }

  .wheel-img {
    width: 880px;
    height: 100%;
  }

  .curriculum {
    min-width: 1080px;
    width: 1140px;
    margin: 30px auto;
  }
  .home-feature{
    min-width: 1080px;
    width: 1140px;
    margin: 40px auto;
  }
  .nav-bottom{
    height: 260px;
    width: 100%;
    margin-top: 40px;
  }


</style>

