<template>
  <div><!-- <div class="wd-top">顶部导航栏111</div> -->
    <div class="wd-con">
      <div class="con-top">
        <div class="con-top-img">
          <img src="../assets/con-top.png" />
        </div>
      </div>
      <div class="con-con">
        <div class="con-con-top">
          <ul>
            <li>首&nbsp;&nbsp;页</li>
            <li>机构设置</li>
            <li>重要文件</li>
            <li>组织民管</li>
            <li>保障女工</li>
            <li>生产宣传</li>
            <li>财务经审</li>
            <li>综合办公</li>
            <li>党组织建设</li>
          </ul>
        </div>
        <div class="con-con-search">   
        </div>
      </div>
      <div class="con-content">
        <div class="content-left">
          <a-carousel :after-change="onChange" autoplay>
            <div><img style="width:100%;" src="../assets/1.jpg"/></div>
            <div><img style="width:100%;" src="../assets/2.jpg"/></div>
            <div><img style="width:100%;" src="../assets/3.jpg"/></div>
          </a-carousel>
        </div>
        <div class="content-right">
          <div class="title">
            <div class="title-name">工会要闻</div>
            <div class="title-area-left"></div>
            <div class="title-area-right"></div>
            <div class="title-more">更多</div>
          </div>
          <div class="content-title">
            <div class="content-title-name">
              集团公司工会迅速组织劳模先进热议党的二十大报告
            </div>
            <div class="content-title-content">
              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;这里是轮播图片的详细内容开头部分这里是轮播图片的详细内容开头部分这里是轮播
              图片的详细内容开头部分这里是轮播图片的详细内容开头部分这里是轮播图片的详细
              内容开头部分这里是轮播图片的详细内容开头部分这里是轮播图片的详细内容开头部
              分这里是轮播图片的详细内容开头部分.....
              <font>【详情】</font>
              
            </div>
          </div>
          <div class="content-list">
            <ul>
              <li>赵俊赵培林到青岗村调研指导 <div>2023-01-26</div></li>
              <li>赵俊赵培林到青岗村调研指导 <div>2023-01-26</div></li>
              <li>赵俊赵培林到青岗村调研指导 <div>2023-01-26</div></li>
              <li>赵俊赵培林到青岗村调研指导赵俊赵培林到青岗村调研指导 <div>2023-01-26</div></li>
              <li>赵俊赵培林到青岗村调研指导 <div>2023-01-26</div></li>
            </ul>
          </div>
        </div>
      </div>
    </div>
    <a-divider></a-divider>
    <div class="con-content-card">
      <div v-for="index in [1,2,3,4,5,6]" :key="index">
          <div class="title">
            <div class="title-name">工会要闻{{ index }}</div>
            <div class="title-area-left"></div>
            <div class="title-area-right"></div>
            <div class="title-more">更多</div>
          </div>
          <div class="content-list">
            <ul>
              <li>赵俊赵培林到青岗村调研指导 <div>2023-01-26</div></li>
              <li>赵俊赵培林到青岗村调研指导 <div>2023-01-26</div></li>
              <li>赵俊赵培林到青岗村调研指导 <div>2023-01-26</div></li>
              <li>赵俊赵培林到青岗村调研指导赵俊赵培林到青岗村调研指导 <div>2023-01-26</div></li>
              <li>赵俊赵培林到青岗村调研指导 <div>2023-01-26</div></li>
            </ul>
          </div>
      </div>
    </div>
    <div class="wd-sider">
      <div class="wd-sider-list">
        <img style="width: 20px;height: 20px;" src="../assets/fasfa-phone-volume@2x.png" />
        联系电话</div>
      <div class="wd-sider-list">
        <img style="width: 20px;height: 20px;" src="../assets/farfa-comment-dots@2x.png" />
        网上留言
      </div>
      <div class="wd-sider-list">
        <img style="width: 20px;height: 20px;" src="../assets/farfa-file-alt@2x.png" />
        模板下载</div>
      <div class="wd-sider-list">
        <img style="width: 20px;height: 20px;" src="../assets/if-award@2x.png" />
        竞赛培训</div>
      <div class="wd-sider-list">
        <img style="width: 20px;height: 20px;" src="../assets/riLine-edit-2-line@2x.png" />
        及时填报</div>
      <div class="wd-sider-list">
        <img style="width: 20px;height: 20px;" src="../assets/if-ui-touch-phone@2x.png" />
        宣传矩阵</div>
    </div>
    <div class="wd-back-top" v-if="showBtn" @click="backTop()">回顶部</div>
  </div>
