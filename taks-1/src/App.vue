<template>
  <main id="app" @mousemove="mousemove">
    <header>
      <div>
        <img id="app-logo" src="data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4KPHN2ZyB3aWR0aD0iMzcxcHgiIGhlaWdodD0iMTY4cHgiIHZpZXdCb3g9IjAgMCAzNzEgMTY4IiB2ZXJzaW9uPSIxLjEiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgeG1sbnM6eGxpbms9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGxpbmsiPgogICAgPCEtLSBHZW5lcmF0b3I6IFNrZXRjaCA1Mi40ICg2NzM3OCkgLSBodHRwOi8vd3d3LmJvaGVtaWFuY29kaW5nLmNvbS9za2V0Y2ggLS0+CiAgICA8dGl0bGU+bG9nby9idWtrdV9wdXJwbGVfaWNvPC90aXRsZT4KICAgIDxkZXNjPkNyZWF0ZWQgd2l0aCBTa2V0Y2guPC9kZXNjPgogICAgPGcgaWQ9ImxvZ28vYnVra3VfcHVycGxlX2ljbyIgc3Ryb2tlPSJub25lIiBzdHJva2Utd2lkdGg9IjEiIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CiAgICAgICAgPHBhdGggZD0iTTU0LjYzNTEsNjguNTU2IEM1NC42MzUxLDU2LjAzMiA0Ny40MTYxLDQ3LjYzMiAzNi44MDYxLDQ3LjYzMiBDMjYuMTk4MSw0Ny42MzIgMTguOTc3MSw1Ni4wMzIgMTguOTc3MSw2OC41NTYgQzE4Ljk3NzEsODEuMDggMjYuMzQ0MSw4OS43NzQgMzYuODA2MSw4OS43NzQgQzQ3LjI2ODEsODkuNzc0IDU0LjYzNTEsODEuMDggNTQuNjM1MSw2OC41NTYgTTczLjIwMTEsNjguNzAyIEM3My4yMDExLDkwLjUxMSA1OC42MTQxLDEwNS44MzYgMzcuOTg2MSwxMDUuODM2IEMzMS4yMDgxLDEwNS44MzYgMjQuMTM1MSwxMDMuNjI1IDE4Ljk3NzEsOTguNDY4IEwxOC45NzcxLDEwNC4zNjEgTDEuMDAwMSwxMDQuMzYxIEwxLjAwMDEsMSBMMTguOTc3MSwxIEwxOC45NzcxLDM4LjkzOCBDMjQuMTM1MSwzMy43ODIgMzEuMjA4MSwzMS41NzEgMzcuOTg2MSwzMS41NzEgQzU4LjYxNDEsMzEuNTcxIDczLjIwMTEsNDYuODk2IDczLjIwMTEsNjguNzAyIFogTTE0NS4xMDk3LDMzLjA0MzMgTDE0NS4xMDk3LDEwNC4zNjEzIEwxMjcuMTMyNywxMDQuMzYxMyBMMTI3LjEzMjcsOTkuMDU2MyBDMTIyLjg1OTcsMTAzLjQ3ODMgMTE2LjY3MjcsMTA1LjgzNjMgMTA5LjE1NzcsMTA1LjgzNjMgQzkyLjk0OTcsMTA1LjgzNjMgODIuMTkyNyw5NS4yMjYzIDgyLjE5MjcsNzcuODM3MyBMODIuMTkyNywzMy4wNDMzIEwxMDAuMTY4NywzMy4wNDMzIEwxMDAuMTY4Nyw3NC4xNTYzIEMxMDAuMTY4Nyw4NC4wMjczIDEwNS4xNzg3LDg5LjYyNTMgMTEzLjU3NzcsODkuNjI1MyBDMTIxLjgyODcsODkuNjI1MyAxMjcuMTMyNyw4My44NzkzIDEyNy4xMzI3LDc0LjE1NjMgTDEyNy4xMzI3LDMzLjA0MzMgTDE0NS4xMDk3LDMzLjA0MzMgWiBNMjA2LjEwMTksMTA0LjM2MTIgTDE3OC4yNTE5LDYxLjQ4MzIgTDE3OC4yNTE5LDEwNC4zNjEyIEwxNjAuMjc1OSwxMDQuMzYxMiBMMTYwLjI3NTksMS4wMDAyIEwxNzguMjUxOSwxLjAwMDIgTDE3OC4yNTE5LDU5LjEyNTIgTDIwMS41MzI5LDMzLjA0MzIgTDIyMy4wNDU5LDMzLjA0MzIgTDE5OS4xNzQ5LDYwLjE1NjIgTDIyOC4wNTU5LDEwNC4zNjEyIEwyMDYuMTAxOSwxMDQuMzYxMiBaIE0yNzkuOTEzNCwxMDQuMzYxMiBMMjUyLjA2MzQsNjEuNDgzMiBMMjUyLjA2MzQsMTA0LjM2MTIgTDIzNC4wODg0LDEwNC4zNjEyIEwyMzQuMDg4NCwxLjAwMDIgTDI1Mi4wNjM0LDEuMDAwMiBMMjUyLjA2MzQsNTkuMTI1MiBMMjc1LjM0NTQsMzMuMDQzMiBMMjk2Ljg1NzQsMzMuMDQzMiBMMjcyLjk4NjQsNjAuMTU2MiBMMzAxLjg2ODQsMTA0LjM2MTIgTDI3OS45MTM0LDEwNC4zNjEyIFogTTM2OS41MDQyLDMzLjA0MzMgTDM2OS41MDQyLDEwNC4zNjEzIEwzNTEuNTI4MiwxMDQuMzYxMyBMMzUxLjUyODIsOTkuMDU2MyBDMzQ3LjI1NTIsMTAzLjQ3ODMgMzQxLjA2NzIsMTA1LjgzNjMgMzMzLjU1MzIsMTA1LjgzNjMgQzMxNy4zNDUyLDEwNS44MzYzIDMwNi41ODgyLDk1LjIyNjMgMzA2LjU4ODIsNzcuODM3MyBMMzA2LjU4ODIsMzMuMDQzMyBMMzI0LjU2NDIsMzMuMDQzMyBMMzI0LjU2NDIsNzQuMTU2MyBDMzI0LjU2NDIsODQuMDI3MyAzMjkuNTc0Miw4OS42MjUzIDMzNy45NzMyLDg5LjYyNTMgQzM0Ni4yMjQyLDg5LjYyNTMgMzUxLjUyODIsODMuODc5MyAzNTEuNTI4Miw3NC4xNTYzIEwzNTEuNTI4MiwzMy4wNDMzIEwzNjkuNTA0MiwzMy4wNDMzIFogTTIyMS4yNjEsMTMxLjMyNSBMMzY5LjUwNCwxMzEuMzI1IEwzNjkuNTA0LDE0OS4zMDEgTDIyMS4yNjEsMTQ5LjMwMSBDMjEzLjA3OCwxNDkuMzAxIDIwNS40MDcsMTUxLjUxIDE5OC43OTEsMTU1LjM0NiBDMTkzLjU0NiwxNTguMzg5IDE4OC45NjQsMTYyLjQ1MiAxODUuMzM0LDE2Ny4yNzcgTDE4NS4yODQsMTY3LjI3NyBDMTgxLjY1NSwxNjIuNDUyIDE3Ny4wNzMsMTU4LjM4OSAxNzEuODI3LDE1NS4zNDYgQzE2NS4yMTIsMTUxLjUxIDE1Ny41NCwxNDkuMzAxIDE0OS4zNTgsMTQ5LjMwMSBMMSwxNDkuMzAxIEwxLDEzMS4zMjUgTDE0OS4zNTgsMTMxLjMyNSBDMTYyLjcyOSwxMzEuMzI1IDE3NS4xMTYsMTM1LjUwOSAxODUuMzEsMTQyLjYyMSBDMTk1LjUwMiwxMzUuNTA5IDIwNy44OSwxMzEuMzI1IDIyMS4yNjEsMTMxLjMyNSBaIiBpZD0iQ29tYmluZWQtU2hhcGUiIGZpbGw9IiM2MTU2OTkiPjwvcGF0aD4KICAgIDwvZz4KPC9zdmc+" style="margin-left: 45%; margin-right: 31%;">
      </div>
      <br>
      <section class="new-book">
        <h2>{{bigTitle}}</h2>
      </section>
    </header>
    <section class="products" href="./detile-product">
      <ul>
        <Product
        v-for="product in products"
        :key="product.color"
        :product="product"
      />
      </ul>
    </section>
  </main>
