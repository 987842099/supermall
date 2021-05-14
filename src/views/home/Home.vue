<template>
  <div id="home">
    <nav-bar class="home-nav"><div slot="center">购物街</div></nav-bar>
    <home-swiper :banners="banners"></home-swiper>
    <recommend-view :recommends="recommends"></recommend-view>
    <pop-in-week></pop-in-week>

    <ul>
      <li>列表11</li>
      <li>列表12</li>
      <li>列表13</li>
      <li>列表14</li>
      <li>列表15</li>
      <li>列表16</li>
      <li>列表17</li>
      <li>列表18</li>
      <li>列表19</li>
      <li>列表110</li>
      <li>列表111</li>
      <li>列表112</li>
      <li>列表113</li>
      <li>列表114</li>
      <li>列表115</li>
      <li>列表116</li>
      <li>列表117</li>
      <li>列表118</li>
      <li>列表119</li>
      <li>列表120</li>
      <li>列表121</li>
      <li>列表122</li>
      <li>列表123</li>
      <li>列表124</li>
      <li>列表125</li>
      <li>列表126</li>
      <li>列表127</li>
      <li>列表128</li>
      <li>列表129</li>
      <li>列表130</li>
      <li>列表131</li>
      <li>列表132</li>
      <li>列表133</li>
      <li>列表134</li>
      <li>列表135</li>
      <li>列表136</li>
      <li>列表137</li>
      <li>列表138</li>
      <li>列表139</li>
      <li>列表140</li>
      <li>列表141</li>
      <li>列表142</li>
      <li>列表143</li>
      <li>列表144</li>
      <li>列表145</li>
      <li>列表146</li>
      <li>列表147</li>
      <li>列表148</li>
      <li>列表149</li>
      <li>列表150</li>
      <li>列表151</li>
      <li>列表152</li>
      <li>列表153</li>
      <li>列表154</li>
      <li>列表155</li>
      <li>列表156</li>
      <li>列表157</li>
      <li>列表158</li> 
    </ul>
  </div>
</template>

<script>
import NavBar from 'components/common/navbar/NavBar'
import HomeSwiper from './childComps/HomeSwiper.vue'
import RecommendView from './childComps/RecommendView.vue'
import PopInWeek from './childComps/PopInWeek'

import { getHomeMultidata } from 'network/home.js'

export default {
    name:"Home",
    components: {
      NavBar,
      HomeSwiper,
      RecommendView,
      PopInWeek,
    },
    data(){
      return {
        //存储轮播图和下面的数据
        banners: [],
        recommends: []
      }
    },
    created() {
      //1.请求多个数据
      getHomeMultidata().then(res => {
        this.banners = res.data.data.banner.list
        this.recommends = res.data.data.recommend.list
      })
    }
}
</script>


<style scoped>
#home {
  padding-top: 44px;
}
.home-nav {
  background-color: var(--color-tint);
  color: #fff;

  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  z-index: 9;
}
</style>


