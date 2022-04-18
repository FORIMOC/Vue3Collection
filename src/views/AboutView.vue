<template>
  <GlassCard :card_config="card_config"></GlassCard>
</template>
<script>
import GlassCard from "@/components/GlassCard/GlassCard";
export default {
  components: {GlassCard},
  data() {
    return {
      card_config: {
        BlogID: 1,
        Color: 'purple',
        Tag: '前后端',
        Title: 'QQ机器人搭建教学',
        Desc: '前端go-cqhttp原理讲解+实践服务器配置+使用三种语言实现简单Demo',
        Author: 'forimoc',
      }
    }
  }
}
</script>