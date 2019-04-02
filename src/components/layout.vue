<template>
  <div>
    <vue-ads-layout
      :full-bar="true"
    >
      <vue-ads-bar
        slot="toolbar"
        :fixed="true"
        class="bg-red"
      >
        <div slot="first" class="top-left-nav">
          <vue-ads-hide-button
            :hidden="hiddenLeft"
            @clicked="hideLeft"
            class="hide-button"
          />
          <div>
            <img src="../assets/md-logo.png" alt="logo">
          </div>
        </div>
        <div slot="last" class="top-right-nav">
          123123
        </div>
      </vue-ads-bar>
      <vue-ads-drawer
        slot="left-drawer"
        :fixed="true"
        :minified="minifiedLeft"
        :hidden="hiddenLeft"
        class="bg-yellow"
        @minify="minifyLeft"
        @hide="hideLeft"
      >
        <div slot="top">
          <div class="left-nav">
            <vuescroll :ops="ops">
              <ul>
                <li>1</li>
                <li>2</li>
                <li>3</li>
                <li>4</li>
                <li>5</li>
                <li>6</li>
                <li>7</li>
                <li>8</li>
                <li>9</li>
                <li>10</li>
                <li>11</li>
                <li>12</li>
                <li>13</li>
                <li>14</li>
                <li>15</li>
              </ul>
            </vuescroll>
          </div>
        </div>
        <vue-ads-minify-button
          slot="bottom"
          class="left-bottom"
          :minified="minifiedLeft"
          @clicked="minifyLeft"
        />
      </vue-ads-drawer>
      <div style="background-color: skyblue;height: 400px;">
        <TopBar @tip-color="getMsg" color="red"></TopBar>
      </div>
      <div style="background-color: gray;height: 400px;">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ab accusamus, accusantium, animi aspernatur beatae cupiditate dolor doloribus ducimus, earum eius expedita fugiat harum hic modi molestias pariatur possimus quae quam quod recusandae rerum sapiente sunt tenetur ullam vitae voluptatem voluptates. Aliquam animi at beatae culpa delectus dolore dolorem eum eveniet facilis ipsam iste itaque, maiores maxime molestiae necessitatibus nulla numquam obcaecati odio odit omnis, placeat possimus quae quasi quis quisquam ratione sed sit tempora unde veritatis voluptate voluptates voluptatibus voluptatum? A culpa ea earum labore non porro saepe totam? A aspernatur at blanditiis, dolore facilis libero molestias optio quis voluptatum!
      </div>
      <div style="background-color: palegreen;height: 400px;">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ab accusamus, accusantium, animi aspernatur beatae cupiditate dolor doloribus ducimus, earum eius expedita fugiat harum hic modi molestias pariatur possimus quae quam quod recusandae rerum sapiente sunt tenetur ullam vitae voluptatem voluptates. Aliquam animi at beatae culpa delectus dolore dolorem eum eveniet facilis ipsam iste itaque, maiores maxime molestiae necessitatibus nulla numquam obcaecati odio odit omnis, placeat possimus quae quasi quis quisquam ratione sed sit tempora unde veritatis voluptate voluptates voluptatibus voluptatum? A culpa ea earum labore non porro saepe totam? A aspernatur at blanditiis, dolore facilis libero molestias optio quis voluptatum!
      </div>
      <div style="background-color: slategray;height: 400px;">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ab accusamus, accusantium, animi aspernatur beatae cupiditate dolor doloribus ducimus, earum eius expedita fugiat harum hic modi molestias pariatur possimus quae quam quod recusandae rerum sapiente sunt tenetur ullam vitae voluptatem voluptates. Aliquam animi at beatae culpa delectus dolore dolorem eum eveniet facilis ipsam iste itaque, maiores maxime molestiae necessitatibus nulla numquam obcaecati odio odit omnis, placeat possimus quae quasi quis quisquam ratione sed sit tempora unde veritatis voluptate voluptates voluptatibus voluptatum? A culpa ea earum labore non porro saepe totam? A aspernatur at blanditiis, dolore facilis libero molestias optio quis voluptatum!
      </div>
    </vue-ads-layout>
  </div>
</template>

<script>
import '../../node_modules/@fortawesome/fontawesome-free/css/all.css'
import '../../node_modules/vue-ads-layout/dist/vue-ads-layout.css'
import Vuescroll from 'vuescroll'
import {VueAdsLayout, VueAdsBar, VueAdsDrawer, VueAdsHideButton, VueAdsMinifyButton} from 'vue-ads-layout'
export default {
  name: 'App',

  components: {
    VueAdsMinifyButton,
    VueAdsHideButton,
    VueAdsDrawer,
    VueAdsBar,
    VueAdsLayout,
    Vuescroll
  },

  data () {
    return {
      minifiedLeft: null,
      minifiedRight: false,
      hiddenLeft: null,
      hiddenRight: false,
      ops: {
        vuescroll: {},
        scrollPanel: {},
        rail: {},
        bar: {
          background: '#c1c1c1',
          onlyShowBarOnScroll: false
        }
      }
    }
  },

  methods: {
    minifyLeft (minified) {
      console.log(minified)
      this.minifiedLeft = minified
    },
    hideLeft (hidden) {
      this.hiddenLeft = hidden
    },

    minifyRight (minified) {
      this.minifiedRight = minified
    },

    hideRight (hidden) {
      this.hiddenRight = hidden
    },
    getMsg (params) {
      console.log(params)
    }
  }
}
</script>
<style>
  .top-title{
    height: 64px;
    line-height: 64px;
    color: #333;
    text-align: center;
    background-color: #ddd;
    width: calc(100% - 1px);
  }
  .bg-red{
    background-color: #fff;
    box-shadow: 0 1px 3px 0 rgba(0,0,0,.2);
  }
  .bg-yellow{
    border-right: 1px solid #ddd;
  }
  .left-bottom{
    background: #ddd;
    height: 20px;
    line-height: 20px;
  }
  .left-nav ul{
    padding: 0;
    margin: 0;
  }
  .left-nav{
    height: calc(100vh - 84px);
    overflow: auto;
  }
  .left-nav ul li{
    list-style: none;
    height: 80px;
    line-height: 80px;
  }
  .top-left-nav{
    padding-left: 40px;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .top-left-nav img{
    margin-left: 30px;
    height: 36px;
  }
  .top-right-nav{
    flex: 1111;
    height: 40px;
    background-color: rebeccapurple;
  }
  .hide-button{
    cursor: pointer;
  }
</style>
