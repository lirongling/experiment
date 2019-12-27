<template>
  <div>
    <div class="block">
      <el-carousel >
        <el-carousel-item v-for="(item,index) in pictures" :key="index">
          <img :src="item.picture_url">
        </el-carousel-item>
      </el-carousel>
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
                pictures:[]
            }
        },
        methods: {
            getPictures() {
                this.$axios
                    .req("banner-pictures")
                    .then(res => {
                        this.pictures = res
                        console.log(res);
                    })
                    .catch(err => {
                        console.log(err);
                    });
            },
        },
        mounted() {
            this.getPictures()
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
  .el-carousel__item h3 {
    color: #475669;
    font-size: 14px;
    opacity: 0.75;
    line-height: 150px;
    margin: 0;
  }

  .el-carousel__item:nth-child(2n) {
    background-color: #99a9bf;
  }

  .el-carousel__item:nth-child(2n+1) {
    background-color: #d3dce6;
  }
</style>
