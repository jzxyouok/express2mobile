<template>
  <div id="app1">
        <div class="weui-tab">
          <div class="weui-tab__panel">
            <router-view></router-view>
          </div>
          <div class="weui-tabbar">
            <router-link to="/index" class="weui-tabbar__item" :class="{'weui-bar__item_on':isActive==1}">
              <div class="weui-tabbar__icon">
                <img src="./assets/icon_nav_button.png" alt="">
              </div>
              <p class="weui-tabbar__label">寄快递</p>
            </router-link>
            <router-link to="/orderlist" class="weui-tabbar__item" :class="{'weui-bar__item_on':isActive==2}"> 
              <div class="weui-tabbar__icon">
                <img src="./assets/icon_nav_cell.png" alt="">
              </div>
              <p class="weui-tabbar__label">查快递</p>
            </router-link>
            <router-link to="/addressbook/addresslist" class="weui-tabbar__item" :class="{'weui-bar__item_on':isActive==3}">
              <div class="weui-tabbar__icon">
                <img src="./assets/icon_nav_toast.png" alt="">
              </div>
              <p class="weui-tabbar__label">地址库</p>
            </router-link>
            <router-link to="/settings/center" class="weui-tabbar__item" :class="{'weui-bar__item_on':isActive==4}">
              <div class="weui-tabbar__icon">
                <img src="./assets/icon_nav_dialog.png" alt="">
              </div>
              <p class="weui-tabbar__label">设置</p>
           </router-link>
          </div>
      </div>
  </div>
</template>

<script>

export default {
  name: 'app1',
    data () {
    return {
      
    }
  },
  components: {
    
  },
  computed:{
    isActive:function(){
      var path =this.$route.path;
      console.log(path.search('/index'))
      
      if(path.search('/index')!==-1){
        return 1;
      }
      if(path.search('/orderlist')!==-1){
        return 2;
      }
      if(path.search('/addressbook')!==-1){
        return 3;
      }
      if(path.search('/settings')!==-1){
        return 4;
      }
    }
  }
}
</script>

<style>
#app1 {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height:100%;

}
</style>
