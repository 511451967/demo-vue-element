<template>
  <div>
    <el-button @click="onAjax">按钮</el-button>
    <el-dialog :visible.sync="visible" title="Hello world">
      <p>欢迎使用 Element</p>
    </el-dialog>
  </div>
</template>

<script>
  import http from '@/libs/http'
  export default {
    name: 'HelloWorld',
    data () {
      return {
        visible: false
      }
    },
    methods: {
      onAjax: function () {
        this.apiGet('index.php?a=index&m=Test&g=Api', {token: '123'}).then((res) => {
          console.log(res)
        })
      }
    },
    mixins: [http]
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
