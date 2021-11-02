<template>
  <swiper
      :mousewheel="true"
      class="swiper-con"
      direction="vertical"
      :pagination="true"
  >
    <swiper-slide :style="{background: item.color}"
                  v-for="item in d"
                  class="slides">
      <div class="gh">
        <h1>
          {{ item.name }}
        </h1>
      </div>

    </swiper-slide>
  </swiper>
</template>
<script>
import {Swiper, SwiperSlide} from 'swiper/vue';
import SwiperCore, {Mousewheel, Pagination} from "swiper";
import "swiper/swiper-bundle.min.css";

SwiperCore.use([Mousewheel, Pagination])

export default {
  name: "Swiperr",
  components: {
    Swiper,
    SwiperSlide
  },
  data() {
    return {
      d: [
        {name: 'one', color: '#2F86A6'},
        {name: 'two', color: '#B91646'},
        {name: 'three', color: '#CEE5D0'},
        {name: 'four', color: '#FF5DA2'},
        {name: 'five', color: '#88E0EF'}
      ]
    }
  }
}
</script>

<style lang="scss">
.swiper-con {
  width: 100%;
  height: 100vh;
}
.slides {
  font-size: 150px;
  color: white;
  font-family: Roboto, sans-serif;
  font-weight: 700;
  @media(max-width: 650px){
      font-size: 95px;
  }
  @media(max-width: 450px){
      font-size: 79px;
  }
}

.gh {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
}
.swiper-pagination-bullet {
  width: 34px;
  height: 34px;
}
.swiper-pagination-bullet-active {
  background: pink;
}

</style>