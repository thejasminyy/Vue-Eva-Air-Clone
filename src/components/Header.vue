<template>
  <div id="header">
    <div class="header">
      <div class="headerImg cursor">
        <!--logo點擊圖片扭-->
        <a href="https://www.evaair.com/zh-tw/index.html" traget="_blank">
          <img src="https://www.evaair.com/images/zhtw/new_eva_logo_tcm27-38760.png" alt="長榮航空標誌" />
        </a>
      </div>
      <!--填充物-->
      <div class="spacer"></div>
      <div class="headerRight">
        <div class="SignIn style colorSwitch cursor">
          <!--會員登入按鈕-->
          <p>
            <i class="fas fa-user"></i>會員登入
          </p>
        </div>
        <div class="language style colorSwitch">
          <!--繁體字-->
          <a href="#" class="cursor">
            <i class="fas fa-globe"></i>台灣(繁體中文)
            <i class="fas fa-sort-down"></i>
          </a>
        </div>
        <div class="search style">
          <!--搜尋框-->
          <label>
            <input type="text" id="search" placeholder="站內搜尋" v-bind:class="{active:isActive}" />
            <i class="fas fa-search cursor" @click="isActive=true"></i>
          </label>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
  data: function() {
    return {
      isActive: false
    };
  },
  methods: {
    onClickSearch() {}
  }
};
</script>

<style>
.header {
  display: flex;
  justify-content: right;
}
.headerImg img {
  margin: 10px;
}
.spacer {
  flex-grow: 1;
}
.headerRight {
  display: flex;
}
.SignIn:hover {
  background-color: #416e5e;
  color: #ffffff;
}
.SignIn > p {
  margin-top: 4px;
}
.SignIn > p > i {
  margin-right: 10px;
}
.language > a > i {
  margin-right: 10px;
}
.language {
  border-right: 1px solid #c4c4c4;
  border-left: 1px solid #c4c4c4;
}
.SignIn,
.language > a {
  color: #696969;
  font-size: 13px;
}
.style {
  padding: 20px 20px 0px 20px;
}
.colorSwitch:hover {
  background-color: #416e5e;
}
.colorSwitch:hover > a {
  color: #ffffff;
}
.search > label > i {
  margin-left: 10px;
}
.search > label > input {
  width: 0;
  padding: 0;
  border: 0;
  transition: width 2s;
}
.search > label > input.active {
  width: 150px;
}
#header {
  border-bottom: 1px solid #c4c4c4;
}
#search {
  padding: 5px;
}
</style>
