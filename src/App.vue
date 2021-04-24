<template>
  <div class="container">
    <global-header :user="currentUser"></global-header>
    <router-view></router-view>
    <footer class="text-center py-4 text-secondary bg-light mt-6">
      <small>
        <ul class="list-inline mb-0">
          <li class="list-inline-item">© 2021 者也专栏</li>
          <li class="list-inline-item">课程</li>
          <li class="list-inline-item">文档</li>
          <li class="list-inline-item">联系</li>
          <li class="list-inline-item">更多</li>
        </ul>
      </small>
    </footer>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import 'bootstrap/dist/css/bootstrap.min.css'
import GlobalHeader, { UserProps } from './components/GlobalHeader.vue'
const currentUser: UserProps = {
  isLogin: false
}
export default defineComponent({
  name: 'App',
  components: {
    GlobalHeader
  },
  setup() {
    const emailval = ref()
    const passwordval = ref()
    const onFormSubmit = (result: boolean) => {
      console.log('xxm', result)
    }
    return {
      currentUser,
      emailval,
      passwordval,
      onFormSubmit
    }
  }
})
</script>

<style></style>
