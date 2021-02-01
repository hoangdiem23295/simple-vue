<template>
  <div class="home">
    <ParentComp text="Data of Component 1" :index="1"/>
    <ParentComp text="Data of Component 2" :index="2"/>
  </div>
</template>

<script>
// @ is an alias to /src
import ParentComp from '@/components/ParentComp.vue'

export default {
  name: 'Home',
  components: {
    ParentComp
  }
}
</script>
<style lang="scss">
  .home {
    & > div {
      margin-bottom: 20px;
    }
  }
</style>