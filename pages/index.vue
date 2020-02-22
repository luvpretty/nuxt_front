<template>
  <div class="layui-container">
    <div class="layui-row layui-col-space15">
      <div class="layui-col-md8">
        <!-- <imooc-top></imooc-top> -->
        <nuxt-child />
      </div>
      <div class="layui-col-md4">
        <Tips :lists="tips"></Tips>
        <Sign></Sign>
        <HotList :lists="top"></HotList>
        <Ads></Ads>
        <Links :lists="links"></Links>
      </div>
    </div>
  </div>
</template>

<script>
import Tips from '~/components/sidebar/Tips'
import Sign from '~/components/sidebar/Sign'
import HotList from '~/components/sidebar/HotList'
import Ads from '~/components/sidebar/Ads'
import Links from '~/components/sidebar/Links'
// import Top from '~/components/contents/Top'
export default {
  name: 'Index',
  components: {
    Tips,
    Sign,
    HotList,
    Ads,
    Links
    // 'imooc-top': Top
  },
  async asyncData({ $axios }) {
    // tips
    const tipsResult = await $axios.$get('/public/tips')
    // hotlist
    const topResult = await $axios.$get('/public/topWeek')
    // links
    const linksResult = await $axios.$get('/public/links')
    return {
      tips: tipsResult.data || [],
      top: topResult.data || [],
      links: linksResult.data || []
    }
  }
}
</script>

<style></style>
