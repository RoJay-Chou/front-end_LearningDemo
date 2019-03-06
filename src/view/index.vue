<template>
  <div>
    <ul>
      <li v-for="item in data" :key="item.id">
        <leftSlider @msg-from-child="getMsgFromChild(item)">
          <div>
            <p>哈哈这是一个标题:{{item.text}}-----{{item.id}}</p>
          </div>
        </leftSlider>
      </li>
    </ul>
  </div>
</template>
<script>
import leftSlider from '../components/HelloWorld'
export default{
  components: {
    leftSlider
  },
  data () {
    return {
      data: [{
        text: '苹果',
        id: 1
      }, {
        text: '香蕉',
        id: 2
      }, {
        text: '橘子',
        id: 3
      }, {
        text: '菠萝',
        id: 4
      }, {
        text: '哈密瓜',
        id: 5
      }]
    }
  },
  methods: {
    getMsgFromChild (v) {
      this.data.splice(v, 1)
    }
  }
}
</script>
<style>
  
</style>