<template>
  <div id="app">
    <div class="bg" :style="bgStyle"></div>
    <div class="main">
      <div class="title">
        <h1>尋找李明哲</h1>
        <h2>WhereisLee</h2>
        <img :src="pic" alt="李明哲大頭照">
        <h3>關注中國社會發展及維權人士的台灣非政府組織工作者李明哲，在2017年3月19日上午從澳門進入中國時失去聯絡...</h3>
        <h3>A human rights advocate Ming-Che Li is missing after traveling to China via Macau on 19 Mar.2017, sparking concern among family and friends....</h3>
      </div>
      <hr>
      <h2>新聞稿與聲明 Press Release</h2>
        <p class="share"><a href="https://blog.whereislee.org/2017/03/58">李明哲妻李凈瑜最新聲明</a> 2017-03-28 14:00</p>
        <p class="share"><a href="https://blog.whereislee.org/2017/03/14">【採訪通知】尋找李明哲–家屬及民間社團聯合記者會</a> 2017-03-24 10:00</p>
        <p class="share"><a href="https://blog.whereislee.org/2017/03/25">家屬聲明-李明哲妻 李凈瑜</a> 2017-03-24 09:00</p>
        <p style="color: #F08080">由於網站流量過大，如果以上網頁發生異常或無法存取請稍候再試。</p>
        <p style="color: #F08080">Due to heavy traffic on the website, please try again later if you can't access to above pages.</p>
      <hr>
      <div class="news-wrapper">
        <h2>相關新聞 News Articles</h2>
        <ul class="news">
          <li v-for="item in news">
            <a :href="item.url" target="_blank">{{ item.title }}</a>
          </li>
        </ul>
      </div>
      <div class="action">
        <p class="share">希望你可以幫忙轉發這消息，運用網路的力量，協助找到李明哲</p>
        <div class="shareaholic-canvas" data-app="share_buttons" data-app-id="26706199"></div>
        <a class="more" href="//blog.whereislee.org">持續關注</a>
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

export default {
  name: 'app',
  data() {
    return {
      bgStyle: {
        backgroundImage: `url(${BG})`,
      },
      pic,
      news: [
        { title: '美國之音：台湾NGO工作者李明哲被中国国安部门拘留', url: 'http://www.voachinese.com/a/news-taiwan-ngo-arrest-20170328/3784745.html' },
        { title: '中央社：李明哲妻：丈夫被陸國安單位拘留', url: 'http://www.cna.com.tw/news/firstnews/201703285029-1.aspx' },
        { title: 'Missing Taiwanese Man May Be in Chinese Custody, Some Fear: New York Times', url: 'https://www.nytimes.com/2017/03/25/world/asia/taiwan-lee-ming-cheh-missing-china.html' },
        { title: 'Rights advocate missing in China: family, friends: Taipei Times', url: 'http://www.taipeitimes.com/News/front/archives/2017/03/23/2003667298' },
        { title: '朝日新聞：中国で台湾人男性が行方不明に元与党職員', url: 'http://www.asahi.com/articles/ASK3S547NK3SUHBI00S.html' },
        { title: '自由亞洲電台：台北市文山社區大學李明哲已失聯超過34小時', url: 'http://www.rfa.org/mandarin/yataibaodao/gangtai/hx1-03202017104024.html' },
      ],
    };
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
  background-color: rgba(0, 0, 0, 0.4);
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

ul.news {
  padding: 0;
}

ul.news li {
  padding: 0.5em 0;
  list-style: none;
}

.action {
  border: white 2px solid;
  padding: 1em;
  display: inline-block;
  font-size: 1.2em;
}

@media (min-width: 40em) {
  .action {
    padding: 2em 3em;
  }
}

.more {
  display: inline-block;
  margin-top: 1em;
  padding: 1em 2em;
  border: 1px solid white;
  text-decoration: none;
  background-color: white;
  color: black;
  transition: all 0.5s ease;
}

.more:hover,
.more:active {
  background-color: transparent;
  font-weight: bold;
  color: white;
  transform: scale(1.1);
}

#disqus_thread {
  margin: 2em auto;
  padding: 2em;
  background-color: rgba(255, 255, 255, 0.6);
}

</style>
