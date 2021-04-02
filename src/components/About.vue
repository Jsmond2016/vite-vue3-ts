<template>
  <h1>{{ msg }}</h1>
  <el-button type="primary" @click="goBack">回到首页</el-button>
</template>
<script lang="ts">
import { defineComponent, reactive, toRefs } from 'vue'
import { useRouter }  from 'vue-router'
export default defineComponent({
  name: 'About',
  setup() {
    const state = reactive({
      msg: "About"
    })
   
    const history = useRouter()
    const goBack = () => {
      history.push('/home')
    }

    return {
      ...toRefs(state),
      goBack,
    }
  },
})
</script>