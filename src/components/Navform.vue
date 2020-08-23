<template>
  <div id="navform">
    <!--點擊後下拉 使用bootstrap-->
    <nav>
      <div class="nav nav-tabs justify-content-center" id="nav-tab" role="tablist">
        <a
          class="nav-item nav-link active formStyle"
          id="nav-bookATrip-tab"
          data-toggle="tab"
          href="#nav-bookATrip"
          role="tab"
          aria-controls="nav-bookATrip"
          aria-selected="true"
        >預訂行程</a>
        <a
          class="nav-item nav-link formStyle"
          id="nav-manageItinerary-tab"
          data-toggle="tab"
          href="#nav-manageItinerary"
          role="tab"
          aria-controls="nav-manageItinerary"
          aria-selected="false"
        >
          行程管理
          <br />網路報到
        </a>
        <a
          class="nav-item nav-link formStyle"
          id="nav-timetable-tab"
          data-toggle="tab"
          href="#nav-timetable"
          role="tab"
          aria-controls="nav-timetable"
          aria-selected="false"
        >班機表定時刻表</a>
        <a
          class="nav-item nav-link formStyle"
          id="nav-flightTime-tab"
          data-toggle="tab"
          href="#nav-flightTime"
          role="tab"
          aria-controls="nav-flightTime"
          aria-selected="false"
        >班機實際到離</a>
      </div>
    </nav>
    <!--預訂行程內容-->
    <div class="tab-content navForm" id="nav-tabContent">
      <div
        class="tab-pane fade show active"
        id="nav-bookATrip"
        role="tabpanel"
        aria-labelledby="nav-bookATrip-tab"
      >
        <ul class="nav nav-pills mb-3" id="pills-tab" role="tablist">
          <li class="nav-item">
            <a
              class="nav-link active"
              id="pills-home-tab"
              data-toggle="pill"
              href="#pills-home"
              role="tab"
              aria-controls="pills-home"
              aria-selected="true"
            >網路購票</a>
          </li>
          <li class="nav-item">
            <a
              class="nav-link"
              id="pills-profile-tab"
              data-toggle="pill"
              href="#pills-profile"
              role="tab"
              aria-controls="pills-profile"
              aria-selected="false"
            >飯店</a>
          </li>
        </ul>
        <div class="tab-content" id="pills-tabContent">
          <!--按鈕:網路購票內容-->
          <div
            class="tab-pane fade show active"
            id="pills-home"
            role="tabpanel"
            aria-labelledby="pills-home-tab"
          >
            <div class="navFormCentent">
              <div class="stroke">
                <p class="fontStyle">單程或來回</p>
                <form style="display:initial">
                  <input type="radio" name="oneWay" />
                  <label for="oneWay" style="margin: 0px 25px 0px 10px; font-size: 14px;">單程</label>
                  <input type="radio" name="roundTrip" />
                  <label for="roundTrip" style="margin: 0px 25px 0px 10px; font-size: 14px;">來回</label>
                </form>
                <a href="#" class="stayCity">不同進出點/中途停留/多個城市</a>
              </div>
              <div class="destineLocation">
                <div class="destineLocationFirst">
                  <div class="location">
                    <span>
                      <label for="setOff" class="fontStyle">出發地</label>
                    </span>
                    <form>
                      <input type="text" name="setOff" value="台北 (桃園機場) - TPE" />
                    </form>
                  </div>
                  <div class="location">
                    <span>
                      <label for="destination" class="fontStyle">目的地</label>
                    </span>
                    <form>
                      <input type="text" name="destination" />
                    </form>
                  </div>
                </div>
                <div class="destineLocationFirst">
                  <div class="location">
                    <span>
                      <label for="from" class="fontStyle">行程日期</label>
                    </span>
                    <form>
                      <input type="text" name="from" value="2020年7月30日" />
                    </form>
                  </div>
                  <div class="location">
                    <span>
                      <label for="grade" class="fontStyle">艙等</label>
                    </span>
                    <select class="selectStyle" style="margin:0px;">
                      <option value="1">經濟艙</option>
                      <option value="2">頭等艙</option>
                      <option value="3">商務艙/皇璽桂冠艙/桂冠艙</option>
                      <option value="4">豪華經濟艙</option>
                    </select>
                  </div>
                </div>
              </div>
              <div class="date">
                <input type="checkbox" name="flexible" />
                <label for="flexible">彈性旅遊日期</label>
              </div>
              <div class="selectorNumber">
                <div class="people">
                  <p class="fontStyle">大人</p>
                  <select>
                    <option value="1">1</option>
                    <option value="2">2</option>
                    <option value="3">3</option>
                    <option value="4">4</option>
                    <option value="5">5</option>
                    <option value="6">6</option>
                    <option value="7">7</option>
                    <option value="8">8</option>
                    <option value="9">9</option>
                    <option value="10">10</option>
                  </select>
                  <span class="ageStyle">(12歲以上)</span>
                </div>
                <div class="people">
                  <p class="fontStyle">小孩</p>
                  <select>
                    <option value="0">0</option>
                    <option value="1">1</option>
                    <option value="2">2</option>
                    <option value="3">3</option>
                  </select>
                  <span class="ageStyle">(2-11)</span>
                </div>
                <div class="people">
                  <p class="fontStyle">嬰兒</p>
                  <select>
                    <option value="0">0</option>
                    <option value="1">1</option>
                  </select>
                  <span class="ageStyle">(2歲以下)</span>
                </div>
              </div>
              <div class="priceContent">
                <div class="searchPriceButton">
                  <button type="button cursor" class="btn">查詢票價及訂票</button>
                </div>
                <ul class="payment">
                  <li v-for="(item,payment) in items" :key="payment" class="cursor">
                    <i class="fas fa-angle-double-right" style="color: #4c806e; margin-right: 5px;"></i>
                    {{ item.payment}}
                  </li>
                </ul>
              </div>
            </div>
          </div>
          <!--按鈕:飯店內容-->
          <div
            class="tab-pane fade"
            id="pills-profile"
            role="tabpanel"
            aria-labelledby="pills-profile-tab"
          >
            <div class="bookAHotel">
              <div class="hoteltitle">
                <div id="hoteltitle">
                  <i class="fas fa-search"></i>
                  <h4>預訂飯店，賺取無限萬哩遊哩程！</h4>
                  <div class="filling"></div>
                  <img
                    src="https://r-cf.bstatic.com/static/img/affiliate_base/flexi/booking_logo_blue/ebc3273565b5e682ccaf01872d2e046749306442.png"
                  />
                </div>
                <div class="location">
                  <span>
                    <label for="hotelName" class="fontStyle">目的地/住宿名稱:</label>
                  </span>
                </div>
                <form>
                  <input
                    class="hotelName"
                    type="text"
                    name="hotelName"
                    placeholder="例如:城市、地區、區或特定飯店、民宿、公寓名稱"
                  />
                </form>
              </div>
              <div class="hoteldate">
                <div class="location">
                  <span>
                    <p class="fontStyle" style="margin-top: 5px;">入住日期</p>
                  </span>
                </div>
                <i class="far fa-calendar-alt"></i>
                <select style="margin: 0px 5px;">
                  <option value="1">1</option>
                  <option value="2">2</option>
                  <option value="3">3</option>
                  <option value="4">4</option>
                  <option value="5">5</option>
                  <option value="6">6</option>
                  <option value="7">7</option>
                  <option value="8">8</option>
                  <option value="9">9</option>
                  <option value="10">10</option>
                  <option value="11">11</option>
                  <option value="12">12</option>
                  <option value="13">13</option>
                  <option value="14">14</option>
                  <option value="15">15</option>
                  <option value="16">16</option>
                  <option value="17">17</option>
                  <option value="18">18</option>
                  <option value="19">19</option>
                  <option value="20">20</option>
                  <option value="21">21</option>
                  <option value="22">22</option>
                  <option value="23">23</option>
                  <option value="24">24</option>
                  <option value="25">25</option>
                  <option value="26">26</option>
                  <option value="27">27</option>
                  <option value="28">28</option>
                  <option value="29">29</option>
                  <option value="30">30</option>
                  <option value="31">31</option>
                </select>
                <select>
                  <option value="7月'20'">7月'20'</option>
                  <option value="8月'20'">8月'20'</option>
                  <option value="9月'20'">9月'20'</option>
                  <option value="10月'20'">10月'20'</option>
                  <option value="11月'20'">11月'20'</option>
                  <option value="12月'20'">12月'20'</option>
                  <option value="1月'21'">1月'21'</option>
                </select>
                <div class="location">
                  <span>
                    <p class="fontStyle">退房日期</p>
                  </span>
                  <i class="far fa-calendar-alt"></i>
                  <select style="margin: 0px 5px;">
                    <option value="1">1</option>
                    <option value="2">2</option>
                    <option value="3">3</option>
                    <option value="4">4</option>
                    <option value="5">5</option>
                    <option value="6">6</option>
                    <option value="7">7</option>
                    <option value="8">8</option>
                    <option value="9">9</option>
                    <option value="10">10</option>
                    <option value="11">11</option>
                    <option value="12">12</option>
                    <option value="13">13</option>
                    <option value="14">14</option>
                    <option value="15">15</option>
                    <option value="16">16</option>
                    <option value="17">17</option>
                    <option value="18">18</option>
                    <option value="19">19</option>
                    <option value="20">20</option>
                    <option value="21">21</option>
                    <option value="22">22</option>
                    <option value="23">23</option>
                    <option value="24">24</option>
                    <option value="25">25</option>
                    <option value="26">26</option>
                    <option value="27">27</option>
                    <option value="28">28</option>
                    <option value="29">29</option>
                    <option value="30">30</option>
                    <option value="31">31</option>
                  </select>
                  <select>
                    <option value="7月'20'">7月'20'</option>
                    <option value="8月'20'">8月'20'</option>
                    <option value="9月'20'">9月'20'</option>
                    <option value="10月'20'">10月'20'</option>
                    <option value="11月'20'">11月'20'</option>
                    <option value="12月'20'">12月'20'</option>
                    <option value="1月'21'">1月'21'</option>
                  </select>
                </div>
                <div class="date" style="margin-top: 5px;">
                  <input type="checkbox" name="flexible" />
                  <label for="flexible">我還沒有確定具體日期</label>
                </div>
                <div id="priceContent">
                  <div id="searchPriceButton">
                    <button type="button cursor" class="btn">搜尋</button>
                  </div>
                  <ul class="payment">
                    <li v-for="(item,payment) in items" :key="payment">
                      <i
                        class="fas fa-angle-double-right"
                        style="color: #4c806e; margin-right: 5px;"
                      ></i>
                      {{ item.payment}}
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div
        class="tab-pane fade"
        id="nav-manageItinerary"
        role="tabpanel"
        aria-labelledby="nav-manageItinerary-tab"
      >
        <!--行程管理 網路報到 內容-->
        <ul class="nav nav-pills mb-3" id="pills-tab" role="tablist">
          <li class="nav-item">
            <!--無限萬哩遊會員 按鈕-->
            <a
              class="nav-link active"
              id="pills-member-tab"
              data-toggle="pill"
              href="#pills-member"
              role="tab"
              aria-controls="pills-member"
              aria-selected="true"
            >無限萬哩遊會員</a>
          </li>
          <li class="nav-item">
            <!--使用訂位代號或機票號碼查詢 按鈕-->
            <a
              class="nav-link"
              id="pills-searchItinerary-tab"
              data-toggle="pill"
              href="#pills-searchItinerary"
              role="tab"
              aria-controls="pills-searchItinerary"
              aria-selected="false"
            >使用訂位代號或機票號碼查詢</a>
          </li>
        </ul>
        <!--無限萬哩遊會員 內容-->
        <div class="tab-content" id="pills-tabContent">
          <div
            class="tab-pane fade show active"
            id="pills-member"
            role="tabpanel"
            aria-labelledby="pills-member-tab"
          >
            <div class="signIn">
              <div class="location">
                <span>
                  <label for="accountNumber" class="fontStyle">無限萬哩遊會員卡號/E-Mail帳號/會員代號</label>
                </span>
                <form>
                  <input type="text" name="accountNumber" style="width: 100%;" />
                </form>
              </div>
              <p id="signIn" class="cursor">卡號查詢</p>
              <div class="location">
                <span>
                  <label for="password" class="fontStyle">密碼</label>
                </span>
                <form>
                  <input type="password" name="password" style="width: 100%;" />
                </form>
                <p id="signIn" class="cursor">密碼查詢</p>
              </div>
              <div class="rememberCode">
                <input type="checkbox" name="flexible" />
                <label for="flexible">記住我的會員卡號/E-Mail帳號或會員代號</label>
              </div>
              <div class="comment">
                <p>您可以在班機起飛前1.5-48小時進行網路報到。</p>
                <p>
                  還不是會員嗎? 立刻
                  <span class="joinMember cursor">加入會員!</span>
                </p>
              </div>
            </div>
            <div id="memberButton">
              <button type="button cursor" class="btn" style="margin-bottom: 10px;">登入</button>
            </div>
          </div>
          <!--使用訂位代號或機票號碼查詢 內容-->
          <div
            class="tab-pane fade"
            id="pills-searchItinerary"
            role="tabpanel"
            aria-labelledby="pills-searchItinerary-tab"
          >
            <div class="searchItinerary">
              <div class="location">
                <span>
                  <label for="searchcode" class="fontStyle">訂位代號/機票號碼</label>
                </span>
                <form>
                  <input type="text" name="searchcode" style="width: 100%; margin-bottom: 10px;" />
                </form>
              </div>
              <div class="location">
                <span>
                  <label for="searchItineraryFamilyName" class="fontStyle">姓 (例如:陳禹暘，[姓]填入CHEN)</label>
                </span>
                <form>
                  <input
                    type="text"
                    name="searchItineraryFamilyName"
                    style="width: 100%; margin-bottom:10px;"
                  />
                </form>
              </div>
              <div class="location">
                <span>
                  <label for="searchItineraryGivenName" class="fontStyle">名 (例如:陳禹暘，[名]填入YUYANG)</label>
                </span>
                <form>
                  <input
                    type="text"
                    name="searchItineraryGivenName"
                    style="width: 100%; margin-bottom: 10px;"
                  />
                </form>
              </div>
              <div class="searchItineraryFoot">
                <p>您可以在班機起飛前1.5-48小時進行網路報到。</p>
                <div id="memberButton">
                  <button type="button" class="btn cursor" style="margin-bottom: 10px;">登入</button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <!--班機表定時刻表-->
      <div
        class="tab-pane fade"
        id="nav-timetable"
        role="tabpanel"
        aria-labelledby="nav-timetable-tab"
      >
        <div class="navForm">
          <div class="stroke">
            <p class="fontStyle">行程類型</p>
            <form style="display:initial">
              <input type="radio" name="oneWay" />
              <label for="oneWay" style="margin:0px 25px 0px 10px; font-size:14px;">單程</label>
              <input type="radio" name="roundTrip" />
              <label for="roundTrip" style="margin:0px 25px 0px 10px; font-size:14px;">來回</label>
            </form>
          </div>
          <div class="flightSchedule">
            <div class="location">
              <span>
                <label for="locationSetOff" class="fontStyle">出發地</label>
              </span>
              <form>
                <input type="text" name="locationSetOff" value="台北 (桃園機場) - TPE" />
              </form>
            </div>
            <div class="location">
              <span>
                <label for="locationDestination" class="fontStyle">目的地</label>
              </span>
              <form>
                <input type="text" name="locationDestination" />
              </form>
            </div>
          </div>
          <div class="strokeDate">
            <div class="location">
              <span>
                <label for="TravelDate" class="fontStyle">行程日期</label>
              </span>
              <form>
                <input type="text" name="TravelDate" value="2020年7月30日" style="width: 100%;" />
              </form>
            </div>
          </div>
          <div class="searchPriceButton">
            <button type="button cursor" class="btn" style="margin: 10px 0px;">搜尋</button>
          </div>
        </div>
      </div>
      <div
        class="tab-pane fade"
        id="nav-flightTime"
        role="tabpanel"
        aria-labelledby="nav-flightTime-tab"
      >
        <!--班機實際到離-->
        <ul class="nav nav-pills mb-3" id="pills-tab" role="tablist">
          <li class="nav-item">
            <a
              class="nav-link active"
              id="pills-flightTimeDeparture-tab"
              data-toggle="pill"
              href="#pills-flightTimeDeparture"
              role="tab"
              aria-controls="pills-flightTimeDeparture"
              aria-selected="true"
            >出發地與目的地</a>
          </li>
          <li class="nav-item">
            <a
              class="nav-link"
              id="pills-flightTimeFlightNumber-tab"
              data-toggle="pill"
              href="#pills-flightTimeFlightNumber"
              role="tab"
              aria-controls="pills-flightTimeFlightNumber"
              aria-selected="false"
            >班機編號</a>
          </li>
          <li class="nav-item">
            <a
              class="nav-link"
              id="pills-flightTimeCityName-tab"
              data-toggle="pill"
              href="#pills-flightTimeCityName"
              role="tab"
              aria-controls="pills-flightTimeCityName"
              aria-selected="false"
            >指定城市名稱</a>
          </li>
          <li class="nav-item">
            <a
              class="nav-link"
              id="pills-flightTimeFlightStatus-tab"
              data-toggle="pill"
              href="#pills-flightTimeFlightStatus"
              role="tab"
              aria-controls="pills-flightTimeFlightStatus"
              aria-selected="false"
            >航班離/到場證明</a>
          </li>
        </ul>
        <div class="tab-content" id="pills-tabContent">
          <div
            class="tab-pane fade show active"
            id="pills-flightTimeDeparture"
            role="tabpanel"
            aria-labelledby="pills-flightTimeDeparture-tab"
          >
            <!--出發地與目的地內容-->
            <div class="searchFligh">
              <div class="searchFlighTitle">
                <div class="searchFlighTitleContent" style="width:73.12em;">
                  <p class="fontStyle">查詢選擇</p>
                  <form style="display:initial">
                    <input type="radio" name="flightDeparture" />
                    <label
                      for="flightDeparture"
                      style="margin:0px 25px 0px 10px; font-size:14px;"
                    >航班出發</label>
                    <input type="radio" name="arrivalDate" />
                    <label for="arrivalDate" style="margin: 0px 25px 0px 10px; font-size:14px;">抵達日期</label>
                  </form>
                </div>
                <div>
                  <div class="location">
                    <span>
                      <label for="searchDate" class="fontStyle">日期</label>
                    </span>
                    <form>
                      <input type="text" name="searchDate" value="2020年7月30日" style="margin:0px" />
                    </form>
                  </div>
                </div>
              </div>
              <div class="formInput" style="margin-top:15px;">
                <div class="location">
                  <span>
                    <label for="formDeparture" class="fontStyle">出發地</label>
                  </span>
                  <form>
                    <input type="text" name="formDeparture" value="台北 (桃園機場) - TPE" />
                  </form>
                </div>
                <div class="location">
                  <span>
                    <label for="formDestination" class="fontStyle">目的地</label>
                  </span>
                  <form>
                    <input type="text" name="formDestination" />
                  </form>
                </div>
              </div>
              <div class="searchPriceButton">
                <button type="button cursor" class="btn" style="margin:10px 0px;">搜尋</button>
              </div>
            </div>
          </div>
          <div
            class="tab-pane fade"
            id="pills-flightTimeFlightNumber"
            role="tabpanel"
            aria-labelledby="pills-flightTimeFlightNumber-tab"
          >
            <!--班機編號內容-->
            <div class="searchFligh">
              <div class="searchFlighTitle">
                <div class="searchFlighTitleContent" style="width:73.12em;">
                  <p class="fontStyle">查詢選擇</p>
                  <form style="display:initial">
                    <input type="radio" name="flightDeparture" />
                    <label
                      for="flightDeparture"
                      style="margin:0px 25px 0px 10px; font-size:14px;"
                    >航班出發</label>
                    <input type="radio" name="arrivalDate" />
                    <label for="arrivalDate" style="margin: 0px 25px 0px 10px; font-size:14px;">抵達日期</label>
                  </form>
                </div>
                <div>
                  <div class="location">
                    <span>
                      <label for="searchDate" class="fontStyle">日期</label>
                    </span>
                    <form>
                      <input type="text" name="searchDate" value="2020年7月30日" style="margin:0px" />
                    </form>
                  </div>
                </div>
              </div>
              <div class="flightNumberStyle" style="margin-top:15px;">
                <div class="flightNumber">
                  <p class="fontStyle">班機編號：</p>
                  <form style="display:initial">
                    <input type="radio" name="flightNumberBR" />
                    <label for="flightNumberBR" style="margin:0px 25px 0px 10px; font-size:14px;">BR</label>
                    <input type="radio" name="flightNumberB7" />
                    <label for="flightNumberB7" style="margin:0px 25px 0px 10px; font-size:14px;">B7</label>
                  </form>
                </div>
                <div class="flightNumberinput">
                  <form>
                    <input type="text" name="formDeparture" />
                  </form>
                </div>
              </div>
              <div class="searchPriceButton">
                <button type="button cursor" class="btn" style="margin:10px 0px;">搜尋</button>
              </div>
            </div>
          </div>
          <div
            class="tab-pane fade"
            id="pills-flightTimeCityName"
            role="tabpanel"
            aria-labelledby="pills-flightTimeCityName-tab"
          >
            <!--指定城市名稱內容-->
            <div id="searchCityName">
              <div class="searchCityName">
                <div class="searchCityNameContent" style="width:73.12em;">
                  <p class="fontStyle">查詢選擇</p>
                  <form style="display:initial">
                    <input type="radio" name="flightDeparture" />
                    <label
                      for="flightDeparture"
                      style="margin:0px 25px 0px 10px; font-size:14px;"
                    >航班出發</label>
                    <input type="radio" name="arrivalDate" />
                    <label for="arrivalDate" style="margin: 0px 25px 0px 10px; font-size:14px;">抵達日期</label>
                  </form>
                </div>
                <div>
                  <div class="location">
                    <span>
                      <label for="searchDate" class="fontStyle">日期</label>
                    </span>
                    <form>
                      <input type="text" name="searchDate" value="2020年7月30日" style="margin:0px" />
                    </form>
                  </div>
                </div>
              </div>
              <div class="searchCityName" style="margin-top:15px;">
                <div class="location">
                  <span>
                    <label for="formDeparture" class="fontStyle">選擇出發/抵達機場 :</label>
                  </span>
                  <form>
                    <input type="text" name="formDeparture" value="台北 (桃園機場) - TPE" />
                  </form>
                </div>
                <div class="location">
                  <span>
                    <label for="formDepartureTime" class="fontStyle">選擇出發/抵達時間 :</label>
                  </span>
                  <select class="searchTimeStyle">
                    <option value="00:00 ~ 05:59">00:00 ~ 05:59</option>
                    <option value="06:00 ~ 11:59">06:00 ~ 11:59</option>
                    <option value="12:00 ~ 17:59">12:00 ~ 17:59</option>
                    <option value="18:00 ~ 23:59">18:00 ~ 23:59</option>
                  </select>
                </div>
              </div>
              <div class="searchPriceButton">
                <button type="button cursor" class="btn" style="margin:10px 0px;">搜尋</button>
              </div>
            </div>
          </div>
          <div
            class="tab-pane fade"
            id="pills-flightTimeFlightStatus"
            role="tabpanel"
            aria-labelledby="pills-flightTimeFlightStatus-tab"
          >
            <!--航班離/到場證明內容-->
            <div class="searchFligh">
              <div class="searchFlighTitle">
                <div class="searchFlighTitleContent" style="width:73.12em;">
                  <p class="fontStyle">查詢選擇</p>
                  <form style="display:initial">
                    <input type="radio" name="flightDeparture" />
                    <label
                      for="flightDeparture"
                      style="margin:0px 25px 0px 10px; font-size:14px;"
                    >航班出發</label>
                    <input type="radio" name="arrivalDate" />
                    <label for="arrivalDate" style="margin: 0px 25px 0px 10px; font-size:14px;">抵達日期</label>
                  </form>
                </div>
                <div>
                  <div class="location">
                    <span>
                      <label for="searchDate" class="fontStyle">日期</label>
                    </span>
                    <form>
                      <input type="text" name="searchDate" value="2020年7月30日" style="margin:0px" />
                    </form>
                  </div>
                </div>
              </div>
              <div class="flightNumberStyle" style="margin-top:15px;">
                <div class="flightNumber">
                  <p class="fontStyle">班機編號：</p>
                  <form style="display:initial">
                    <input type="radio" name="flightNumberBR" />
                    <label for="flightNumberBR" style="margin:0px 25px 0px 10px; font-size:14px;">BR</label>
                    <input type="radio" name="flightNumberB7" />
                    <label for="flightNumberB7" style="margin:0px 25px 0px 10px; font-size:14px;">B7</label>
                  </form>
                </div>
                <div class="flightNumberinput">
                  <form>
                    <input type="text" name="formDeparture" />
                  </form>
                </div>
              </div>
              <div class="searchPriceButton">
                <button type="button cursor" class="btn cursor" style="margin:10px 0px;">搜尋</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navform",
  data: function() {
    return {
      items: [
        {
          payment: "信用卡專區"
        },
        {
          payment: "確認付款"
        },
        {
          payment: "優惠碼購票"
        }
      ]
    };
  }
};
</script>



