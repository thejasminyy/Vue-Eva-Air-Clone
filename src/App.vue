<template>
  <div id="app">
    <Header />
    <Navigation />
    <headerImg />
    <Navform />
    <Discount />
    <Featuredoffers />
    <Announcement />
    <Companyservices />
    <Foot />
  </div>
</template>

<script>
import Header from "./components/Header";
import Navigation from "./components/Navigation";
import HeaderImg from "./components/HeaderImg";
import Navform from "./components/Navform";
import Discount from "./components/Discount";
import Featuredoffers from "./components/Featuredoffers";
import Announcement from "./components/Announcement";
import Companyservices from "./components/Companyservices";
import Foot from "./components/Foot";

export default {
  name: "App",
  components: {
    Header,
    Navigation,
    HeaderImg,
    Navform,
    Discount,
    Featuredoffers,
    Announcement,
    Companyservices,
    Foot
  }
};
</script>

<style>
* {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
  font-family: Microsoft JhengHei;
}
.cursor {
  cursor: pointer;
}
</style>
