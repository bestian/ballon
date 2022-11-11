<template>
  <q-page>
    <div v-for="i in list" :key="i.n">
      <div v-show="i.n.indexOf(myKey) > -1 || !myKey">
        <h3>{{i.n}}</h3>
        <iframe width="560" height="315" :src="i.h" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
      </div>
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  props: ['myKey'],
  methods: {
    has(k, l) {
      return l.filter(function (i) {
        return i.n.indexOf(k) > -1 || !k
      })
    }
  },
  data () {
    return {
      list: [
        { n: '頑皮豹', h: 'https://www.youtube.com/embed/-RK04LnHVYk'},        
        { n: '海盜劍', h: 'https://www.youtube.com/embed/9Y8mgHZBYQ4'},        
        { n: '花朵手帶', h: 'https://www.youtube.com/embed/0bwSbwjYWFc'},        
        { n: '貴婦狗', h: 'https://www.youtube.com/embed/n7pDHQ5402A'},        
        { n: '氣球鎗', h: 'https://www.youtube.com/embed/a0O_4q7vIa0'}
      ]
    }
  }
}
</script>