</template>
<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      showBtn: false,
      ulContent: ["头部内容1", "头部内容2", "头部内容3", "头部内容4", "头部内容5", "头部内容6", "头部内容7"]
    }  
  },
  mounted() {
    window.addEventListener("scroll", this.scrollEvent, true);
  },
  methods: {
    // 回到顶部是否狮子
    scrollEvent() {
      let that = this;
      let scrollTop =
        window.pageYOffset ||
        document.documentElement.scrollTop ||
        document.body.scrollTop;
      console.log('scroll', scrollTop)
      that.scrollTop = scrollTop;
      if (scrollTop > 2000) {
        this.showBtn = true;
      } else {
        this.showBtn = false;
      }
      let header = document.querySelector('.wd-top')
      // let styTop = document.querySelector('.wd-top')
      if (that.scrollTop > 60) {
        header.style.background = 'red'
        header.style.top = '0'
      } else {
        header.style.background = 'goldenrod'
        header.style.top = '-90px'
      }
    },
    /*回到顶部实现过程注解：
      1.获取当前页面距离顶部的距离
      2.计算出每次向上移动的距离，用负的滚动距离除以5，因为滚动的距离是一个正数，想向上移动就是一个减法
      3.用当前距离加上计算出的距离，然后赋值给当前距离，就可以达到向上移动的效果
      4.最后在移动到顶部的时候，清除定时器
    */
    backTop() {
      var timer = setInterval(function () {
        let osTop =
          document.documentElement.scrollTop || document.body.scrollTop;
        let ispeed = Math.floor(-osTop / 5);
        document.documentElement.scrollTop = document.body.scrollTop =
          osTop + ispeed;
        this.isTop = true;
        if (osTop === 0) {
          clearInterval(timer);
        }
      }, 30);
    }
  }  
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" scoped>
.wd-before-top{
  width: 100%;
  height: 100px;
  background: goldenrod;
}
.wd-top{ 
  position: fixed;
  top: -80px;
  /*-80px默认情况为隐藏头图，下滑到一定距离再显示*/
  left: 0;
  width: 100%;
  height: 80px;
  background-color: purple;
  text-align: center;
  color: #fff;
  line-height: 80px;
  font-size: 30px;
  transition: all .3s;
}
.wd-sider {
  width: 120px;
  position: fixed;
  right: 0;
  top: 45%;
  text-align: center;
  line-height: 35px;
  background-color: #BD1B2D;
  opacity: 0.72;
  box-shadow: 0px 1px 3px 1px #888888;
  z-index: 999;
}
.wd-sider-list{
  font-size: 14px;
  font-weight: bolder;
  color: #F9FBE6;
  border: 1px solid;
}
.wd-sider-list:hover{
  padding: 0px;
  background: rgb(252, 5, 5);
  width: 140px;
  font-size: 16px;
  margin-left: -10px;
  transition: property;
}
 .wd-back-top {
   height: 35px;
   width: 37px;
   position: fixed;
   right: 4%;
   bottom: 11%;
   text-align: center;
   line-height: 35px;
   font-size: 25px;
   background-color: #fff;
   border-radius: 50%;
   box-shadow: 0px 1px 3px 1px #888888;
   z-index: 999;
 }
