<template>
  <div id="discount">
    <div class="discountContent">
      <div class="discountHeader">
        <div>
          <!--特別優惠標題-->
          <h2>{{header}}</h2>
        </div>
        <!--使用v-if的地區按鈕-->
        <!--pageNum頁碼為0 areaFilter設定要篩選的地區-->
        <ul id="area">
          <li
            class="area cursor"
            v-for="(area,i) in areas"
            :key="i"
            @click="() => {
              areaFilter = area.region;
              pageNum = 0;
            }"
          >{{area.region}}</li>
        </ul>
      </div>
      <div class="discountImg">
        <ul id="photo">
          <!--優惠地區圖片加文字-->
          <li v-for="(photo,i) in photosShowed" :key="i">
            <div class="imgStyle">
              <img v-bind:src="photo.imgSrc" />
            </div>
            <h4>{{photo.title}}</h4>
            <span style="font-size: 13px;">{{photo.price}}{{photo.twd}}</span>
            <span class="amount">{{photo.amount}}</span>
            <p class="economyClass">{{photo.p}}</p>
            <p>
              {{photo.p1}}
              <br />
              <i class="fas fa-shield-alt" style="color: #ff922b;"></i>
              {{photo.br}}
              <br />
              {{photo.br1}}
            </p>
            <a class="dataStyle" v-bind:href="photo.href">{{photo.content}}</a>
          </li>
        </ul>
      </div>
      <!--更多優惠按鈕-->
      <div id="moreDiscount">
        <p class="dataStyle cursor">
          <i class="fas fa-fan" style="color: #ff922b;"></i>更多優惠價格
        </p>
      </div>
      <!--分頁按鈕-->
      <div class="changePhto">
        <div class="changeContent">
          <!--計算photosFiltered有多少,除以一頁有3個-->
          <button
            class="cursor"
            v-for="i in totalPages"
            :key="i - 1"
            @click="ButtononClick(i - 1);"
            v-bind:class="{changeColor: pageNum === i - 1}"
          ></button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Discount",
  data: function() {
    return {
      header: "特別優惠",
      pageNum: 0,
      photoPerPage: 3,
      areas: [
        {
          region: "全部"
        },
        {
          region: "香港澳門"
        },
        {
          region: "中國大陸"
        },
        {
          region: "東南亞"
        },
        {
          region: "東北亞"
        },
        {
          region: "美洲"
        },
        {
          region: "歐洲"
        },
        {
          region: "紐澳"
        }
      ],
      areaFilter: "全部",
      photos: [
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 東京(成田)",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "8,160",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/19~",
          br: "截止時間 : 2021/04/30",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "香港澳門"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 布里斯本",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "13,300",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/19~",
          br: "截止時間 : 2021/04/30",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "中國大陸"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 宿霧",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "7,008",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/19~",
          br: "截止時間 : 2021/04/30",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "香港澳門"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 名古屋",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "7,488",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 即日起~2020/05/31",
          br: "截止時間 : 2021/05/31",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "東北亞"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 曼谷",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "5,280",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/19~",
          br: "截止時間 : 2021/04/30",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "美洲"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 阿姆斯特丹",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "22,800",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/19~",
          br: "截止時間 : 2021/04/30",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "歐洲"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 大阪",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "6,528",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/19~",
          br: "截止時間 : 2021/04/30",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "紐澳"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 香港",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "4,066",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/19~",
          br: "截止時間 : 2021/04/30",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "香港澳門"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 首爾(仁川)",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "5,376",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/19~",
          br: "截止時間 : 2021/04/30",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "中國大陸"
        },

        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 巴黎",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "26,125",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/19~",
          br: "截止時間 : 2021/04/30",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "東南亞"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 洛杉磯",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "21,632",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/18~",
          br: "截止時間 : 2021/04/30",
          br1: "*(含稅)",
          href: "",
          content: "詳細預定資料",
          region: "東北亞"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 舊金山",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "21,632",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/18~",
          br: "截止時間 : 2021/04/30",
          br1: "*(含稅)",
          href: "",
          content: "詳細預定資料",
          region: "美洲"
        },

        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 西雅圖",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "24,992",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/18~",
          br: "截止時間 : 2021/04/30",
          br1: "*(含稅)",
          href: "",
          content: "詳細預定資料",
          region: "歐洲"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 北京",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "8,832",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/19~",
          br: "截止時間 : 2021/04/30",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "紐澳"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 峇里島",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "11,808",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/19~",
          br: "截止時間 : 2021/04/30",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "香港澳門"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 澳門",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "4,598",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/19~",
          br: "截止時間 : 2021/04/30",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "中國大陸"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 溫哥華",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "18,930",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/18~",
          br: "截止時間 : 2021/04/30",
          br1: "*(含稅)",
          href: "",
          content: "詳細預定資料",
          region: "東南亞"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 維也納",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "26,125",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/19~",
          br: "截止時間 : 2021/04/30",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "東北亞"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 倫敦",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "22,800",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/19~",
          br: "截止時間 : 2021/04/30",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "美洲"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 浦東",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "5,952",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/19~",
          br: "截止時間 : 2021/04/30",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "歐洲"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 虹橋",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "8,256",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/19~",
          br: "截止時間 : 2021/04/30",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "紐澳"
        },

        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 成都",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "10,080",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/19~",
          br: "截止時間 : 2021/04/30",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "香港澳門"
        },
        {
          imgSrc: "https://source.unsplash.com/user/erondu/278x278",
          title: "桃園 - 廈門",
          price: "最低售價(起)",
          twd: "TWD",
          amount: "4,320",
          p: "來回 / 經濟艙",
          p1: "適用出發日 : 2020/05/19~",
          br: "截止時間 : 2021/04/30",
          br1: "*(未稅)",
          href: "",
          content: "詳細預定資料",
          region: "中國大陸"
        }
      ]
    };
  },
  methods: {
    //分頁按鈕
    ButtononClick(index) {
      this.pageNum = index;
    }
  },
  computed: {
    photosFiltered() {
      if (this.areaFilter === "全部") {
        return this.photos;
      } else {
        return this.photos.filter(photo => photo.region === this.areaFilter);
      }
    },
    photosShowed() {
      return this.photosFiltered.slice(
        this.photoPerPage * this.pageNum,
        this.photoPerPage * (this.pageNum + 1)
      );
    },
    totalPages() {
      return Math.round(this.photosFiltered.length / this.photoPerPage);
    }
  }
};
</script>

