<template>
  <div id="scroll-one" class="one">
    <div class="one__title-wrapper">
      <h2 class="one__title">{{ title }}</h2>
      <SVGOneTitle />
    </div>
    <p class="one__text">{{ text }}</p>
    <div class="one__advantages">
      <div
        v-for="(advantage, key) in advantages"
        :key="key"
      >
        <img :src="getImgUrl(advantage.imgPath)" alt="picture">
        <span>{{ advantage.text }}</span>
      </div>
    </div>
  </div>
</template>

<script>
import SVGOneTitle from '@/assets/images/home/meet_title.svg'

export default {
  name: 'One',
  components: {
    SVGOneTitle
  },
  data () {
    return {
      title: 'Meet',
      text: `Vessel is Ruby high-level web crawling framework based on Ferrum for 
        extracting the data you need from websites. It can be used in a wide range 
        of scenarios, like data mining, monitoring or historical archival. 
        For automated testing we recommend Cuprite. Fast as Chrome, dead simple 
        and yet extendable.`,
      advantages: [
        {
          text: 'Fast as Chrome',
          imgPath: '/home/meet_chrome.png'
        },
        {
          text: 'Dead simple',
          imgPath: '/home/meet_simple.png'
        },
        {
          text: 'Extendable',
          // TODO: fix bug with meet_ext.png
          // imgPath: `/home/meet_ext.png`
          imgPath: `/home/meet_chrome.png`
        }
      ]
    }
  },
  methods: {
    /**
     * Get dynamic image path
     * @param {string} imgPath
     * @returns string
     */
    getImgUrl (imgPath) {
      return require('@/assets/images' + imgPath)
    }
  }
}
</script>

<style lang="scss" scoped>
.one {
  padding-bottom: 307px;
  @include sm {
    padding-bottom: 120px;
  }
  &__title-wrapper {
    position: relative;
    display: inline-block;
    svg {
      position: absolute;
      bottom: 16px;
      left: 185px;
      @include sm {
        transform: scale(0.6641);
        bottom: 3px;
        left: 56px;
      }
      @include xs {
        bottom: -3px;
      }
    }
  }
  &__title {
    margin-bottom: 32px;
    @include xs {
      margin-bottom: 24px;
    }
  }
  &__text {
    max-width: 563px;
    line-height: 32px;
    margin-bottom: 95px;
    margin-top: 0;
    @include sm {
      margin-bottom: 35px;
    }
  }
  &__advantages {
    display: flex;
    @include xs {
      flex-direction: column;
      align-items: flex-start;
    }
    div {
      display: flex;
      flex-direction: column;
      margin-right: 160px;
      @include md {
        margin-right: 11.92%;
      }
      @include sm {
        margin-right: 8.48%;
      }
      @include xs {
        margin-right: 0;
        margin-bottom: 34px;
        &:last-child {
          margin-bottom: 0;
        }
      }
      &:last-child {
        margin-right: 0;
      }
    }
    img {
      margin-bottom: 34px;
    }
    span {
      display: inline-block;
      font-size: 24px;
      font-weight: 500;
      margin-top: auto;
      white-space: nowrap;
      @include sm {
        font-size: 20px;
        letter-spacing: -1px;
      }
    }
  }
}
</style>
