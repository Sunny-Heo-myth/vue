
<!-- PLAIN TEXT -->
<template>
  <h2>one room shop</h2>

  <div class="menu">
    <a v-for="a in menu" :key=a>{{a}}</a>
  </div>

  <div class="rooms">
    <h4 v-for="(product, i) in products" :key="i" :style="roomColor[i]">{{product}}
      <p>{{ price[i] }} $</p>
      <p><button @click="roomReportCnt[i]++">report</button> <span>report count: {{ roomReportCnt[i] }}</span></p>
      <p><button @mouseover="countLike(i)">like</button> <span>like coount: {{ roomLikeCnt[i] }}</span></p>
      <p>---------------------------------------</p>
    </h4>
  </div>

  <div class="like">
    <h4>likeyyy</h4>
    
  </div>

</template>



<!-- JAVASCRIPT -->
<script>

export default {
  name: 'App',
  data() {
    return {
      // all data goes in here
      menu: ['home', 'shop', 'about'],
      room: ['room1', 'room2', 'room3'],
      products: ['Yeoksam', 'Cheonho', 'Mapo'],
      price: [60, 70, 80],
      roomColor: ['color: red', 'color: blue', 'color: green'],
      roomReportCnt: [0, 0, 0],
      roomLikeCnt: [0, 0, 0]
    }
  },
  methods: {
    countLike(i) {
      this.roomLikeCnt[i]++;
      console.log(this.roomLikeCnt[i]);
    }
  },
  components: {
    
  }
}

</script>



<!-- STYLE -->
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
 color: white;
 padding: 10px;
}

</style>
