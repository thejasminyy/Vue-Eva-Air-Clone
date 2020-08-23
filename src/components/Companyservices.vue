<template>
  <!--公司服務詳細內容-->
  <div id="companyServices">
    <div class="servicesContent">
      <section>
        <nav role="navigation">
          <ul class="service">
            <li>
              <p>關於我們與顧客服務</p>
            </li>
            <li>
              <a href>關於我們</a>
            </li>
            <li>
              <a href>公司簡介</a>
            </li>
            <li>
              <a href>企業社會責任專區</a>
            </li>
            <li>
              <a href>公司治理專區</a>
            </li>
            <li>
              <a href>投資人專區</a>
            </li>
            <li>
              <a href>利害關係人專區</a>
            </li>
            <li>
              <a href>常見問答</a>
            </li>
            <li>
              <a href>與我聯絡</a>
            </li>
            <li>
              <a href>資訊安全政策</a>
            </li>
          </ul>
        </nav>
      </section>
      <section>
        <nav role="navigation">
          <ul class="service">
            <li>
              <p>網站聲明與規範</p>
            </li>
            <li>
              <a href>網站導覽</a>
            </li>
            <li>
              <a href>行動方案</a>
            </li>
            <li>
              <a href>顧客承諾與機坪延遲應變計畫</a>
            </li>
            <li>
              <a href>運送條款</a>
            </li>
            <li>
              <a href>隱私保護與Cookie使用</a>
            </li>
            <li>
              <a href>網路安全自我保護</a>
            </li>
            <li>
              <a href>智慧財產權</a>
            </li>
          </ul>
        </nav>
      </section>
      <section>
        <nav role="navigation">
          <ul class="service">
            <li>
              <p>相關網站及服務功能</p>
            </li>
            <li>
              <a href>Hello Kitty彩繪機</a>
            </li>
            <li>
              <a href>長榮假期</a>
            </li>
            <li>
              <a href>國內航線(立榮航空)</a>
            </li>
            <li>
              <a href>機上免稅品/樂e購</a>
            </li>
            <li>
              <a href>貨運全球資訊網</a>
            </li>
            <li>
              <a href>EVA Wi-Fi</a>
            </li>
            <li>
              <a href>企業會員網路購票</a>
            </li>
            <li>
              <a href>企業會員網站</a>
            </li>
            <li>
              <a href>長榮航空城市觀光半程馬拉松</a>
            </li>
            <li>
              <a href>空中仁醫申請</a>
            </li>
          </ul>
        </nav>
      </section>
      <section>
        <nav role="navigation">
          <ul class="service">
            <li>
              <p>熱門航點</p>
            </li>
            <li>
              <a href>所有航點</a>
            </li>
            <li>
              <a href>從台灣出發</a>
            </li>
            <li>
              <a href>從台北出發</a>
            </li>
            <li>
              <a href>到東京</a>
            </li>
            <li>
              <a href>到香港</a>
            </li>
            <li>
              <a href>到首爾</a>
            </li>
          </ul>
        </nav>
      </section>
      <section>
        <nav role="navigation">
          <ul class="service">
            <li>
              <p>歡迎加入我們</p>
            </li>
            <li class="cursor">
              <img src="https://source.unsplash.com/user/erondu/32x32" />
              <img src="https://source.unsplash.com/user/erondu/32x32" />
              <img src="https://source.unsplash.com/user/erondu/32x32" />
              <img src="https://source.unsplash.com/user/erondu/32x32" />
              <img src="https://source.unsplash.com/user/erondu/32x32" />
            </li>
          </ul>
        </nav>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  name: "Companyservices"
};
</script>

<style>
.servicesContent {
  display: flex;
  justify-content: center;
}
.servicesContent section {
  padding: 0 1.538em;
  width: 15.76em;
}
.servicesContent ul {
  list-style-type: none;
  padding: 0px;
}
.servicesContent p {
  font-size: 13px;
  border-bottom: 1px dotted gray;
  padding-bottom: 5px;
  margin-top: 20px;
}
.service li a {
  font-size: 14px;
  color: black;
}
.service li img {
  padding: 4px;
}
#companyServices {
  background: #f3f3f3;
  margin-top: 100px;
}
</style>
