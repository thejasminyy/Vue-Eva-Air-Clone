<template>
  <div id="announcement">
    <div class="container">
      <div class="announcement">
        <h5 class="titleStyle">旅遊公告與航班訊息</h5>
        <!--左邊的航班訊息-->
        <div class="announcementLeft">
          <ul id="announcementContent">
            <li v-for="(item,k) in items" :key="k" class="cursor">‧ {{item.content}}</li>
          </ul>
          <p class="moreInfo cursor">
            <i class="fas fa-fan" style="color: #ff922b;"></i>更多訊息
          </p>
        </div>
      </div>
      <!--右邊的長榮景觀窗圖片-->
      <div class="announcementRight">
        <div id="announcementRight">
          <h5 class="titleStyle">長榮景觀窗</h5>
          <img src="https://source.unsplash.com/user/erondu/460x305" alt />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Announcement",
  data: function() {
    return {
      items: [
        {
          content: "請查詢最新旅遊限制相關規定"
        },
        {
          content: "自2020年6月1日起，長榮航空/立榮航空調整行李費率"
        },
        {
          content: "長榮航空台灣地區收取客運燃油附加費說明 -5月11日更新"
        },
        {
          content:
            "長榮/立榮航空因應新冠病毒疫情影響之國際、兩岸及港澳航線改、退票作業辦法(5月07日 更新)"
        },
        {
          content: "長榮航空防疫說明(4/21更新)"
        }
      ]
    };
  }
};
</script>

<style>
.container {
  display: flex;
  border-top: 1px dotted gray;
  margin-top: 50px;
}
.titleStyle {
  text-align: center;
  font-weight: bold;
  margin: 18px 0px;
}
.announcementLeft {
  border: 1px dotted gray;
  padding: 20px;
  margin-right: 15px;
}
.moreInfo {
  text-align: end;
  font-size: 14px;
  margin: 0px;
}
#announcement {
  width: 900px;
  margin: 0px auto;
}
#announcementContent {
  list-style-type: none;
  padding: 0px;
  margin-bottom: 40px;
}
#announcementContent li {
  font-size: 14px;
  margin-bottom: 15px;
  text-decoration: underline;
}
#announcementContent li:hover {
  text-decoration: none;
}
</style>
