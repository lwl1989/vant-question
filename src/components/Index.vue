<template>
  <form style="margin-top: 20px;margin-bottom: 20px;">

    <div class="question_title">
      <p class="title"><span style="color: red">*</span>1、您是否在桥南家电城内经营？</p>
      <span class="intro">如您不在桥南家电城，额度可能为零。</span>
    </div>
    <div class="question_line">
      <div style="padding-left: 2%">
        <van-radio-group v-model="in_mall" style="margin-top: 2px;font-size:0.3em;line-height: 25px;">
          <van-radio name="1">是的</van-radio>
          <van-radio name="2">不是</van-radio>
        </van-radio-group>
      </div>
    </div>

    <div class="question_title">
      <p class="title"><span style="color: red">*</span>2、您在该市场经营年限是？</p>
      <span class="intro">以实际经营年限为准，可以营业执照、租赁合同、代理合同为准。</span>
    </div>
    <div class="question_line">
      <div style="padding-left: 1%">
        <van-radio-group v-model="years"  style="margin-top: 2px;padding-left:2px;font-size:0.3em;line-height: 25px;">
          <van-radio name="1">十年以上</van-radio>
          <van-radio name="2">5-10年</van-radio>
          <van-radio name="3">3-5年</van-radio>
          <van-radio name="4">1-3年</van-radio>
          <van-radio name="5">1年以下</van-radio>
        </van-radio-group>
      </div>
    </div>

    <div class="question_title">
      <p class="title"><span style="color: red">*</span>3、您或者配偶是否本地人？</p>
    </div>
    <div class="question_line">
      <div style="padding-left: 1%">
        <van-radio-group v-model="local_people" style="margin-top: 2px;padding-left:2px;font-size:0.3em;line-height: 25px;">
          <van-radio name="1">常德市区户籍</van-radio>
          <van-radio name="2">常德地区非市区户籍</van-radio>
          <van-radio name="3">省内非常德户籍</van-radio>
          <van-radio name="4">省外户籍</van-radio>
        </van-radio-group>
      </div>
    </div>

    <div class="question_title">
      <span class="title"><span style="color: red">*</span>4、您在本地的居住情况？</span>
      <span class="intro">商品房包含抵押和按揭房产</span>
    </div>
    <div class="question_line">
      <div style="padding-left: 1%">
        <van-radio-group v-model="living" style="margin-top: 2px;padding-left:2px;font-size:0.3em;line-height: 25px;">
          <van-radio name="1">多套商品房</van-radio>
          <van-radio name="2">一套商品房</van-radio>
          <van-radio name="3">自建房</van-radio>
          <van-radio name="4">租住</van-radio>
        </van-radio-group>
      </div>
    </div>

    <div class="question_title">
      <span class="title"><span style="color: red">*</span>5、您及配偶信用卡使用状况？</span>
    </div>
    <div class="question_line">
      <div style="padding-left: 1%">
        <van-radio-group v-model="card" style="margin-top: 2px;padding-left:2px;font-size:0.3em;line-height: 25px;">
          <van-radio name="1">总额度低于10万</van-radio>
          <van-radio name="2">占用总额度50%以下</van-radio>
          <van-radio name="3">占用总额度50%-70%</van-radio>
          <van-radio name="4">占用总额度70%-90%</van-radio>
          <van-radio name="4">占用总额度90%以上</van-radio>
        </van-radio-group>
      </div>
    </div>

    <div class="question_title">
      <p class="title"><span style="color: red">*</span>6、您的年龄段？</p>
    </div>
    <div class="question_line">
      <div style="padding-left: 1%">
        <van-radio-group v-model="age" style="margin-top: 2px;padding-left:2px;font-size:0.3em;line-height: 25px;">
          <van-radio name="1">18周岁以下或者65周岁以上</van-radio>
          <van-radio name="2">18-28周岁</van-radio>
          <van-radio name="3">28-50周岁</van-radio>
          <van-radio name="4">50-65周岁</van-radio>
        </van-radio-group>
      </div>
    </div>

    <div class="question_title">
      <p class="title"><span style="color: red">*</span>7、您的年销售规模？</p>
    </div>
    <div class="question_line">
      <div style="padding-left: 1%">
        <van-radio-group v-model="sales"  style="margin-top: 2px;padding-left:2px;font-size:0.3em;line-height: 25px;">
          <van-radio name="1">1000万以上</van-radio>
          <van-radio name="2">500-1000万</van-radio>
          <van-radio name="3">300-500万</van-radio>
          <van-radio name="4">100-300万</van-radio>
          <van-radio name="5">100万以下</van-radio>
        </van-radio-group>
      </div>
    </div>

    <!--<div class="question_title">-->
      <!--<p class="title">电话</p>-->
    <!--</div>-->
      <!--<div style="padding-left: 1%">-->
        <!--<van-cell-group>-->
          <!--<van-field type="tel" v-model="tel" placeholder="请输入电话" />-->
        <!--</van-cell-group>-->
      <!--</div>-->

    <!--<div class="question_title">-->
      <!--<p class="title">7、您对我行有哪些宝贵的建议?</p>-->
    <!--</div>-->
      <!--<div style="padding-left: 1%">-->
        <!--<van-cell-group>-->
          <!--<van-field-->
            <!--v-model="message"-->
            <!--type="textarea"-->
            <!--placeholder="请输入建议"-->
            <!--rows="3"-->
            <!--autosize-->
          <!--/>-->
        <!--</van-cell-group>-->
      <!--</div>-->
    <div>
      <result-component ref="result"></result-component>
      <van-button type="primary" @click="click_href"  style="width: 80%;margin-top: 5px;background: #1593ff;border: #1593ff 1px solid">提交</van-button>
    </div>
  </form>
</template>

<script>
import ResultComponent from './Result'
export default {
  name: 'HelloWorld',
  components: {ResultComponent},
  data: function () {
    return {
      in_mall: '1',
      years: '1',
      local_people: '1',
      living: '1',
      age: '1',
      sales: '1',
      tel: '',
      card: '1',
      message: ''
    }
  },
  methods: {
    click_href: function (e) {
      this.$refs.result.show(this)
    }
  }
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .question_title {
    text-align: left;
    margin-top: 10px;
    margin-left: 2%;
  }
  .van-radio__control{
    line-height: 30px;
  }
  .van-radio__label{
    line-height: 25px;
  }
  .van-radio{
    padding-top: 3px;
    padding-bottom: 3px;
  }
.question_line{
  width: 95%;
  text-align: left;
  margin-left: 2%;
  margin-top:2px;
  border: darkgray solid 1px;
  border-radius:5px;
}
.title{
  font-size: 16px;
  display: block;
  margin: 0;
  padding: 0;
  margin-left: 5px;
}
.intro{
  font-size: 12px;
  margin: 0;
  padding: 0;
  margin-left: 5px;
  color: darkgray;
  line-height: 0.3em;
  height: 0.3em;
}

</style>
