<template>
  <div id="featuredOffers">
    <div class="featuredHeader">
      <h5>精選項目</h5>
    </div>
    <ul id="featuredPhoto">
      <li v-for="(feature, i) in features[pageNum]" :key="i" class="featuredPhoto">
        <div>
          <img v-bind:src="feature.imgSrc" />
        </div>
        <div>
          <a class="featuredPhotoStyle displayStyle" v-bind:href="feature.href">{{ feature.title }}</a>
        </div>
        <div>
          <h5 class="featuredPhotoStyle">{{ feature.description }}</h5>
        </div>
      </li>
    </ul>
    <div id="exchangeDirectory">
      <div id="exchangeContent">
        <button
          class="cursor"
          v-for="(feature, index) in features"
          v-bind:key="index"
          @click="handleButtonClick(index)"
          v-bind:class="{changeButtonColor:ischangeButtonColor ==index}"
        ></button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Featuredoffers",
  data: function() {
    return {
      pageNum: 0,
      ischangeButtonColor: "",
      features: [
        [
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "長榮假期 ! 即訂即開 想飛就飛",
            description:
              "帶您FUN心玩世界！機票酒店線上下單、專人服務，我們用心款待您每一趟夢想之旅！"
          },
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title:
              "歡迎登入「空中仁醫 Compassionate Doctors on Board」申請專頁",
            description:
              "歡迎在台灣執業的醫師們一起加入「空中仁醫 /Compassionate Doctors on Board」專案。"
          },
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "艙位升等優惠活動-艙位升等最優3,750哩起，舒適旅行好愜意！",
            description: "會員限定!艙位升等至豪華經濟艙只要3,750哩起！"
          },
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "哩程累計優惠活動-搭機最高加贈2,500哩!讓EVA和你一起去旅行!",
            description: "購票享好哩，最高2,500哩屬於你!"
          }
        ],
        [
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "網路投保旅平險投保抽RIMOWA登機箱",
            description:
              "透過富邦產險網路投保旅平險，享優惠、超便利、出發前一小時投保即生效，用手機也能投保唷!投保後即可享有抽獎資格。"
          },
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "擔心害怕票價錯過就不在? 我們幫您保留72小時!",
            description:
              "明明機位有限，朋友卻三推四請也不給個明確的答覆嗎? 現在起，你有更輕鬆的方式來計劃你的行程!"
          },
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "美國運通長榮航空簽帳金卡 國內外刷卡都加碼！",
            description:
              "首年免年費，免登錄，首三個月最優10元1哩，額外最高可獲10萬哩！"
          },
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "降哩換票真好康，最多現省20,000哩!",
            description: "降哩換票趁現在，優惠航線最多現省20,000哩！"
          }
        ],
        [
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "西雅圖 最夢幻的飛行",
            description: "全面升等的雲端體驗"
          },
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "國泰世華長榮航空聯名卡購票最高9折 (限台灣地區出發)",
            description:
              "依活動辦法至長榮航空全球資訊網信用卡專區，購買長榮/立榮航空實際營運之國際航線機票，立享票價最高9折!"
          },
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "會員酬賓新禮遇",
            description:
              "無限萬哩遊會員酬賓新禮遇，搭越多、累計越多、優惠多更多!"
          },
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title:
              "美國運通長榮航空簽帳白金卡 /金卡專屬優惠 (限台灣地區出發機票適用)",
            description:
              "活動期間依辦法至長榮航空全球資訊網購買長榮/立榮航空實際營運之國際航線即享商務艙九折優惠！"
          }
        ],
        [
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "立即拿出您的信用卡，享受卡友獨享優惠吧!",
            description:
              "自即日起，長榮航空網路購票正式推出信用卡優惠專區，立即拿出您的信用卡，享受卡友獨享優惠吧!"
          },
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "輕鬆買，實在省!",
            description:
              "您可於長榮航空官方網站享有九折優惠預先購買超額行李，滿足您的旅程需求!"
          },
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "PDF時刻表",
            description: "提供長榮/立榮航空國際線時刻表 (PDF檔案)下載服務"
          },
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "網路訂房",
            description:
              "長榮航空與線上訂房專家Agoda.com攜手合作，不論商務或是休閒出遊，提供全世界超過75萬個住宿選項。"
          }
        ],
        [
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "【長榮航空】KLOOK全站商品95折",
            description:
              "即日起至2020年12月31日23:59前，結帳輸入頁面指定優惠碼，享KLOOK全站商品95折優惠。"
          },
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "GLOBAL WiFi 專屬優惠",
            description:
              "優惠一、輸入航班號碼最高享7折+來回免運。優惠二、使用指定連結進行預約，日本吃到飽機種85元/日起。"
          },
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "HERTZ租車優惠",
            description:
              "全球租車享有10%折扣。無限萬哩遊會員可額外賺取高達2,000獎勵哩程。"
          },
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "國泰世華長榮航空聯名卡帶您看見不一樣的人生風景",
            description:
              "首刷最高刷NT$5萬即得50,000哩，消費最優NT$10=1哩，消費集哩就是快！長榮官網購票立享最高9折！"
          }
        ],
        [
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "HERTZ租車優惠",
            description:
              "全球租車享有10％折扣。無限萬哩遊會元可額外賺取高達2,000獎勵哩程。"
          },

          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "國泰世華長榮航空聯名卡帶您看見不一樣的人生風景",
            description:
              "首刷最高刷NT$5萬即得50,000哩，消費最優NT$10=1哩，消費集哩就是快 ! 長榮官網購票立享最高9折!"
          },
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "美國運通長榮航空簽帳白金卡 金屬版璀璨上市",
            description:
              "首刷不限金額即享50,000哩，消費累積哩程享升等禮遇，再享全球1,200間機場貴賓室及1,000間精選酒店住房優惠"
          },
          {
            imgSrc: "https://source.unsplash.com/user/erondu/231x200",
            href: "",
            title: "長榮假期 ! 即訂即開 想飛就飛",
            description:
              "帶您FUN心玩世界！機票酒店線上下單、專人服務，我們用心款待您每一趟夢想之旅！"
          }
        ]
      ]
    };
  },
  methods: {
    handleButtonClick(index) {
      this.pageNum = index;
      this.ischangeButtonColor = index;
    }
  }
};
</script>

<style>
.featuredHeader h5 {
  text-align: center;
  font-weight: bolder;
  margin: 20px 0px;
}
.featuredPhotoStyle {
  font-size: 17px;
  color: black;
}
#featuredPhoto {
  display: flex;
  list-style-type: none;
  width: 900px;
  margin: 0px auto;
  padding: 0px;
}
#featuredPhoto li {
  margin: 5px 5px;
}
#featuredPhoto li img {
  margin-bottom: 10px;
}
.displayStyle:hover {
  color: #4c806e;
}
#featuredPhoto li h5 {
  margin-top: 18px;
  font-size: 14px;
}
#exchangeContent {
  display: flex;
  justify-content: center;
}
#exchangeContent button {
  border: 2px black none;
  background: #cccccc;
  height: 15px;
  width: 15px;
  margin: 40px 5px 20px 5px;
}
#exchangeContent > .changeButtonColor {
  background: #ff922b;
}
</style>