<style>
.formStyle {
  background: #4c806e;
  color: white;
  padding: 10px 50px;
  margin-right: 2px;
}
.formStyle:hover {
  background: white;
  color: #4c806e;
}
.navFormCentent {
  width: 100%;
}
.fontStyle {
  font-size: 14px;
  font-weight: bold;
  margin-bottom: 2px;
}
.navForm {
  width: 800px;
  margin: 0px auto;
  margin-top: 20px;
}
.destineLocationFirst,
.searchFlighTitle,
.formInput,
.searchCityName,
.flightNumberStyle,
#hoteltitle {
  display: flex;
}
.stayCity {
  color: gray;
  text-decoration: underline;
  font-size: 14px;
  margin-left: 15px;
}
.stayCity:hover {
  text-decoration: none;
  color: gray;
}

.location input {
  font-size: 14px;
  width: 385px;
  padding: 7px;
  margin-right: 30px;
  box-shadow: inset 0 1px 3px #ddd;
  border: 1px solid #cccccc;
}
.selectStyle {
  display: block;
  font-size: 14px;
  width: 385px;
  padding: 7px;
  box-shadow: inset 0 1px 3px #ddd;
  border: 1px solid #cccccc;
}
.searchTimeStyle {
  display: block;
  font-size: 14px;
  padding: 7px;
  box-shadow: inset 0 1px 3px #ddd;
  border: 1px solid #cccccc;
}
.date label {
  margin-left: 10px;
}
.selectorNumber {
  display: flex;
  margin: 15px 0px;
}
.people select {
  width: 170px;
  padding: 6px;
  box-shadow: inset 0 1px 3px #ddd;
  border: 1px solid #cccccc;
}
.ageStyle {
  font-size: 15px;
  margin: 0px 30px 0px 5px;
  font-style: italic;
}
.nav-pills .nav-link.active {
  background: #4c806e;
  color: white;
}
.nav-item a {
  color: #4c806e;
  border: 1px solid #4c806e;
  margin-left: 10px;
}
.nav-item a:hover {
  background: #4c806e;
  color: white;
}
.nav-tabs .nav-link.active {
  color: #4c806e;
}
.searchPriceButton,
#memberButton {
  display: flex;
  justify-content: flex-end;
}
.searchPriceButton button,
#memberButton button {
  color: white;
  background: #4c806e;
  font-size: 1.692em;
  padding: 10px 30px;
}
.searchPriceButton button:hover,
#memberButton button:hover {
  color: #4c806e;
  background: white;
  border-color: #4c806e;
}
.payment {
  padding: 0px;
  list-style-type: none;
  display: flex;
}
.payment li {
  font-size: 14px;
  color: gray;
  margin-right: 30px;
}
.payment li:hover {
  color: #4c806e;
}
.hoteltitle h4 {
  margin-left: 5px;
}
.hoteltitle img {
  width: 90px;
  height: 15px;
}
.filling {
  flex-grow: 1;
}
.hotelName {
  width: 100%;
  padding: 5px;
  border: 1px solid #cccccc;
  box-shadow: inset 0 1px 3px #ddd;
}
.rememberCode label {
  font-size: 15px;
  font-weight: 700;
  margin-left: 10px;
}
.comment {
  font-size: 14px;
  margin-top: 5px;
}
.joinMember {
  text-decoration: underline;
}
.joinMember:hover,
#signIn:hover {
  text-decoration: none;
}
.searchItineraryFoot p {
  font-size: 14px;
  font-weight: 700;
}
.flightSchedule {
  display: flex;
  margin: 10px 0px;
}
.flightNumberinput input {
  font-size: 14px;
  padding: 7px;
  margin-top: 13px;
  box-shadow: inset 0 1px 3px #ddd;
  border: 1px solid #cccccc;
}
#searchPriceButton {
  display: flex;
  justify-content: flex-end;
}
#searchPriceButton button {
  color: white;
  background: #4c806e;
}
#searchPriceButton button:hover {
  color: #4c806e;
  background: white;
  border-color: #4c806e;
}
#signIn {
  font-size: 13px;
  color: gray;
  text-decoration: underline;
  margin-top: 10px;
}
</style>
