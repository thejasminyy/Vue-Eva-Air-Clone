<template>
  <!--底-->
  <div id="foot">
    <div class="copyright">
      <div class="left">
        <a href>
          <img src="https://www.evaair.com/images/zhtw/new_star_logo_tcm27-38762.png" />
        </a>
        <p>Copyright © EVA Airways. All rights reserved.</p>
      </div>
      <div class="right">
        <a href>
          <img src="https://www.evaair.com/images/zhtw/skytrax_tcm27-43165.png" />
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Foot"
};
</script>

<style>
.copyright {
  display: flex;
  justify-content: center;
}
.left {
  margin-right: 20px;
}
.left a img {
  margin: 0px 0px 25px 30px;
}
.left p {
  font-size: 15px;
  color: white;
}
#foot {
  background: #4c806e;
  padding: 30px 0px;
}
</style>
