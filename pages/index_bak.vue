<template>
  <div class="wrap">
    <div class="main_sticky">
      <div class="bone">
        <div ref="imageScroll" class="image_scroll">
          <picture v-for="(item, index) in mainScrollImage" :key="index">
            <img :src="item.imgFileName" />
          </picture>
        </div>
        <div class="main_net flex"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      mainScrollImage: [
        { imgFileName: require('@/assets/images/hero/62.png') },
        { imgFileName: require('@/assets/images/hero/63.png') },
      ],
    }
  },
  created() {
    if (process.browser) {
      this.imagesAnimation()
    }
  },
  methods: {
    imagesAnimation() {
      window.addEventListener('scroll', () => {
        this.mainScrollImage.forEach((e) => {
          console.log(e)
        })
      })
    },
  },
}
</script>