</template>

<script>
import Product from './components/Product';
export default {
  name: 'app',
  components: {
    Product
  },
  data () {
    return {
      products: [
        {
          title: 'Gevano',
          color: 'blue',
          bgtext: 'Zahra Vita',
          name: 'Zahra Vita',
          price: '99.000',
          src: require('./assets/bku-10940.png')
        },
        {
          title: 'Unlimited You',
          color: 'tosca',
          bgtext: 'Wirda Mansyur',
          name: 'Wirda Mansyur',
          price: '99.000',
          src: require('./assets/bku-8640.png')
        },
        {
          title: 'Mommyclopedia',
          color: 'bablue',
          bgtext: 'Dr. Meta Hanindita, Sp.A.(K)',
          name: 'Dr. Meta Hanindita, Sp.A.(K)',
          price: '99.000',
          src: require('./assets/bku-10960.png')
        }
      ],
      bigTitle:'New Book',
    }
  },
  methods: {
    mousemove (e) {
      let mouseX = e.clientX;
      let mouseY = e.clientY;
      let products = document.querySelectorAll('.products .product');
      for (let i = 0; i < products.length; i++) {
        let product = products[i];
        let product_image = product.querySelector('.product-image-wrap');
        let img_x = mouseX - this.coords(product_image).x;
        let img_y = mouseY - this.coords(product_image).y;
        product_image.style.transform = `translateY(-${img_y/40}px) translateX(-${img_x/40}px) translateZ(100px)`;
        let bgtext = product.querySelector('.bg-text');
        let bg_x = mouseX - this.coords(bgtext).x;
        bgtext.style.transform = `translateX(${bg_x/25}px)`;
      }
    },
    coords (el) {
      let coords = el.getBoundingClientRect();
      return {
        x: coords.left / 2,
        y: coords.top / 2
      }
    }
  }
}
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  body {
    font-family: 'montseratt', sans-serif;
  }
  main {
    width: 100vw;
    min-height: 100vh;
    overflow: hidden;
    background-color: #EEE;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .products {
    display: flex;
    max-width: 1280px;
    padding: 25px;
    margin: 0 auto;
  }
  #app{
    position: relative;
    width: 100%;
    max-width: 750px;
    margin: 0 auto;
    overflow:hidden;
    box-shadow:0 2px 5px 0 rgba(0,0,0,0.16),0 2px 10px 0 rgba(0,0,0,0.12);
  }
  header{
    position:fixed;
    height:50px;
    width: 100%;
    max-width: 750px;
    background-color:#fff;
    color: rgb(64, 96, 145);
    top:0;
    z-index:99;
    border-bottom:3px solid beige;
    padding: 8px 16px !important;
   }
   .logo{
    position:fixed;
    height:50px;
    width:100%;
    max-width:800px;
    background-color:#fff;
    top:50px;
    left: 20%;
    z-index: 99;
    border-bottom:1px solid beige;
   }
   #app-logo{
    position: relative;
    top:0;
    width:78px;
    margin:auto
   }
</style>