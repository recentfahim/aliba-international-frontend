<template>
<div class="product-grid">
  <div>
    <div>
      <img src="https://ae01.alicdn.com/kf/Ha43529c630d44f74bd8d50733e9a9633S/Rc-car-1-12-4WD-update-version-2-4G-radio-remote-control-car-car-toy-car.jpg">
    </div>
    <div class="product-des-container">
      <div class="product-title">
        <p>Original Lenovo XT91 TWS Earphone Wireless Bluetooth Headphones AI Control Gaming Headset Stereo bass With Mic Noise Reduction</p>
      </div>
      <div class="product-price">
        <p>BDT 305.56</p>
      </div>
      <div class="product-sold">
        <p>802 sold</p>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
name: "SearchProduct"
}
</script>

<style scoped>
.product-grid{
  background-color: #ffffff;
  margin-top: 10px;
  border-radius: 8px;
}
.product-des-container{
  margin: 5px 10px 5px 10px;
  padding-bottom: 1px;
}
.product-title{
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
.product-title p{
  color: #333;
  vertical-align: middle;
  width: 100%;
  height: 16px;
  margin-bottom: 2px;
  line-height: 14px;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}
.product-price p{
  margin-top: 3px;
  font-size: 16px;
  line-height: 22px;
  font-weight: 700;
  color: #000;
  font-family: Open Sans,Arial,Helvetica,sans-serif,Heiti;
}
.product-sold{
  margin-top: -15px;
}
</style>