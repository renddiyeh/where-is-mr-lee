<template>
  <div id="app">
    <div class="bg" :style="bgStyle">
      <div class="main">
        <div class="title">
          <h1>{{ title }}</h1>
          <h3>關注中國社會發展及維權人士的台灣非政府組織工作者李明哲，在2017年3月19日上午從澳門進入中國時失去聯絡...</h3>
        </div>
        <hr>
        <div class="news-wrapper">
          <h2>相關新聞：</h2>
          <ul class="news">
            <li v-for="item in news">
              <a :href="item.url" target="_blank">{{ item.title }}</a>
            </li>
          </ul>
        </div>
        <div class="action">
          <a class="share" :href="fbLink" target="_blank">希望你可以幫忙轉發這消息，運用網路的力量，協助找到李明哲</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BG from './assets/Guangzhou.jpg';

const title = '有人看見李明哲嗎？';
const fbID = '1330773760349289';
const fbParams = {
  app_id: fbID,
  display: 'popup',
  href: '',
};

const fbParamsString = Object.keys(fbParams).map(key => `${key}=${fbParams[key]}&`);

export default {
  name: 'app',
  data() {
    return {
      bgStyle: {
        backgroundImage: `url(${BG})`,
      },
      title,
      news: [
        { title: '共諜案」報復？民進黨前黨工李明哲 傳入境中國失聯', url: 'http://www.storm.mg/article/236333' },
        { title: '民進黨前黨工李明哲失聯？ 陸委會：未接獲陸方通報', url: 'https://udn.com/news/story/1/2355286' },
        { title: '民進黨前黨工李明哲赴陸失蹤　海基會發函海協會協尋', url: 'http://www.nownews.com/n/2017/03/21/2450734' },
      ],
      fbLink: `https://www.facebook.com/dialog/share?${fbParamsString}`,
    };
  },
  head: {
    title: {
      inner: title,
    },
    meta: [
      { property: 'fb:app_id', content: fbID },
      { property: 'og:title', content: title },
    ],
  },
};
</script>

<style>
html, body {
  width: 100%;
  height: 100%;
}

#app {
  font-family: sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  width: 100%;
  height: 100%;

}

.bg::before {
  content: '';
  display: block;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  box-shadow: inset 0 0 10em #333;
  background-color: rgba(0, 0, 0, 0.3);
  position: absolute;
  z-index: 1;
}

.bg {
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: 50% 50%;
  position: relative;
  color: white;
  padding: 1em;
}

a {
  color: white;
}

.main {
  top: 25%;
  z-index: 10;
  position: relative;
}

.title {
  margin-bottom: 2em;
}

.main h1 {
  margin-top: 0;
}

.news-wrapper {
  margin: 2em auto;
}

ul.news li {
  padding: 0.5em 0;
  list-style: none;
}

.action {
  padding-top: 2em;
}

.share {
  border: white 2px solid;
  padding: 2em;
  text-decoration: none;
  transition: background-color 500ms ease-in-out,
    color 500ms ease-in-out;
}

.share:hover {
  background-color: white;
  color: black;
}

</style>
