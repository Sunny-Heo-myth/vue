
<!-- PLAIN TEXT -->
<template>
  <h2>one room shop</h2>

  <div class="menu">
    <a v-for="a in menu" :key=a>{{ a }}</a>
  </div>

  <!-- product Detail -->
  <div class="rooms" v-for="(product, i) in products" :key="i" :style="roomColor[i]">
    <h4 @click="openModal(i)">{{ product }}</h4>
    <p>{{ price[i] }} $</p>
    <!-- <img :src="imgPath + roomImgUrl[i]" :alt="'Kalynda' + i" class="room-img" @click="actionModal()"> -->
    <p><button @click="roomReportCnt[i]++">report</button> <span>report count: {{ roomReportCnt[i] }}</span></p>
    <p><button @mouseover="countLike(i)">like</button> <span>like coount: {{ roomLikeCnt[i] }}</span></p>


    <div class="black-bg" v-if="isModalOpen[i]" @click="closeModal(i)">
      <div class="white-bg">
        <h4>detail page</h4>
        <p>{{ modalText[i] }}</p>
        <!-- <p><button @click="closeModal(i)">close</button></p> -->
      </div>
    </div>

    <p>---------------------------------------</p>
  </div>

  <!-- <div class="like">
    <h4>likeyyyyy</h4>
  </div> -->
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
      price: [60, 70, 1000],
      roomColor: ['color: red', 'color: blue', 'color: green'],
      roomReportCnt: [0, 0, 0],
      roomLikeCnt: [0, 0, 0],
      imgPath: "file://Users/alan/Downloads/",
      roomImgUrl: [
        "KakaoTalk_Photo_2023-04-16-22-07-20 003.jpeg",
        "KakaoTalk_Photo_2023-04-16-22-07-20 002.jpeg",
        "KakaoTalk_Photo_2023-04-16-22-07-19 001.jpeg"
      ],
      isModalOpen: [false, false, false],
      modalText: [
        "love", "live", "laugh"
      ]
    }
  },

  methods: {
    countLike(i) {
      this.roomLikeCnt[i]++;
      console.log(this.roomLikeCnt[i]);
    },

    openModal(i) {
      // this.closeAllModal();
      this.isModalOpen[i] = true
    },

    closeModal(i) {
      this.isModalOpen[i] = false
    },

    // closeAllModal() {
    //   for (let i = 0; i <= this.isModalOpen.length; i++) {
    //     this.isModalOpen[i] = false;
    //   }
    // }
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

.room-img {
  width: 100%;
  margin-top: 40px;
}

/* How to build animating UI */
/* 0. Design HTML, CSS. */
/* 1. Save current state of UI in data. */
/* 2. Write code of action how UI work by the current state. */

body {
  margin: 0
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
