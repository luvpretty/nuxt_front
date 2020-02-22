<template>
  <div>
    <dl class="fly-panel fly-list-one">
      <dt class="fly-panel-title">本周热议</dt>
      <dd v-for="(item, index) in lists" :key="'hotlist' + index">
        <nuxt-link to="/">{{ item.title }}</nuxt-link>
        <span><i class="iconfont icon-pinglun1"></i> {{ item.answer }}</span>
      </dd>
    </dl>
  </div>
</template>

<script>
// import { getTop } from '@/api/content'
export default {
  name: 'Hotlist',
  props: {
    lists: {
      type: Array,
      default: () => []
    }
  }
  // data () {
  //   return {
  //     lists: []
  //   }
  // },
  // mounted () {
  //   getTop().then((res) => {
  //     if (res.code === 200) {
  //       this.lists = res.data
  //     }
  //   })
  // }
}
</script>

<style lang="scss" scoped></style>
