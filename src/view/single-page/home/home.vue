<template>
  <div class="box">
    <Row class="aboutme">
      <i-col :md="2" :lg="3" style="margin-bottom: 5px;">
        <Card>
          <img style="margin:0 20px" src="@/assets/images/photo.jpg" alt />
        </Card>
      </i-col>
      <i-col :md="2" :lg="5" style="margin-bottom: 5px;">
        <Card style="height:200px">
          <div class="namebox">
            <p>
              姓名：
              <span>史昌琳</span>
            </p>
            <p>
              出生日期：
              <span>1996-5-20</span>
            </p>
            <p>
              联系电话：
              <span>15545474140</span>
            </p>
            <p>
              邮箱：
              <span>1052606486@qq.com</span>
            </p>
            <p>
              求职方向：
              <span>web前端工程师</span>
            </p>
            <p>
              毕业院校：
              <span>哈尔滨理工大学</span>
            </p>
            <p>
              政治面貌：
              <span>中共党员</span>
            </p>
          </div>
        </Card>
      </i-col>
      <i-col :md="2" :lg="5" style="margin-bottom: 5px;">
        <Card>
          <div class="namebox">
            <p>
              校园经历：
              <span>班长、院学生会副主席</span>
            </p>
          </div>
        </Card>
        <Card>
          <div class="namebox">
            <p>
              兴趣爱好：
              <span>唱歌，各种球类运动、看电影、听音乐</span>
            </p>
          </div>
        </Card>
        <Card>
          <div class="namebox">
            <p>
              专业：
              <span>三等奖学金、CET4</span>
            </p>
          </div>
        </Card>
      </i-col>
      <i-col :md="24" :lg="7" style="margin-bottom: 5px;padding-bottom:9px;">
        <Card style="height:200px" shadow>
          <p>实习经历：</p>
          <p>2019.5-2019.9 上海蔚来汽车有限公司</p>
          DO部门 负责数据可视化的开发工作；
          主要技术栈是vue、echarts。自主运营监控部门的大屏可视化项目。受益良多。
          <p>2019.10-至今 京东数字科技集团</p>
          京东集团-京东数字科技-数字技术中心-数字化管理研发部-企业应用与效能提升组
          主要负责数科官网开发。主要的技术栈是nuxt，本质上是vue
        </Card>
      </i-col>
       <i-col :md="23" :lg="4" style="margin-left:2px;margin-bottom: 5px;">
        <Card shadow>
            <ul style="list-style:none;">
              <li v-for='(item,index) in softSkills' :key="index">
                <p>{{item.name}}:
                 <Icon type="ios-star" v-for="n in 4" :key="n"></Icon><Icon type="ios-star" v-if="item.rate >= 9.5"></Icon><Icon type="ios-star-half" v-else></Icon>
                </p>
              </li>
            </ul>
        </Card>
        <Card style="height:95px" shadow>
          <span>
            具有好奇心，抗压能力强。在学习上能够积极主动的接触新知识，虚心听取前辈的意见。
          </span>
        </Card>
      </i-col>
    </Row>
    <Row :gutter="20" style="margin-top: 5px;">
      <i-col :md="24" :lg="7" style="margin-bottom: 20px;">
        <Card shadow>
          <chart-pie style="height: 300px; margin-left:5px;" :value="pieData" text="专业技能"></chart-pie>
        </Card>
        
      </i-col>
    </Row>
    <Row></Row>
  </div>
</template>

<script>
import InforCard from "_c/info-card";
import CountTo from "_c/count-to";
import { ChartPie, ChartBar } from "_c/charts";
import Example from "./example.vue";
import {HomePage} from "_c/echarts-box"
export default {
  name: "home",
  components: {
    InforCard,
    CountTo,
    ChartPie,
    ChartBar,
    Example
  },
  data() {
    return {
      pieData: [
        { value: 250, name: "js" },
        { value: 310, name: "vue" },
        { value: 234, name: "react" },
        { value: 135, name: "HTML/HTML5" },
        { value: 300, name: "css/css3" },
        { value: 200, name: "小程序" },
        { value: 120, name: "axios封装" },
        { value: 100, name: "git" }
      ],
      softSkills:[
        {
          name:'VsCode',
          rate:9.5
        },
        {
          name:'Chrome',
          rate:9.5
        },
        {
          name:'sourceTree',
          rate:8.5
        },
      ]
    };
  },
  mounted() {
    //
  }
};
</script>

<style lang="less">

.count-style {
  font-size: 50px;
}

.aboutme {
  display: flex;
  img {
    width: 120px;
    height: 163px;
  }
  .namebox {
    margin-left: 20px;
  }
  p {
    font-size: 16px;
    font-weight: 600;
    span {
      font-weight: 500;
    }
  }
}
</style>