.wd-con{
  width: 100%;
  background: white;
  .con-top {
    height: 20vh;
    .con-top-img{
      width: 60%;
      margin-left: 5%;
      height: 100%;
      text-align: center;
      overflow: hidden;
      >img{
        text-align: center;
        margin-top: 20px;
        display: block;
        width: 100%;
      }
    }
  }
  .con-con{
    height: 60vh;
    // background: gray;
    background: url(../assets/1.jpg);
    .con-con-top{
      margin: 0;
      height: 30px;
      background: #fff;
      >ul{
        display: block;
        overflow: hidden;
        white-space: nowrap;
        >li{
          margin: 8px 0 8px 0;
          list-style: none;
          font-size: 15px;
          font-family:"Microsoft YaHei";
          color: black;
          font-weight: bolder;
          display: inline-block;
          margin-left: 15px;
          width: 110px;
        }
        >li:hover{
          color: salmon;
          border-bottom: 2px solid salmon;
        }
      }
    }
    .con-con-search{
    }
  }
  .con-content{
    margin-top: 5vh;
    height: 40vh;
    // border: 1px solid gray;
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-items: center;
    .content-left{
      width: 40%;
      height: 40vh;
      // border: 1px solid red;
    }
    .content-right {
      width: 40%;
      height: 40vh;
      box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
      // border: 1px solid blue;
      .title{
        margin-top: 10px;
        display: flex;
        margin-left: 40px;
        flex-direction: row;
        justify-content: flex-start;
        align-items: center;
        .title-name{
          color: #B53331;
          font-weight: bolder;
          font-size: 15px;
          margin-right: 10px;
        }
        .title-area-left{
          width: 10%;
          height: 5px;
          margin-right: 5px;
          background-color: #CD0505;
        }
        .title-area-right{
          width: 60%;
          overflow: hidden;
          height: 2px;
          margin-right: 10px;
          background-color: #BBBBBB;
        }
        .title-more{
          font-size: 13px;
          font-weight: border;
        }
      }
      .content-title{
        margin-bottom: 10px;
        .content-title-name{
          margin: 20px 0 20px 0;
          font-size: 14px;
          
          color: #CD0505;
          font-weight: bolder;
        }
        .content-title-content{
          // border: 1px solid red;
          margin: 0 40px 0 40px;
          font-size: 10px;
          font-weight: bold;
          text-align: left;
          >font{
            font-weight: bold;
            text-align: right;
            color: #CD0505;
          }
        }
      }
      .content-list{
        
        margin-right: 40px;
        >ul{
          text-align: center;
          text-align: left;
          font-size: 12px;
          font-weight: bold;
          list-style-type: square;
          >li{
            margin-top: 4px;
            // border: 1px solid red;
            position:relative;
            >div{
              z-index: 2;
              color: gray;
              position:absolute;
              top: 0px;
              right: 0px;
              // border: 1px solid blue;
            }
          }
        }
      }
    }
  }
}
.con-content-card{
  height: 20vh;
  display: flex;
  flex-wrap: wrap;
  margin-top: 20px;
  align-items: center;
  flex-direction: row;
  justify-content: space-around;
  >div{
    margin-bottom: 20px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    // border: 1px solid red;
    width: 32%;
    height: 100%;
    .title{
        margin-top: 10px;
        display: flex;
        flex-direction: row;
        justify-content: flex-start;
        align-items: center;
        .title-name{
          color: #B53331;
          font-weight: bolder;
          font-size: 15px;
          margin-left: 20px;
          margin-right: 5px;
        }
        .title-area-left{
          width: 10%;
          height: 5px;
          margin-right: 5px;
          background-color: #CD0505;
        }
        .title-area-right{
          width: 60%;
          overflow: hidden;
          height: 2px;
          margin-right: 10px;
          background-color: #BBBBBB;
        }
        .title-more{
          font-size: 13px;
          font-weight: border;
        }
      }
    .content-list{
        
        margin-right: 10px;
        >ul{
          padding: 0 0 0 10px;
          margin-left: 10px;
          text-align: center;
          text-align: left;
          font-size: 12px;
          margin-left: 20px;
          font-weight: bold;
          list-style-type: square;
          >li{
            margin-top: 4px;
            // border: 1px solid red;
            
            position:relative;
            >div{
              z-index: 2;
              color: gray;
              position:absolute;
              top: 0px;
              right: 0px;
              // border: 1px solid blue;
            }
          }
        }
      }
  }
}
/* For demo 浮动窗口 */ 
.ant-carousel :deep(.slick-slide) {
  text-align: center;
  height: 40vh;
  line-height: 100%;
  background: #364d79;
  overflow: hidden;
}
.ant-carousel :deep(.slick-slide h3) {
  color: #fff;
}
</style>
