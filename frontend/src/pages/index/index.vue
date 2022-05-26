<template>
  <view class="index">
    <view class="card-info">
      <view class="user-info">
        <view class="user-header"></view>
        <view class="user-time">
          <view class="user-name">lingdu's Flag</view>
          <view class="user-date">2022/06/01</view>
        </view>
      </view>
      <view class="flag-content">
        <view>我要减肥</view>
        <view class="word-loading">进行中</view>
      </view>
      <view class="flag-footer">
        <nut-row style="overflow:hidden;">
          <nut-col :span="10" class="progress">
            <div style="float:right;" class="progress-bar">
                <div style="background-color:rgba(66,147,33,1);height:0.5rem;"></div>
            </div>
            <div class="progress-icon-left">
            <nut-icon name="fabulous" color="#fff"></nut-icon>
            </div>
          </nut-col>
          <nut-col :span="4">
            <span class="word-vs">VS</span>
          </nut-col>
           <nut-col :span="10"  class="progress">
             <div style="float:left;" class="progress-bar">
                <div style="background-color:#fa6419;height:0.5rem;"></div>
             </div>
             <div class="progress-icon-right">
            <nut-icon name="footprint" color="#fff"></nut-icon>
             </div>
          </nut-col>
        </nut-row>
      </view>
    </view>
    <!-- <view>
      <img src="" alt="">
    </view>
    {{ msg }}
    <view class="btn">
      <nut-button type="primary" @click="handleClick('text', msg2, true)">点我</nut-button>
    </view>
    <nut-toast :msg="msg" v-model:visible="show" :type="type" :cover="cover" /> -->
  </view>
</template>

<script>
import { reactive, toRefs } from 'vue';
export default {
  name: 'Index',
  components: {
    
  },
  setup(){
    const state = reactive({
      msg: '欢迎使用 NutUI3.0 开发小程序',
      msg2: '你成功了～',
      type: 'text',
      show: false,
      cover: false
    });

    const handleClick = (type, msg, cover = false) => {
      state.show = true;
      state.msg2 = msg;
      state.type = type;
      state.cover = cover;
    };

    return {
      ...toRefs(state),
      handleClick
    }
  }
}
</script>

<style lang="scss">
.index {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
.card-info{
  margin:1rem;
  padding:1rem;
  border:0.1rem solid #4cb3d4;
  border-radius: 1rem;
  height:20rem;
  background-color:#eef9fd;
   flex-direction: column;
   display:flex;
   justify-content: space-between;
}
.user-info{
  overflow:hidden;
}
.user-header{
  float:left;
  width:3rem;
  height:3rem;
  border:0.1rem solid #ccc;
  border-radius: 1.5rem;
}
.user-name{
  font-size:0.8rem;
}
.user-time{
  float:left;
  padding: 0.5rem 1rem;
  text-align: left;
}
.user-date{
  font-size:0.6rem;
  color:#ccc;
  text-align: left;
}
.flag-content{
 flex-grow:1;
 flex-direction: column;
   display:flex;
 justify-content: center;
}
.flag-footer{
 height:3rem;
 overflow:hidden;
}
.word-vs{
  font-size:1.4rem;
  font-weight: bold;
}
.word-loading{
  color:#CCCCCC;
  font-size:0.6rem;
}
.progress{
  padding:0.8rem 0.1rem;
}
.progress-icon-left{
float:right;
background-color:rgba(66,147,33,1);
  width: 1.4rem;
  height: 1.4rem;
  margin-top: -0.4rem;
border-radius:50%;
}
.progress-icon-right{
float:left;
background-color:#fa6419;
 width: 1.4rem;
  height: 1.4rem;
  margin-top: -0.4rem;
border-radius:50%;
}
.progress-bar{
height:0.5rem;width:70%;
}
</style>
