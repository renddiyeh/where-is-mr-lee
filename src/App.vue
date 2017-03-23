<template>
  <div id="app">
    <div class="bg" :style="bgStyle"></div>
    <div class="main">
      <div class="title">
        <img :src="pic" alt="李明哲大頭照">
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
        <p class="share">希望你可以幫忙轉發這消息，運用網路的力量，協助找到李明哲</p>
        <div class="shareaholic-canvas" data-app="share_buttons" data-app-id="26706199"></div>
      </div>
      <div id="disqus_thread"></div>
    </div>
  </div>
</template>

<script>
import BG from './assets/Guangzhou.jpg';
import pic from './assets/pic.jpg';

(() => {
  const d = document;
  const s = d.createElement('script');
  s.src = 'https://where-is-lee.disqus.com/embed.js';
  s.setAttribute('data-timestamp', +new Date());
  (d.head || d.body).appendChild(s);
})();

const title = '有人看見李明哲嗎？';
const fbID = '1330773760349289';
const fbParams = {
  app_id: fbID,
  display: 'popup',
  href: 'https://whereislee.org',
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
      pic,
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
  box-shadow: inset 0 0 10em rgba(0, 0, 0, 0.8);
  background-color: rgba(0, 0, 0, 0.8);
  position: absolute;
  z-index: 1;
}

.bg {
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: 50% 50%;
  position: fixed;
  color: white;
  padding: 1em;
}

a {
  color: white;
}

.main {
  top: 15%;
  z-index: 10;
  position: relative;
  color: white;
  max-width: 50em;
  padding: 0 1em;
  margin: 0 auto;
}

.title {
  margin-bottom: 2em;
  line-height: 1.8;
}

.title img {
  width: 33%;
  max-width: 20em;
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
  border: white 2px solid;
  padding: 2em;
  display: inline-block;
}

#disqus_thread {
  margin: 2em auto;
  padding: 2em;
  background-color: rgba(255, 255, 255, 0.6);
}

</style>
