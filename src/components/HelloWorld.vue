<template>
  <div class="img-deal">
    <div class="tools">
      <div class="content">
        <div class="show">
          <!-- 图片展示 -->
          <div class="imgList">
            <div class="one" v-if="imgList.length===1">
              <img  src="../assets/error.svg" alt="" />
            </div>
            <div  
              v-else
              class="img"   
              v-for="item in imgList" 
              :key="item" > 
              <img  src="../assets/error.svg" alt="" />
            </div>

          </div>

          <!-- 底部工具 -->
          <div class="footer">
            <div class="left">
              <i class="fa fa-bandcamp" aria-hidden="true"></i>
              <i class="fa fa-envelope-open" aria-hidden="true"></i>
            </div>
            <div class="right">
              <i class="fa fa-minus" aria-hidden="true"></i>
              <i class="fa fa-plus" aria-hidden="true"></i>
            </div>
          </div>

        </div>
        <div class="oper">
          <div class="edit">切换参数时保持现有编辑参数不变
            <el-switch v-model="editSwitch" >
</el-switch>
          </div>
<div class="imgXY">
   <i class="fa fa-bandcamp" aria-hidden="true"></i>
   X <el-input class="inp"> </el-input> Y<el-input class="inp"> </el-input> 
     <el-switch v-model="editSwitch">
</el-switch>
</div>
<div class="upload">
  <el-button type="primary"> 从水印库中选择</el-button>
  <el-button type="primary">上传水印图片</el-button>
</div>
<div class="light">
   <el-slider v-model="value1"></el-slider>亮度
</div>
<div class="opa">
   <el-slider v-model="value1"></el-slider>饱和度
</div>
<div class="gif">
  <div>GIF</div>
  <el-input></el-input>
  <el-input></el-input>
   <el-button type="primary">导出</el-button>
</div>
<div class="down">
  <el-button type="primary">下载图片</el-button>
  <el-button type="primary">分发图片至</el-button>
</div>
    
        </div>
      </div>
      <div class="img-scroll">
        这是图片内容
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      aa: 12,
      imgList: [1],
      editSwitch: true
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.img-deal {
  .tools {
    border: 4px solid #03a9f4;
    border-radius: 10px;
    width: 1000px;
    margin: 0 auto;
    .content {
      min-height: 500px;
      display: flex;
      .show {
        border: 4px solid #03a9f4;
        border-radius: 10px;
        width: 60%;
        margin: 10px 20px;
        display: flex;
        flex-direction: column;
        // 图片展示
        .imgList {
          flex: 1;
          // display: flex;
          // justify-content: center;
          // align-items: center;
          .one {
            width: 100%;
            height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
          }
          .img {
            height: 50%;
            width: 50%;
            display: inline-block;
          }
        }
        // 底部工具
        .footer {
          display: flex;
          justify-content: space-between;
          .left,
          .right {
            width: 60px;
            display: flex;
            justify-content: space-around;
            margin: 20px;
          }
        }
      }
      .oper {
        margin: 10px 0;
        .imgXY {
          text-align: left;
          .inp,
          /deep/.el-input,
          /deep/.el-input__inner {
            display: inline-block;
            width: 24px;
            height: 24px;
            margin:2px 4px;
            padding: 0;
          }
        }
        .gif{
          text-align: left;
           /deep/.el-input,
          /deep/.el-input__inner {
            display: inline-block;
            width: 60px;
            height: 24px;
            margin:2px 4px;
            padding: 0;
          }
        }
      }
    }
    .img-scroll {
      min-height: 100px;
    }
  }
}
</style>
