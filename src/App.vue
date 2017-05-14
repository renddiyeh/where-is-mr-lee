<template>
  <div id="app">
    <div class="bg" :style="bgStyle"></div>
    <div class="main">
      <div class="title">
        <h1>李明哲無罪·釋放李明哲</h1>
        <h2>Release Lee</h2>
        <img :src="pic" alt="李明哲大頭照">
        <h3>關注中國社會發展及維權人士的台灣非政府組織工作者李明哲，在2017年3月19日上午從澳門進入中國時遭當局以違反國家安全名義拘留。</h3>
        <h3>A human rights advocate Lee Ming-cheh has been detained after traveling to China via Macau on 19 Mar.2017, China claimed they are investigating him on suspicion of "pursuing activities harmful to national security".</h3>
        <h4><a href="https://blog.whereislee.org/whoislee">誰是李明哲？ Who is Ming-Che Li?</a></h4>
      </div>
      <hr>
      <h2>新聞稿與聲明 Press releases and statements</h2>
        <!--<p class="share"><a href="/static/lmj_20161217_recording.zip">錄音檔/李明哲20161217-相同皮膚下的鴻溝</a> 2017-03-29 15:10</p>-->
        <p class="share"><a href="https://blog.whereislee.org/2017/05/133">「李明哲國際救援⼩組」⾏前聲明</a> 2017-04-12 16:00</p>
        <p class="share"><a href="https://blog.whereislee.org/2017/04/120">李明哲妻  李凈瑜回覆國台辦聲明</a> 2017-04-12 16:00</p>
        <p class="share"><a href="https://blog.whereislee.org/2017/04/117">李明哲妻李凈瑜給台灣人民的一封信 (Eng. available)</a> 2017-04-10 20:00</p>
        <p class="share"><a href="https://blog.whereislee.org/2017/04/110">李明哲妻李凈瑜於桃園國際機場聲明 (Eng. available)</a> 2017-04-10 11:00</p>
        <p class="share"><a href="https://blog.whereislee.org/2017/04/108">李明哲妻李凈瑜回覆國台辦聲明 (Eng. available)</a> 2017-04-09 21:20</p>
        <p class="share"><a href="https://blog.whereislee.org/2017/04/100">李明哲妻李凈瑜聲明</a> 2017-04-04 14:00</p>
        <p class="share"><a href="https://blog.whereislee.org/2017/03/95">圖片/李明哲妻 李凈瑜聲明</a> 2017-03-31 15:30</p>
        <p class="share"><a href="https://blog.whereislee.org/2017/03/91">李凈瑜新聞稿</a> 2017-03-31 15:00</p>
        <p class="share"><a href="https://blog.whereislee.org/2017/03/80">李明哲妻李凈瑜聲明</a> 2017-03-29 14:00</p>
        <p class="share"><a href="https://blog.whereislee.org/2017/03/58">李明哲妻李凈瑜最新聲明</a> 2017-03-28 14:00</p>
        <p class="share"><a href="https://blog.whereislee.org/2017/03/25">家屬聲明-李明哲妻 李凈瑜</a> 2017-03-24 09:00</p>
        <p style="color: #F08080">由於網站流量過大，如果以上網頁發生異常或無法存取請稍候再試。</p>
        <p style="color: #F08080">Due to heavy traffic on the website, please try again later if you can't access to above pages.</p>
      <hr>
      <h2>國際聲援與行動 Statements from others</h2>
        <h3><a href="http://www.tahr.org.tw/node/1806" target="_new">Free Li Ming-Che! The Joint Statement from NGOs</a></h3>
        <h3><a href="https://www.amnesty.tw/petition/2453" target="_new">個人連署/國際特赦組織：【緊急救援】李明哲在哪裡？ 聲援遭中國拘留的台灣社區大學工作者</a></h3>
        <p class="share"><a href="https://www.amnesty.org/en/latest/news/2017/03/china-release-taiwan-ngo-worker/">Amnesty International:China: Taiwan NGO worker detained on vague national security charges</a></p>
        <p class="share"><a href="https://blog.whereislee.org/2017/03/73">Quotes from Human Rights Watch</a>
        <p class="share"><a href="https://blog.whereislee.org/2017/03/73">Frontline Defenders: Lee Ming-cheh detained by Chinese authorities</a>
      <hr>
      <div class="news-wrapper">
        <h2>國際報導 International News Coverage</h2>
        <ul class="news">
          <li v-for="item in news">
            <a :href="item.url" target="_blank">{{ item.title }}</a>
          </li>
        </ul>
      </div>
      <div class="action">
        <h3>您也可以幫忙尋找李明哲！</h3>
        <p class="share">1. 你可以選擇喜歡的社群工具轉發這消息，運用網路的力量，協助李明哲早日回家</p>
        <div class="shareaholic-canvas" data-app="share_buttons" data-app-id="26706199"></div>
        <p class="share">2. 你也可以對事件粉絲團按讚來追蹤事件，以獲得最新訊息</p>
        <div class="fb-page" data-href="https://www.facebook.com/whereislee.org/" data-tabs="timeline" data-height="70" data-small-header="true" data-adapt-container-width="true" data-hide-cover="true" data-show-facepile="false"><blockquote cite="https://www.facebook.com/whereislee.org/" class="fb-xfbml-parse-ignore"><a href="https://www.facebook.com/whereislee.org/">尋找李明哲</a></blockquote></div>
        <p><a class="more" href="//blog.whereislee.org">事件部落格</a></p>
      </div>
      <!--<div id="disqus_thread"></div>-->
    </div>
  </div>
</template>

<script>
import BG from './assets/Guangzhou.jpg';
import pic from './assets/pic_new.jpg';

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
        { title: '自由亞洲電台：台湾人权团体召开“释放李明哲”记者会 境内外媒体塞爆会场', url: 'http://www.rfa.org/mandarin/yataibaodao/gangtai/hx-03292017113234.html' },
        { title: 'TIME: Wife of Taiwanese Rights Activist Detained in China Speaks Out About His Disappearance', url: 'http://time.com/4716175/taiwan-missing-activist-china/' },
        { title: 'The Guardian: China says it has detained Taiwanese activist missing since 19 March', url: 'https://www.theguardian.com/world/2017/mar/29/missing-taiwanese-human-rights-activist-detained-by-china' },
        { title: 'New York Times: China Says It Has Detained Rights Activist From Taiwan', url: 'https://www.nytimes.com/2017/03/29/world/asia/china-taiwan-activist-lee-ming-cheh.html?_r=0' },
        { title: 'Reuters: Tell us the charges or free Taiwan activist, Taipei tells Beijing', url: 'http://www.reuters.com/article/us-china-taiwan-idUSKBN170084?il=0' },
        { title: 'ABC News: China confirms detention of Taiwan pro-democracy activist', url: 'http://abcnews.go.com/International/wireStory/taiwan-democracy-activist-detained-china-46416241' },
        { title: 'Aljazeera: Missing Taiwan activist allegedly detained in China', url: 'http://www.aljazeera.com/news/2017/03/missing-taiwan-activist-allegedly-detained-china-170328144407417.html' },
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
  margin-bottom: 4em;
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
