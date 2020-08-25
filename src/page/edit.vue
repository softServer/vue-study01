<template>
    <div>
      <Uediter :value="ueditor.value" :config="ueditor.config" ref="ue"></Uediter>
      <input type="button" value="显示编辑器内容（从控制台查看）" @click="returnContent">
    </div>
  </template>
  <script>
    import Uediter from '@/components/ue.vue'
    export default {
      components: {Uediter},
      data () {
        return {
          dat: {
            content: ''
          },
          ueditor: {
            value: '编辑器默认文字',
            config: {
          // serverUrl: this.$config.baseUrl + 'ueditor/ueditorConfig',
          serverUrl: 'http://localhost:8090/ueditor/ueditorConfig',
          // 你的UEditor资源存放的路径,相对于打包后的index.html
          UEDITOR_HOME_URL: '/ueditor/',
          // 编辑器不自动被内容撑高
          autoHeightEnabled: false,
          // 工具栏是否可以浮动
          autoFloatEnabled: false,
          // 初始容器高度
          initialFrameHeight: 340,
          // 初始容器宽度
          initialFrameWidth: '100%',
          // 关闭自动保存
          enableAutoSave: false}
          }
        }
      },
      methods: {
        returnContent () {
          this.dat.content = this.$refs.ue.getUEContent()
          console.log(this.dat.content)
        }
      }
    }
  </script>
