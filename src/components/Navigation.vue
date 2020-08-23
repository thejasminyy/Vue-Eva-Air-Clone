<template>
  <div id="navigation">
    <!--點擊後下拉 需要用bootstrap-->
    <nav>
      <div class="nav nav-tabs justify-content-center" id="nav-tab" role="tablist">
        <a
          class="nav-item nav-link active text-dark navStyle"
          id="nav-buytickets-tab"
          data-toggle="tab"
          href="#nav-buytickets"
          role="tab"
          aria-controls="nav-buytickets"
          aria-selected="true"
          @click="show = true"
        >購票及旅遊規劃</a>
        <a
          class="nav-item nav-link text-dark navStyle"
          id="nav-route-tab"
          data-toggle="tab"
          href="#nav-route"
          role="tab"
          aria-controls="nav-route"
          aria-selected="false"
        >行程管理</a>
        <a
          class="nav-item nav-link text-dark navStyle"
          id="nav-flight-tab"
          data-toggle="tab"
          href="#nav-flight"
          role="tab"
          aria-controls="nav-flight"
          aria-selected="false"
        >飛行體驗</a>
        <a
          class="nav-item nav-link text-dark navStyle"
          id="nav-mileage-tab"
          data-toggle="tab"
          href="#nav-mileage"
          role="tab"
          aria-controls="nav-mileage"
          aria-selected="false"
        >無限萬哩遊</a>
        <a
          class="nav-item nav-link text-dark navStyle"
          id="nav-explore-tab"
          data-toggle="tab"
          href="#nav-explore"
          role="tab"
          aria-controls="nav-explore"
          aria-selected="false"
        >探索長榮</a>
      </div>
    </nav>
    <div class="tab-content" id="nav-tabContent">
      <div
        class="tab-pane fade show active"
        id="nav-buytickets"
        role="tabpanel"
        aria-labelledby="nav-buytickets-tab"
        v-if="show"
      >
        <div class="content">
          <div class="container-left">
            <p>票價產品</p>
            <ul>
              <li>票價產品介紹</li>
              <li>票價產品優惠訊息</li>
              <li>票價產品常見問答</li>
              <li>會員酬賓新禮遇</li>
            </ul>
            <p>網路購票</p>
            <ul>
              <li>網路購票</li>
              <li>改票-更改日期/航班</li>
              <li>優惠碼購票</li>
              <li>學生票/打工度假票</li>
              <li>限時促銷 (Happy Hours)</li>
              <li>信用卡專區</li>
              <li>交易紀錄查詢</li>
              <li>退票申請/查詢</li>
              <li>購票證明單列印</li>
              <li>退票手續費/未登機費收據列印</li>
              <li>訂位須知與問答</li>
              <li>票務須知與問答</li>
              <li>會員酬賓機票與升等</li>
            </ul>
          </div>
          <div class="container-content">
            <p>超值優惠</p>
            <p>航班資訊</p>
            <ul>
              <li>班機表定時刻表查詢</li>
              <li>班機實際到離</li>
              <li>班機到離簡訊提醒</li>
              <li>航線圖與航線介紹</li>
              <li>星空聯盟網絡</li>
              <li>合作夥伴</li>
              <li>各地簽證資訊</li>
            </ul>
            <p>熱門航點</p>
            <ul>
              <li>所有航點</li>
              <li>到清邁</li>
              <li>到大阪</li>
              <li>到沖繩</li>
              <li>到溫哥華</li>
              <li>到首爾</li>
            </ul>
          </div>
          <div class="container-right">
            <p>Hello Kitty 彩繪機</p>
            <ul>
              <li>Hello Kitty 彩繪機家族介紹</li>
            </ul>
            <p>其他旅遊相關服務</p>
            <ul>
              <li>網路訂房</li>
              <li>網路租車、台灣桃園機場接送</li>
              <li>網路投保旅平險</li>
              <li>高鐵車票加購</li>
              <li>奧地利邦聯鐵路(ÖBB)延伸服務</li>
              <li>德國鐵路(DB)延伸服務</li>
              <li>比利時鐵路延伸服務</li>
            </ul>
          </div>
        </div>
      </div>
      <div class="tab-pane fade" id="nav-route" role="tabpanel" aria-labelledby="nav-route-tab">
        <div class="content">
          <div class="container-left">
            <p>管理您的行程</p>
            <ul>
              <li>預付超額行李</li>
              <li>未登機費收取</li>
              <li>取消全部行程</li>
              <li>預辦登機/報到/選位/選餐/行程特別協助</li>
              <li>確認付款</li>
              <li>預訂紐約/休士頓航線機場接駁巴士</li>
              <li>出入境北美通關資料(APIS)</li>
              <li>行程管理服務功能說明</li>
              <li>列印登機證/網路報到確認單</li>
              <li>旅遊叮嚀服務</li>
              <li>常見問答</li>
            </ul>
            <p>劃位報到</p>
            <ul>
              <li>手機報到</li>
              <li>網路報到</li>
              <li>自助報到機</li>
              <li>自助行李託運服務</li>
              <li>機場報到及劃位說明</li>
            </ul>
          </div>
          <div class="container-content">
            <p>您的行李</p>
            <ul>
              <li>行李基本須知</li>
              <li>聯航合作夥伴行李訊息</li>
              <li>託運行李</li>
              <li>隨身行李</li>
              <li>寵物運送</li>
            </ul>
            <p>行李注意事項</p>
            <ul>
              <li>超過限額行李規定及其他服務費用</li>
              <li>禁止攜帶物品</li>
              <li>各地機場之特殊規定</li>
              <li>行李延遲、遺失與損壞</li>
              <li>常見問答</li>
            </ul>
          </div>
          <div class="container-right">
            <p>機場和交通資訊</p>
            <ul>
              <li>貴賓室</li>
              <li>台灣地區機場介紹</li>
              <li>世界各地機場</li>
              <li>機場接駁巴士服務</li>
            </ul>
            <p>特別協助和查詢</p>
            <ul>
              <li>行程特別協助需求與身心障礙旅客搭機</li>
              <li>攜帶冷藏物品須知</li>
            </ul>
          </div>
        </div>
      </div>
      <div class="tab-pane fade" id="nav-flight" role="tabpanel" aria-labelledby="nav-flight-tab">
        <div class="content">
          <div class="container-left">
            <p>機隊</p>
            <ul>
              <li>客機</li>
              <li>貨機</li>
            </ul>
            <p>服務艙等</p>
            <ul>
              <li>皇璽桂冠艙</li>
              <li>桂冠艙</li>
              <li>商務艙</li>
              <li>豪華經濟艙</li>
              <li>經濟艙</li>
            </ul>
          </div>
          <div class="container-content">
            <p>客艙娛樂與服務</p>
            <ul>
              <li>機上通訊與行動服務</li>
              <li>電影</li>
              <li>電視節目</li>
              <li>遊戲</li>
              <li>機上雜誌</li>
              <li>免稅品預購</li>
            </ul>
            <p>機上餐飲</p>
            <ul>
              <li>特別餐</li>
            </ul>
          </div>
          <div class="container-right">
            <p>安全與健康</p>
            <ul>
              <li>客艙與搭機安全</li>
              <li>搭機健康須知</li>
            </ul>
          </div>
        </div>
      </div>
      <div class="tab-pane fade" id="nav-mileage" role="tabpanel" aria-labelledby="nav-mileage-tab">
        <div class="content">
          <div class="container-left">
            <p>會員酬賓新禮遇</p>
            <ul>
              <li>哩程獎勵</li>
              <li>問答集</li>
            </ul>
            <p>會員優惠待遇</p>
            <ul>
              <li>無限萬哩遊/星空聯盟</li>
              <li>各卡籍優惠待遇</li>
              <li>合作夥伴優惠專案</li>
            </ul>
            <p>加入會員</p>
            <ul>
              <li>線上申請</li>
              <li>郵寄申請</li>
              <li>入會規則與條款</li>
            </ul>
            <p>我的帳戶</p>
            <ul>
              <li>我的哩程資料</li>
              <li>我的個人資料</li>
              <li>會員卡補發</li>
              <li>網路服務授權</li>
              <li>查詢哩程核對表</li>
            </ul>
          </div>
          <div class="container-content">
            <p>賺取哩程</p>
            <ul>
              <li>搭乘長榮與立榮航空</li>
              <li>搭乘星空聯盟航班</li>
              <li>其他合作夥伴獎勵哩程</li>
            </ul>
            <p>購買哩程</p>
            <ul>
              <li>辦理購買哩程</li>
              <li>列印購買哩程證明單</li>
            </ul>
            <p>會員獨享哩程優惠</p>
            <ul>
              <li>哩程累計優惠活動</li>
              <li>哩程累計優惠活動註冊</li>
              <li>艙位升等優惠活動</li>
              <li>艙位升等優惠活動註冊</li>
              <li>酬賓機票優惠活動</li>
              <li>查詢已註冊優惠活動</li>
            </ul>
          </div>
          <div class="container-right">
            <p>使用哩程</p>
            <ul>
              <li>兌換長榮/立榮酬賓機票</li>
              <li>兌換星空聯盟酬賓機票</li>
              <li>兌換長榮/立榮國際線艙位升等</li>
              <li>兌換星空聯盟航空艙位升等</li>
              <li>Miles & Cash</li>
              <li>兌換旅遊抵用券</li>
              <li>兌換住宿券</li>
              <li>兌換刊物/商品</li>
              <li>兌換模擬機駕駛課程</li>
              <li>辦理哩程轉讓/轉回</li>
              <li>辦理電子升等憑證轉讓/轉回</li>
            </ul>
            <p>會員資訊與服務</p>
            <ul>
              <li>會員電子專刊</li>
              <li>常見問答</li>
              <li>各地會員服務中心</li>
              <li>下載中心</li>
              <li>空中仁醫申請</li>
            </ul>
          </div>
        </div>
      </div>
      <div class="tab-pane fade" id="nav-explore" role="tabpanel" aria-labelledby="nav-explore-tab">
        <div class="content">
          <div class="content-left">
            <p>最新消息</p>
            <ul>
              <li>公司消息</li>
              <li>旅遊與航班訊息</li>
            </ul>
            <p>人才招募</p>
            <ul>
              <li>公司福利</li>
              <li>公司職缺</li>
              <li>履歷登錄</li>
              <li>招募結果查詢</li>
            </ul>
            <p>「綠 旅行」- 長榮航空碳抵銷計劃</p>
          </div>
          <div id="container-content">
            <p>其他</p>
            <ul>
              <li>媒體/表單下載</li>
              <li>電子發票</li>
              <li>電子採購公告</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navigation",
  data: function() {
    return {
      show: false
    };
  }
};
</script>
<style>
.navStyle {
  padding: 15px 30px;
}
.content {
  display: flex;
  justify-content: center;
  margin: 30px 0px 10px 160px;
}
.content ul {
  list-style-type: none;
  padding: 0px 0px 0px 10px;
  width: 18.76em;
}
.content ul li {
  color: gray;
  font-size: 15px;
}
.content p {
  margin: 0;
  font-weight: bold;
}
.content p,
.content li {
  cursor: pointer;
}
.content p:hover,
.content li:hover {
  color: #4c806e;
}
.container-content {
  border-left: 1px dotted gray;
  border-right: 1px dotted gray;
  padding-left: 10px;
  margin-right: 10px;
}
#navigation .nav-tabs .nav-link.active {
  border-top: none;
  border-right: none;
  border-left: none;
}
#navigation a:hover {
  background: #4c806e;
}
#container-content {
  border-left: 1px dotted gray;
  padding-left: 10px;
}
</style>