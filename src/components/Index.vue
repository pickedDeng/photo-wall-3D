<template>
  <div class="wenming">
    <!-- <div class="content"> -->
      <div class="photo-wrap">
        <div class="container1">
          <div class="img imgALL" v-for="(itemImg,index) in column" :key="index">
            <div class="imgBox">
               <img src="../assets/imgs/timg.jpg" alt />
            </div>
            <div class="imgBox">
               <img src="../assets/imgs/timg.jpg" alt />
            </div>
            <div class="imgBox">
               <img src="../assets/imgs/timg.jpg" alt />
            </div>
          </div>
        </div>
      </div>
    <!-- </div> -->
  </div>
</template>
<script>
export default {
  data() {
    return {
    //   imgData:[],
      column:16, //多少列
    };
  },
  mounted() {
    this.$nextTick(()=>{
      this.picturesRotating(this.column);
    })
  },
  methods: {
   
    // 页面旋转的方法
    picturesRotating(column){
      var imgAll=document.getElementsByClassName('imgALL'); //获取列
      for(var i=0;i<imgAll.length;i++){
        imgAll[i].style.transform='rotateY('+360/column*(i+1)+'deg) translateZ(1500px) rotateX(0)';
      }
    }
  }
};
</script>
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
@keyframes rotate-frame {
  0% {
    transform: rotateX(0) rotateY(0deg);
  }
  10% {
    transform: rotateX(0) rotateY(36deg);
  }
  20% {
    transform: rotateX(0) rotateY(72deg);
  }
  30% {
    transform: rotateX(0) rotateY(108deg);
  }
  40% {
    transform: rotateX(0) rotateY(144deg);
  }
  50% {
    transform: rotateX(0) rotateY(180deg);
  }
  60% {
    transform: rotateX(0) rotateY(216deg);
  }
  70% {
    transform: rotateX(0) rotateY(252deg);
  }
  80% {
    transform: rotateX(0) rotateY(288deg);
  }
  90% {
    transform: rotateX(0) rotateY(324deg);
  }
  100% {
    transform: rotateX(0) rotateY(360deg);
  }
}
body {
  background: #f9f9f9;
}
.imgALL .imgBox{
  width: 100%;
  height: 45%;
  margin-bottom: 20px;
}
img{
  width: 100%;
  height: 100%;
  object-fit: cover;
  transform: rotateY(180deg)
}
.photo-wrap {
  perspective: 950px;
  width: 1700px;
  margin: 0 auto;
  height: 100%;
  overflow: hidden;

}
.container1 {
  width: 800px;
  height: 900px;
  margin: 150px auto 0;
  position: relative;
  transform-style: preserve-3d;
  transform: rotateX(0deg);
  animation: rotate-frame 50s linear infinite;
}
.img {
  width: 572px;
  height: 100%;
  text-align: center;
  position: absolute;
  top: -140px;
  left: 111px;
}
.wenming {
  display: flex;
  width: 100%;
  height: 100%;
  justify-content: center;
  align-items: center;
  background: url("../assets/imgs/统一背景_03.png") no-repeat;
  overflow: hidden;
}
/* .content {
  width: 1884px;
  height: 1044px;
  background: url("./assets/imgs/28a0e28dcd4075ad18c0b7432dcf614.png") no-repeat;
  overflow: hidden;

} */
</style>

