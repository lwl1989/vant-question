<template>
  <div id="app">
    <div class="common_header" style="padding-bottom: 20px;">
      <div style="color: #fff;font-size: 1.5em;padding-top: 10px;">长沙银行“长湘贷“</div>
      <div class="is-size-small" style="color: rgb(88, 235, 222);margin-top: 20px;font-size: 0.5em;">//桥南市场客户专属额度自测表//</div>
      <div style="background: rgb(46,166,223);color: #fff;font-size: 0.5em; text-align: left; width: 80%;margin-left: 10%;margin-top: 20px;">
        <p style="padding-left: 1em;padding-right: 1em;padding-top: 0.5em;padding-bottom: 0.5em;">
          桥南家电城是辐射湘西北家电批零的重要市场之一，为此长沙银行小企业信贷中心量身定制了授信方案，只需填入基本信息，即可出具初评额度。
          <br/>
          <br/>
          非常感谢
        </p>
      </div>
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
  body{
    font-family: '微软雅黑', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
#app {
  text-align: center;
  color: #2c3e50;
  #margin-top: 60px;
  border:1px solid #999;
  height: 100%;
  width: 100%;
}
.common_header{
  background: url("../static/logo.png") no-repeat;
  background-size:100% 100%;-moz-background-size:100% 100%;
}
@media only screen and (min-width:320px) and (min-height:480px){
  #app {
    width: 100%;
  }
}
@media only screen and (min-width:320px) and (min-height:568px){
  #app {
    width: 100%;
  }
}
@media only screen and (min-width:360px) and (min-height:640px){
  #app {
    width: 100%;
  }
}
@media only screen and (min-width:375px) and (min-height:667px){
  #app {
    width: 100%;
  }
}
@media only screen and (min-width:414px) and (min-height:736px){
  #app {
    width: 100%;
  }
}
@media only screen and (min-width:736px){
  #app {
    width: 50%;
    margin: 0 auto;
  }
}
</style>
