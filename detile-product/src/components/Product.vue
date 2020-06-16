<template>
  <div class="product">
    <div :class="'product-inner ' + product.color">
      <div class="product-text-wrap">
        <h2 class="bg-text">{{ product.bgtext }}</h2>
      </div>
      <div class="product-image-wrap">
        <img :src="product.src" class="image" />
      </div>
      <div class="product-detail">
        <div class="title-distance">
            <div class="title"><h2>{{ product.title }}</h2></div>
        </div>
        <div class="author">by
                <span class="author-name">{{ product.name }}</span>
        </div>
        <br>
        <div class="price">{{ product.price }}</div>
        <br>
        <div class="info">
          <div class="list">
            <div class="name-info">Kategori</div>
            <div class="desc">{{ product.kategori }}</div>
          </div>
          <div class="list">
            <div class="name-info">Bahasa</div>
            <div class="desc">{{ product.bahasa }}</div>
          </div>
          <div class="list">
            <div class="name-info">Status</div>
            <div class="desc">{{ product.status }}</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'product',
  props: ['product'],
}
</script>

<style>
  .product {
    flex: 1 1 33.333%;
    width: 100%;
    margin-top: 10%;
    max-width:500px;
    padding: 25px;
  }
  .product-inner {
    position: relative;
    padding: 55px;
    box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.25);
    perspective: 1000px;
  }
  .product-inner.blue {
    background-image: linear-gradient(to bottom right, #608dc0, #284866);
  }
  .product-inner.tosca {
    background-image: linear-gradient(to bottom left, #24D484, #2474C4 70%);
  }
  .product-inner.bablue {
    background-image: linear-gradient(to bottom right, #8e97b6, #1168D4);
  }
  .product-text-wrap {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: 0;
    overflow: hidden;
    perspective: 1000px;
  }
  
  .product-text-wrap h2 {
    color: hsl(0, 0%, 19%);
    font-size: 128px;
    font-weight: 900;
    opacity: 0.2;
    transform-origin: center;
  }
  .product-image-wrap {
    position: relative;
    z-index: 1;
    transform-origin: center;
  }
  .product-image-wrap .image {
    width: 100%;
    filter: drop-shadow(0px 0px 12px rgba(0, 0, 0, 0.25));
  }
  .title-distance{
    height:30px
   }
   .product-detail .author{
    font-size:12px
   }
   .product-detail .author-name{
    color:#464453;
    letter-spacing:0
   }
   .price{
    position:relative;
    font-size:18px;
    font-weight:700;
    color:#02a590
   }
  .product-detail {
    background-color: #FFF;
    padding: 25px;
    margin: 0px -25px -25px;
  }
  .product-detail h2 {
    font-size: 24px;
    font-weight: 700;
    color: #676767;
    margin-bottom: 15px;
  }
  .product-detail p {
    font-size: 14px;
    line-height: 1.5;
    font-weight: 300;
    color: #676767;
  }

  .info{
    overflow: hidden;
    padding: 16px 16px 18px;
  }
  .info .list{
    float: left;
    width: 33.3333333%;
  }
  .info .list .name-info{
    font-size: 12px;
    letter-spacing: .4px;
    color: #6e6c7c;
    margin-bottom: 2px;
  }
  .info .list .desc{
    font-size: 14x;
    letter-spacing: .2px;
    color: #464453;
  }
  .container {
    padding: 16px;
    max-width: 650px;
    margin-left: auto;
    margin-right: auto;
    padding-left: 20px;
    padding-right: 20px;
    width: 100%;
    background: #fff;
   }
   
  .container .tabs .input{
    position: absolute;
    opacity: 0;
  }
  input[type="radio"] {
    box-sizing: border-box;
    padding: 0;
  }

  label, legend {
      font-weight: 400;
      letter-spacing: 0;
  }

  label {
      color: rgba(0,0,0,.38);
      display: inline-block;
      font-size: 16px;
      line-height: 1.5;
  }

  .sinopsis{
      font-size: 14px;
      font-weight: 500;
      line-height: 1.57;
      color: #504d69;
  }

  .sinopsis .desc{
    height: 350px;
  }
  .add-to-cart {
      box-shadow: 0 -10px 10px 0 rgba(0,0,0,.1);
      background-color: #fff;
      padding: 9px 16px 6px;
      position: fixed;
      bottom: 0;
      left: 0;
      right: 0;
      width: 100%;
      max-width: 480px;
      margin: 0 auto;
      z-index: 1;
  }
  .add-to-cart .price{
      padding-bottom: 10px;
      border-bottom: 1px solid #d8d8d8;
  }
  .add-to-cart .action{
      padding-top: 10px;
  }
  .row {
      -ms-flex-wrap: wrap;
      display: -ms-flexbox;
      display: flex;
      flex-wrap: wrap;
      margin-left: -20px;
      margin-right: -20px;
  }

  .col-6{
      min-height: 1px;
      padding-left: 20px;
      padding-right: 20px;
      position: relative;
      width: 100%;
      -ms-flex: 0 0 50%;
      flex: 0 0 50%;
      max-width: 50%;
  }

  .add-to-cart .action .button-buy{
      font-size: 14px;
      letter-spacing: .2px;
      text-align: center;
      color: #fff;
      background-color: #615699;
      width: 100%;
  }
  .btn:not(:disabled):not(.disabled) {
      cursor: pointer;
  }
  .btn {
      transition-duration: .39s;
  }
  .btn {
      -moz-user-select: none;
      -ms-user-select: none;
      -webkit-user-select: none;
      background-color: transparent;
      background-image: none;
      border: 0;
      border-radius: 2px;
      box-shadow: 0 0 4px 0 rgba(0,0,0,.14),0 3px 4px 0 rgba(0,0,0,.12),0 1px 5px 0 rgba(0,0,0,.2);
      color: rgba(0,0,0,.87);
      display: inline-block;
      font-size: .875rem;
      font-weight: 500;
      line-height: 1;
      margin: 0;
      max-width: 100%;
      min-width: 5.5rem;
      padding: .6875rem 1rem;
      position: relative;
      text-align: center;
      text-transform: uppercase;
      transition-duration: .3s;
      transition-property: box-shadow;
      transition-timing-function: cubic-bezier(.4,0,.2,1);
      user-select: none;
      vertical-align: middle;
      white-space: nowrap;
  }

  .add-to-cart .price .nominal{
      font-size: 20px;
      line-height: 1.5;
      color: #02a590;
      padding-top: 8px;
  }
  .add-to-cart .price .count .input-box{
      display: -ms-flexbox;
      display: flex;
      border: 1px solid #ddedeb;
      padding: 8px 10px;
      -ms-flex-pack: justify;
      justify-content: space-between;
  }
  .add-to-cart .action .action-cart .button-cart{
      font-size: 14px;
      color: #615699;
  }

</style>