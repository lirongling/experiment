<template>
  <div class="curriculum00">
    <!--    实战课程-->
    <div class="top flex">
      <div class="top-title flex">
        <div class="top-name">楼+ 实战课程</div>
        <el-divider direction="vertical"></el-divider>
        <div class="top-text">定期开班，导师助教全程辅导，最快最优成长</div>
      </div>
      <div class="top-more">
        更多>
      </div>
    </div>
    <div class="curriculum flex">
      <div class="curriculum-item" v-for="(louplu,index) in louplus" :key="index" v-if="index<4">
        <img :src="louplu.picture_url" class="img">
        <div class="curriculum-title">
          {{louplu.title}}
        </div>
        <div class="curriculum-time">最近班次:<span>{{louplu.open_time}}</span></div>
      </div>
    </div>
    <!--    精品课程-->
    <div class="top flex" v-if="courses[0]">
      <div class="top-title flex">
        <div class="top-name">
          {{courses[0].classify_name}}
        </div>
        <el-divider direction="vertical"></el-divider>
        <div class="top-text">
          {{courses[0].description}}
        </div>
      </div>
      <div class="top-more">
        更多>
      </div>
    </div>
    <div class="boutique flex" v-if="courses[0]">
      <div class="boutique-img">
        <img :src="courses[0].recommend_course.picture_url">
      </div>
      <div class="boutique-item" v-for="(course,index) in  courses[0].courses" :key="index">
        <img :src="course.picture_url">
        <div class="boutique0">
          <div class="boutique-title">
            {{course.name}}
          </div>
          <div class="boutique-text">
            {{course.description}}
          </div>
        </div>
        <div class="boutique-bottom">
          <div class="bottom-text flex">
            <div class="el-icon-s-help"><span>{{course.students_count}}</span></div>
            <div class="boutique-bottom-right">
              <div v-if="course.fee_type==='bootcamp'" class="bootcamp">训练营</div>
              <div v-else-if="course.fee_type==='member'" class="bootcamp member ">会员</div>
            </div>
          </div>

        </div>
        <div v-if="course.label==='倍受好评'" class="label">
          <div>
          </div>
          <div>倍受好评</div>
        </div>
        <div v-else-if="course.online_type==='coming_soon'" class="label">
          <div>
          </div>
          <div>即将上线</div>
        </div>

      </div>
    </div>
    <!--    近日课程-->
    <div class="top flex" v-if="courses[1]">
      <div class="top-title flex">
        <div class="top-name">
          {{courses[1].classify_name}}
        </div>
        <el-divider direction="vertical"></el-divider>
        <div class="top-text">
          {{courses[1].description}}
        </div>
      </div>
      <div class="top-more">
        更多>
      </div>
    </div>
    <div class="boutique flex" v-if="courses[0]">
      <el-carousel indicator-position="outside" class="carousel" :autoplay="false" :indicator-position="none">
        <el-carousel-item v-for="(item,index0) in  classify" :key="index0" class="carousel flex">
          <div class="boutique-item shaw" v-for="(course,index) in  item" :key="index">
            <img :src="course.picture_url">
            <div class="boutique0">
              <div class="boutique-title">
                {{course.name}}
              </div>
              <div class="boutique-text">
                {{course.description}}
              </div>
            </div>
            <div class="boutique-bottom">
              <div class="bottom-text flex">
                <div class="el-icon-s-help"><span>{{course.students_count}}</span></div>
                <div class="boutique-bottom-right">
                  <div v-if="course.fee_type==='bootcamp'" class="bootcamp">训练营</div>
                  <div v-else-if="course.fee_type==='member'" class="bootcamp member ">会员</div>
                </div>
              </div>
            </div>
            <div v-if="course.label==='倍受好评'" class="label">
              <div>
              </div>
              <div>倍受好评</div>
            </div>
            <div v-else-if="course.online_type==='coming_soon'" class="label1 ">
              <div>
              </div>
              <div>即将上线</div>
            </div>

          </div>
        </el-carousel-item>
      </el-carousel>
    </div>
    <!--    基本功-->
    <div class="top flex" v-if="courses[2]">
      <div class="top-title flex">
        <div class="top-name">
          {{courses[2].classify_name}}
        </div>
        <el-divider direction="vertical"></el-divider>
        <div class="top-text">
          {{courses[2].description}}
        </div>
      </div>
      <div class="top-more">
        更多>
      </div>
    </div>
    <div class="boutique flex" v-if="courses[2]">
      <div class="boutique-item" v-for="(course,index) in  courses[2].courses" :key="index">
        <img :src="course.picture_url">
        <div class="boutique0">
          <div class="boutique-title">
            {{course.name}}
          </div>
          <div class="boutique-text">
            {{course.description}}
          </div>
        </div>
        <div class="boutique-bottom">
          <div class="bottom-text flex">
            <div class="el-icon-s-help"><span>{{course.students_count}}</span></div>
            <div class="boutique-bottom-right">
              <div v-if="course.fee_type==='bootcamp'" class="bootcamp">训练营</div>
              <div v-else-if="course.fee_type==='member'" class="bootcamp member ">会员</div>
            </div>
          </div>
        </div>
        <div v-if="course.label==='倍受好评'" class="label">
          <div>
          </div>
          <div>倍受好评</div>
        </div>
        <div v-else-if="course.online_type==='coming_soon'" class="label">
          <div>
          </div>
          <div>即将上线</div>
        </div>

      </div>
    </div>
    <!--    后端开发-->
    <div class="top flex" v-if="courses[3]">
      <div class="top-title flex">
        <div class="top-name">
          {{courses[3].classify_name}}
        </div>
        <el-divider direction="vertical"></el-divider>
        <div class="top-text">
          {{courses[3].description}}
        </div>
      </div>
      <div class="top-more">
        更多>
      </div>
    </div>
    <div class=" flex boutique1">
      <div class="boutique flex" v-if="courses[3]">
        <div class="boutique-left">
          <img :src="courses[3].recommend_course.picture_url">
        </div>
        <div class="right">
          <div class="boutique-item boutique-item1" v-for="(course,index) in  courses[0].courses" :key="index">
            <img :src="course.picture_url">
            <div class="boutique0">
              <div class="boutique-title">
                {{course.name}}
              </div>
              <div class="boutique-text">
                {{course.description}}
              </div>
            </div>
            <div class="boutique-bottom">
              <div class="bottom-text flex">
                <div class="el-icon-s-help"><span>{{course.students_count}}</span></div>
                <div class="boutique-bottom-right">
                  <div v-if="course.fee_type==='bootcamp'" class="bootcamp">训练营</div>
                  <div v-else-if="course.fee_type==='member'" class="bootcamp member ">会员</div>
                </div>
              </div>
            </div>
            <div v-if="course.label==='倍受好评'" class="label">
              <div>
              </div>
              <div>倍受好评</div>
            </div>
            <div v-else-if="course.online_type==='coming_soon'" class="label">
              <div>
              </div>
              <div>即将上线</div>
            </div>

          </div>
        </div>

      </div>
    </div>
    <!--    云计算-->
    <div class="top flex" v-if="courses[4]">
      <div class="top-title flex">
        <div class="top-name">
          {{courses[4].classify_name}}
        </div>
        <el-divider direction="vertical"></el-divider>
        <div class="top-text">
          {{courses[4].description}}
        </div>
      </div>
      <div class="top-more">
        更多>
      </div>
    </div>
    <div class=" flex boutique1">
      <div class="boutique flex" v-if="courses[3]">
        <div class="boutique-left">
          <img :src="courses[4].recommend_course.picture_url">
        </div>
        <div class="right">
          <div class="boutique-item boutique-item1" v-for="(course,index) in  courses[4].courses" :key="index">
            <img :src="course.picture_url">
            <div class="boutique0">
              <div class="boutique-title">
                {{course.name}}
              </div>
              <div class="boutique-text">
                {{course.description}}
              </div>
            </div>
            <div class="boutique-bottom">
              <div class="bottom-text flex">
                <div class="el-icon-s-help"><span>{{course.students_count}}</span></div>
                <div class="boutique-bottom-right">
                  <div v-if="course.fee_type==='bootcamp'" class="bootcamp">训练营</div>
                  <div v-else-if="course.fee_type==='member'" class="bootcamp member ">会员</div>
                </div>
              </div>
            </div>
            <div v-if="course.label==='倍受好评'" class="label">
              <div>
              </div>
              <div>倍受好评</div>
            </div>
            <div v-else-if="course.online_type==='coming_soon'" class="label">
              <div>
              </div>
              <div>即将上线</div>
            </div>

          </div>
        </div>

      </div>
    </div>
    <!--    训练营-->
    <div class="top flex">
      <div class="top-title flex">
        <div class="top-name">
          训练营强化
        </div>
        <el-divider direction="vertical"></el-divider>
        <div class="top-text">
          专注实战的完整项目，在实战中融会贯通
        </div>
      </div>
      <div class="top-more">
        更多>
      </div>
    </div>
    <div v-for="(bootcamp,index) in bootcamps" :key="index">
      <div class="bootcamps flex">
        <img :src="bootcamp.picture_url">
        <div class="bootcamps-right">
          <div>{{bootcamp.name}}</div>
          <div>{{bootcamp.description}}</div>
          <div class="bootcamps-bottom">
            <div class="flex">{{bootcamp.tags[0]}}</div>
            <div>
              <el-button type="warning">查看详情</el-button>
            </div>
          </div>

        </div>
      </div>
    </div>
    <!--    学习路径-->
    <div class="top flex">
      <div class="top-title flex">
        <div class="top-name">

          学习路径

        </div>
        <el-divider direction="vertical"></el-divider>
        <div class="top-text">

          精准而系统的学习路径，从0到大牛

        </div>
      </div>
      <div class="top-more">
        更多>
      </div>
    </div>
    <div class="path-bottom" >
      <div class="path-item" v-for="(path,index) in paths" :key="index">
        <img :src="path.image">
        <div class="path-title">{{path.name}}</div>
        <div class="path-text">{{path.courses_count}}课程</div>
        <img v-if="path.is_hot" class="path-ico" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACwAAAAVCAYAAAA98QxkAAAAAXNSR0IArs4c6QAAAp9JREFUSA3NlrtLHFEUxn8zGhGNCoqKj2ItfBWKgo1gZy0JurilGEiVP0ASQmQD2dhpilQpLCKiYpNCGxtBsLAQUXQVLAK+wUKMgs/dnDN3d91VY2QdYQ7M3nvPnPvNt98958xYiEWj0aCOXjfLsvozhexrIfqJyUlv8+3qUmHJFJa/ODv7zeamj+Vlb5P2+7FF5ijZ2R8IBP54m61hZ8dIjlNWdkJdnec5O4RF5Yio/FFUPvE647jCyvMnVVXncnmasxadY6LypdPeAoEQAwMv4/57x6YmuLiAtbWb2+3tsLoK+/vGV1EBbW1QVAS7uzAzA6enUF4OGnvbRkfh+vq29846WWG9+YP6+msqK+8EpjhqasDnS3HR0gKFhcbX3Ax9fXBwAPPzJjYUgvx8OJGs0z+2tQWtrWau60gkFe8fqxTCovIZGRlf6e4WKdI0y4LeXhgZgdlZWFqCoSFYXwfppRwfw+IiTgs9PzdzXUuPfYylEHY22PZ3GhosSksf3q9H29h4c+XlmfjiYtC5Ek02JVVbm+xJa57I4cTuSOQdKytR5zgTznsmmjbJx1hQYIKU7NGRyfHkbYeHkJWV7ElrnkJYii6by8v3TEzk/hdtYQGmp2/CNGfVtOhKSkCLbmfH+PRXC1WL74l2OyXeEg5nsL2dPqx2grk56OgAOwavLyTtGFNT6ePGdiYUFnVfSKvqZ3z84Zb2mEcOD0NPDwwOwtUV8lIyRRgOP2b3gzFS0saE8Bs2Nr4RDD6dcBxUO0ZOjum/cV+6Y2cn+P2fnTMTsrZ8sX1hbMw9skpMW5WmiIsWz+EAe3u5orCL0M8DZYu6lqgbktyNNdLneZBbqFp0r6QofFRX41xuIbuNo29JMafoROV+t/GfA08+HYJ/ARwRyXMvBnEHAAAAAElFTkSuQmCC">
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
            return {
                louplus: [],
                courses: [],
                none: 'none',
                classify: [],
                bootcamps: [],
                paths:[]
            }
        },
        methods: {
            getLouplus() {
                this.$axios
                    .req("louplus")
                    .then(res => {
                        this.louplus = res
                    })
                    .catch(err => {
                        console.log(err);
                    });
            },
            getCourses() {
                this.$axios
                    .req("classfication-courses")
                    .then(res => {
                        this.courses = res
                        for (let i = 0; i < this.courses[1].courses.length; i += 4) {
                            this.classify.push(this.courses[1].courses.slice(i, i + 4));
                        }
                    })
                    .catch(err => {
                        console.log(err);
                    });
            },
            getBootcamps() {
                this.$axios
                    .req("bootcamps")
                    .then(res => {
                        this.bootcamps = res
                    })
                    .catch(err => {
                        console.log(err);
                    });
            },
            getPaths() {
                this.$axios
                    .req("paths")
                    .then(res => {
                        this.paths = res
                        console.log(res);
                    })
                    .catch(err => {
                        console.log(err);
                    });
            },
        },
        mounted() {
            this.getLouplus()
            this.getCourses()
            this.getBootcamps()
            this.getPaths()
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
  @import "../styles/common1";

  /deep/ .el-carousel__arrow--left {
    left: 5px !important;
  }

  /deep/ .el-carousel__arrow--right {
    left: 1100px !important;
  }

  .curriculum00 {
    min-width: 1080px;
    perspective: 800px;
  }

  .top {
    margin: 45px 0 10px 0;
    justify-content: space-between;
  }

  .top-name {
    font-size: 22px;
    color: #243644;
  }

  .top-text {
    font-size: 15px;
    color: #676767;
  }

  .top-more {
    font-size: 14px;
    color: #3a3c40;
  }

  .top-more:hover, .top-name:hover, .top-text:hover {
    cursor: pointer;
  }

  .curriculum {
    justify-content: space-between;
    margin: 30px 0;
  }

  .curriculum-item:hover {
    box-shadow: #6c6c6c 0px 0px 10px;
    cursor: pointer;
  }

  .curriculum-item {
    width: 260px;
    height: 184px;
    background: white;
    border-radius: 10px;

    .img {
      width: 260px;
      border-radius: 10px 10px 0 0;
    }

    .curriculum-title {
      margin: 20px auto;
      width: 90%;
      font-size: 15px;
      color: #2f2e31;
    }

    .curriculum-time {
      margin: 0 auto;
      width: 90%;
      font-size: 14px;
      color: #737279;
    }


    .curriculum-time > span {
      margin-left: 10px;
    }
  }

  .boutique0 {
    padding: 8px;
    margin: 12px auto;
    height: 68px !important;
    background: white;

    overflow: hidden;
    transition: all ease-in-out 0.4s;

    .boutique-title {
      margin-bottom: 6px;
      font-size: 16px;
      overflow: hidden;
      text-overflow: ellipsis;
      white-space: nowrap;
      color: #565656;
    }

    .boutique-text {
      height: 55px;
      display: -webkit-box;
      margin-top: 10px;
      color: #666;
      font-size: 13px;
      line-height: 1.4;
      -webkit-line-clamp: 3;
      -webkit-box-orient: vertical;
      overflow: hidden;
      text-overflow: ellipsis;
      word-wrap: break-word;
    }

  }

  .boutique {
    justify-content: space-between;

    .boutique-img {
      width: 555px;
      height: 250px;
      border-radius: 10px;
      margin: 20px 0;

    }

    .boutique-bottom {
      width: 100%;
      height: 56px;
      margin: 0 auto;
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
      bottom: 0;
      background: white;
      z-index: 99;

      .bottom-text {
        width: 95%;
        margin: 0 auto;
        margin-top: 25px;
        color: #626262;
        justify-content: space-between;

      }

      .bottom-text > div > span {
        margin-left: 10px;
        font-size: 14px;
      }
    }

    .boutique-img > img {
      width: 100%;
    }

    .boutique-item {
      width: 260px;
      height: 250px;
      margin: 20px 0;
      background: white;
      position: relative;
      transition: all ease-in 0.1s;
    }

    .boutique-item > img {
      width: 100%;
    }
  }

  .boutique-item:hover > .boutique0 {
    cursor: pointer;
    transform: translateY(-70%);
    z-index: 999;
  }

  .carousel {
    justify-content: space-between;
    display: flex;
    align-items: center;
    width: 1140px;
  }

  .boutique-left {
    width: 260px;
    height: 520px;
  }

  .boutique-left > img {
    margin-top: 20px;
    width: 100%;
  }

  .right {
    margin-left: 34px;
    width: 845px;
    height: 520px;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
  }

  .boutique1 {
    margin: 20px 0;
    display: flex;
    justify-content: space-between !important;
  }

  .boutique-item1 {
    margin-bottom: -3px !important;
  }

  .shaw:hover, .boutique-item:hover {
    cursor: pointer;
    box-shadow: #6c6c6c 0px 0px 10px;
  }

  .bootcamp {
    border-radius: 20px;
    padding: 3px 10px;
    font-size: 12px;
    display: flex;
    justify-content: center;
    align-items: center;
    color: #fff;
    background: #f66;
  }

  .member {
    background: #ffc500 !important;
  }

  .label {
    display: flex;
    justify-content: flex-start;
    height: 20px;


  }

  .label > div:nth-child(1) {
    width: 30px;
    height: 16px;
    position: absolute;
    top: 11px;
    left: -22px;
    background: #f66;

    transform: rotateY(-45deg);

  }

  .label > div:nth-child(2) {
    display: flex;
    align-items: center;
    height: 18px;
    position: absolute;
    top: 0;
    width: 64px;
    left: -16px;
    z-index: 9;
    padding: 1px 8px;
    color: #fff;
    background: #f66;
    font-size: 12px;
  }
  .label1 {
    display: flex;
    justify-content: flex-start;
    height: 20px;


  }

  .label1 > div:nth-child(1) {
    width: 30px;
    height: 16px;
    position: absolute;
    top: 4px;
    left: -22px;
    background: #f66;

    transform: rotateY(-45deg);

  }

  .label1 > div:nth-child(2) {
    display: flex;
    align-items: center;
    height: 18px;
    position: absolute;
    top: 0;
    width: 64px;
    left: -16px;
    z-index: 9;
    padding: 1px 8px;
    color: #fff;
    background: #f66;
    font-size: 12px;
  }



  .bootcamps {
    width: 1140px;
    margin: 20px auto;
    justify-content: space-between;
    height: 250px;
    .bootcamps-right{
      width: 642px;
      height: 250px;
    }
    .bootcamps-right>div:nth-child(1){
      width: 90%;
      margin: 20px auto;
      color: #424242;
      font-weight: 400;
      font-size: 18px;
      height: 10%;
    }
    .bootcamps-right>div:nth-child(2){
      width: 90%;
      margin: 20px auto;
      color: #424242;
      font-weight: 400;
      font-size: 15px;
      line-height: 22px;
      height: 40%;
    }
    .bootcamps-bottom{
      display: flex;
      justify-content: space-between;
      width: 90%;
      margin: 0 auto;
    }
    .bootcamps-bottom>div:nth-child(1){
      color: #292929;
    }

  }
  .bootcamps>img{
    height: 250px;
  }
  .path-bottom{
    width: 1140px;
    height: 272px;

    margin: 20px auto;
    display: flex;
    justify-content: space-between;
    .path-item{
      background: white;
      width: 262px;
      height: 272px;
      position: relative;
      .path-title{
        margin: 50px 0 20px 0;
        text-align: center;
        color: #666;
        font-size: 18px;

      }
      .path-text{
        text-align: center;
        color: #a4a4a4;
        font-size: 14px;
      }
      .path-ico{
        width: 44px;
        height: 21px;
        position: absolute;
        top: 10px;
        right: -5px;
      }

    }
    .path-item:hover{
      cursor: pointer;
      box-shadow: #6c6c6c 0px 0px 10px;
    }
    .path-item>img{
      width: 262px;

    }

  }



</style>
