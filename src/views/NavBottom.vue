<template>
  <div class="flex foot">
    <div class="top">
      <div class="top-content flex">
        <div class="top-left">
          <img src="https://static.shiyanlou.com/frontend/dist/img/4a4ab3d.svg">
          <div class="top-title">
            动手做实验，轻松学IT
          </div>
          <div class="let-img">
            <div class="flex"><span class="iconfont icon-weixin"></span></div>
            <div class="flex"><span class="iconfont icon-weibo"></span></div>
          </div>
        </div>
        <div class="top-right flex">
          <div class="right-product">
            <div>公司</div>
            <ul>
              <li>关于我们</li>
              <li>联系我们</li>
              <li>加入我们</li>
            </ul>
          </div>
          <div class="right-product">
            <div>合作</div>
            <ul>
              <li>
                成为作者
              </li>
              <li>
                教师合作
              </li>
              <li>
                友情链接
              </li>
              <li>
                开发者
              </li>
            </ul>
          </div>
          <div class="right-product">
            <div>
              <div class="title" data-v-468a56d2="">
                服务
              </div>
            </div>
            <ul>
              <li>
                企业版
              </li>
              <li>

                会员服务

              </li>
              <li>
                实验报告
              </li>
              <li>
                常见问题
              </li>
              <li>
                隐私条款
              </li>
            </ul>
          </div>
          <div class="right-product">
            <div>
              学习路径
            </div>
            <ul>
              <li>
                Python学习路径
              </li>
              <li>
                Linux学习路径
              </li>
              <li>
                大数据学习路径
              </li>
              <li>

                Java学习路径

              </li>
            </ul>
          </div>

        </div>
      </div>
    </div>
    <div class="bottom flex">

        <span>Copyright @2013-2019 实验楼在线教育 |</span>
        <span>
      蜀ICP备13019762号
    </span>

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
  .foot {
    flex-direction: column;
    height: 260px;
    display: flex;
  }

  .top {
    width: 100%;
    background: #333333;
    flex: 7;

    .top-content {
      width: 1140px;
      margin: 0 auto;
      padding: 10px 20px;
      height: 100%;
      justify-content: space-between;

      .top-left {
        flex: 4;

        .top-title {
          padding: 10px 0;
          color: #0c9;
          font-size: 28px;
        }

        .let-img {
          display: flex;
          justify-content: flex-start;
          margin: 20px 0;
        }

        .let-img > div {
          width: 32px;
          height: 32px;
          background: #636469;
          border-radius: 50%;
          margin-right: 20px;
          justify-content: center;
          color: #5cb85c;
        }

        .let-img span {
          font-size: 20px;
        }

        .let-img > div:nth-child(2) {
          color: #d9534f;
        }


      }

      .top-left > img {

      }

      .top-right {
        height: 100%;
        flex: 8;
        justify-content: space-between;

        .right-product {
          width: 160px;
          height: 160px;
        }

        .right-product > div {
          color: #999;
          font-size: 18px;
          margin: 10px 0;
        }

        .right-product > ul > li {
          margin-bottom: 8px;
          color: #999;
          font-size: 14px;
        }

        .right-product > ul > li:hover {
          cursor: pointer;
          color: #f3f3f3;
        }
      }
    }
  }

  .bottom {
    width: 100%;
    background: #191919;
    flex: 2;
    justify-content: center;
    color: #a1a1a1;
    font-size: 14px;
  }
  .bottom>span:hover{
    cursor: pointer;
    color: #f3f3f3;
  }
</style>