<style>
.area {
  font-size: 14px;
  border-left: 1px solid gray;
  list-style-type: none;
  padding: 0px 20px;
}
.area:first-child {
  border: none;
}
.area:hover {
  color: #4c806e;
}
.discountHeader h2 {
  text-align: center;
  font-size: 25px;
  font-weight: bold;
  padding-top: 30px;
}
.discountImg {
  display: flex;
  justify-content: center;
}
.imgStyle {
  margin-bottom: 20px;
}
.imgStyle img {
  border-radius: 30px;
}
.amount {
  font-weight: bold;
  font-size: 30px;
  color: black;
  margin-left: 20px;
}
.economyClass {
  margin: 5px;
}
.changeContent {
  text-align: center;
}
.changeContent > button {
  border: 2px black none;
  background: #cccccc;
  height: 15px;
  width: 15px;
  margin: 40px 5px 20px 5px;
}
.dataStyle {
  font-size: 14px;
  text-decoration: underline;
  color: black;
}
.changeContent > .changeColor {
  background: #ff922b;
}
#area {
  display: flex;
  justify-content: center;
  padding: 10px;
}
#photo {
  display: flex;
  list-style-type: none;
  padding: 0px;
}
#photo li {
  margin: 20px;
  text-align: center;
  color: gray;
}
#photo li > h4 {
  font-size: 15px;
  color: black;
}
#photo p {
  font-size: 13px;
}

#photo a:hover {
  text-decoration: none;
  color: black;
}
#discount {
  background: #f3efea;
}
#moreDiscount p {
  text-align: center;
  margin-left: 800px;
}
#moreDiscount p:hover {
  text-decoration: none;
}
</style>