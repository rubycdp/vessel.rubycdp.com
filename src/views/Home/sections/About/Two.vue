<template>
  <div class="two">
    <div class="two__title-wrapper">
      <SVGSkillTitleLeft />
      <h2 class="two__title">
        <span>How it all</span><br>
        <span> works</span>
      </h2>
      <SVGSkillTitleRight />
    </div>
    <div class="two__text">
      First Vessel using Ferrum spawns Chrome which goes to one or more
      urls in start_urls, in our case it's only one. After Chrome reports back
      that page is loaded with all the resources it needs the first default callback
      parse is invoked. In the parse callback, we loop through the quote elements
      using a CSS Selector, yield a Hash with the extracted quote text and author
      and look for a link to the next page and schedule another request using the
      same parse method as callback.
    </div>
  </div>
</template>

<script>
import SVGSkillTitleLeft from '@/assets/images/home/skill_title_l.svg'
import SVGSkillTitleRight from '@/assets/images/home/skill_title_r.svg'

export default {
  name: 'Two',
  components: {
    SVGSkillTitleLeft,
    SVGSkillTitleRight
  },
  data () {
    return {
      text: `First Vessel using Ferrum spawns Chrome which goes to one or more 
        urls in start_urls, in our case it's only one. After Chrome reports back 
        that page is loaded with all the resources it needs the first default callback 
        parse is invoked. In the parse callback, we loop through the quote elements 
        using a CSS Selector, yield a Hash with the extracted quote text and author 
        and look for a link to the next page and schedule another request using the 
        same parse method as callback.`
    }
  }
}
</script>

<style lang="scss" scoped>
.two {
  padding-bottom: 242px;
  @include sm {
    padding-bottom: 120px;
  }
  &__title {
    @include sm {
      margin-bottom: 32px;
    }
  }
  &__title-wrapper {
    position: relative;
    display: inline-block;
    margin-bottom: 20px;
    @include sm {
      margin-bottom: 0;
    }
    svg {
      position: absolute;
      bottom: 50%;
      transform: translateY(48%);
      &:first-child {
        left: -74px;
        @include sm {
          transform: scale(0.6641) translate(21px, 72%);
        }
        @include xs {
          left: -75px;
        }
      }
      &:last-child {
        right: -43px;
        bottom: 49%;
        @include sm {
          transform: scale(0.6641) translate(6px, 81%);
        }
        @include xs {
          bottom: 49%;
        }
      }
    }
  }
  &__text {
    max-width: 560px;
    line-height: 32px;
  }
}
</style>
