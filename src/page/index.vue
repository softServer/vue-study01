<template>
  <div>
    <Header></Header>
  <h1>page 的index.vue</h1>
    <h2>  这个怎么报错了？</h2>
    <ul>
      <li>vue页尾必须有一个空行</li>
      <li>vue的代码中不能有空行</li>
    </ul>
    <ul>
      <li v-for="(item,index) in list" :key="item.id" @click="showHtml(index)">
        <router-link :to="'/content/' + item.id">
          {{item.title}}
        </router-link>
      </li>
    </ul>
    <Footer></Footer>
    </div>
</template>
<script>
  import Header from '../components/header.vue'
  import Footer from '../components/footer.vue'
  export default {
    components: { Header, Footer },
    created () {
      this.getData()
    },
    data () {
      return {
        list: [],
        content: []
      }
    },
    methods: {
      getData () {
      this.$api.get('topics', null, r => {
        console.log(r)
        this.list = r.data
      })
      },
      showHtml (index) {
        console.log(index)
        this.content[index] = this.list[index].content
      }
    }
  }
</script>
