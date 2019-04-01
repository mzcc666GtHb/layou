<template>
  <div>
    <vue-ads-layout
      :full-bar="false"
    >
      <vue-ads-bar
        slot="toolbar"
        :fixed="true"
        class="bg-red"
      >
        <vue-ads-hide-button
          slot="first"
          :hidden="hiddenLeft"
          @clicked="hideLeft"
        />
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
          <div class="top-title">
            logo
          </div>
          <div class="left-nav">
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
          </div>
        </div>
        <vue-ads-minify-button
          slot="bottom"
          class="left-bottom"
          :minified="minifiedLeft"
          @clicked="minifyLeft"
        />
      </vue-ads-drawer>

      My content

    </vue-ads-layout>
  </div>
</template>

<script>
import '../../node_modules/@fortawesome/fontawesome-free/css/all.css'
import '../../node_modules/vue-ads-layout/dist/vue-ads-layout.css'

import {VueAdsLayout, VueAdsBar, VueAdsDrawer, VueAdsHideButton, VueAdsMinifyButton} from 'vue-ads-layout'

export default {
  name: 'App',

  components: {
    VueAdsMinifyButton,
    VueAdsHideButton,
    VueAdsDrawer,
    VueAdsBar,
    VueAdsLayout
  },

  data () {
    return {
      minifiedLeft: null,
      minifiedRight: false,
      hiddenLeft: null,
      hiddenRight: false
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
    background-color: #3284ef;
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
</style>
