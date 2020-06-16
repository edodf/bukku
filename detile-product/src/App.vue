<template>
  <main id="app" @mousemove="mousemove">
    <header>
      <div>
        <img id="app-logo" src="data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4KPHN2ZyB3aWR0aD0iMzcxcHgiIGhlaWdodD0iMTY4cHgiIHZpZXdCb3g9IjAgMCAzNzEgMTY4IiB2ZXJzaW9uPSIxLjEiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgeG1sbnM6eGxpbms9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGxpbmsiPgogICAgPCEtLSBHZW5lcmF0b3I6IFNrZXRjaCA1Mi40ICg2NzM3OCkgLSBodHRwOi8vd3d3LmJvaGVtaWFuY29kaW5nLmNvbS9za2V0Y2ggLS0+CiAgICA8dGl0bGU+bG9nby9idWtrdV9wdXJwbGVfaWNvPC90aXRsZT4KICAgIDxkZXNjPkNyZWF0ZWQgd2l0aCBTa2V0Y2guPC9kZXNjPgogICAgPGcgaWQ9ImxvZ28vYnVra3VfcHVycGxlX2ljbyIgc3Ryb2tlPSJub25lIiBzdHJva2Utd2lkdGg9IjEiIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CiAgICAgICAgPHBhdGggZD0iTTU0LjYzNTEsNjguNTU2IEM1NC42MzUxLDU2LjAzMiA0Ny40MTYxLDQ3LjYzMiAzNi44MDYxLDQ3LjYzMiBDMjYuMTk4MSw0Ny42MzIgMTguOTc3MSw1Ni4wMzIgMTguOTc3MSw2OC41NTYgQzE4Ljk3NzEsODEuMDggMjYuMzQ0MSw4OS43NzQgMzYuODA2MSw4OS43NzQgQzQ3LjI2ODEsODkuNzc0IDU0LjYzNTEsODEuMDggNTQuNjM1MSw2OC41NTYgTTczLjIwMTEsNjguNzAyIEM3My4yMDExLDkwLjUxMSA1OC42MTQxLDEwNS44MzYgMzcuOTg2MSwxMDUuODM2IEMzMS4yMDgxLDEwNS44MzYgMjQuMTM1MSwxMDMuNjI1IDE4Ljk3NzEsOTguNDY4IEwxOC45NzcxLDEwNC4zNjEgTDEuMDAwMSwxMDQuMzYxIEwxLjAwMDEsMSBMMTguOTc3MSwxIEwxOC45NzcxLDM4LjkzOCBDMjQuMTM1MSwzMy43ODIgMzEuMjA4MSwzMS41NzEgMzcuOTg2MSwzMS41NzEgQzU4LjYxNDEsMzEuNTcxIDczLjIwMTEsNDYuODk2IDczLjIwMTEsNjguNzAyIFogTTE0NS4xMDk3LDMzLjA0MzMgTDE0NS4xMDk3LDEwNC4zNjEzIEwxMjcuMTMyNywxMDQuMzYxMyBMMTI3LjEzMjcsOTkuMDU2MyBDMTIyLjg1OTcsMTAzLjQ3ODMgMTE2LjY3MjcsMTA1LjgzNjMgMTA5LjE1NzcsMTA1LjgzNjMgQzkyLjk0OTcsMTA1LjgzNjMgODIuMTkyNyw5NS4yMjYzIDgyLjE5MjcsNzcuODM3MyBMODIuMTkyNywzMy4wNDMzIEwxMDAuMTY4NywzMy4wNDMzIEwxMDAuMTY4Nyw3NC4xNTYzIEMxMDAuMTY4Nyw4NC4wMjczIDEwNS4xNzg3LDg5LjYyNTMgMTEzLjU3NzcsODkuNjI1MyBDMTIxLjgyODcsODkuNjI1MyAxMjcuMTMyNyw4My44NzkzIDEyNy4xMzI3LDc0LjE1NjMgTDEyNy4xMzI3LDMzLjA0MzMgTDE0NS4xMDk3LDMzLjA0MzMgWiBNMjA2LjEwMTksMTA0LjM2MTIgTDE3OC4yNTE5LDYxLjQ4MzIgTDE3OC4yNTE5LDEwNC4zNjEyIEwxNjAuMjc1OSwxMDQuMzYxMiBMMTYwLjI3NTksMS4wMDAyIEwxNzguMjUxOSwxLjAwMDIgTDE3OC4yNTE5LDU5LjEyNTIgTDIwMS41MzI5LDMzLjA0MzIgTDIyMy4wNDU5LDMzLjA0MzIgTDE5OS4xNzQ5LDYwLjE1NjIgTDIyOC4wNTU5LDEwNC4zNjEyIEwyMDYuMTAxOSwxMDQuMzYxMiBaIE0yNzkuOTEzNCwxMDQuMzYxMiBMMjUyLjA2MzQsNjEuNDgzMiBMMjUyLjA2MzQsMTA0LjM2MTIgTDIzNC4wODg0LDEwNC4zNjEyIEwyMzQuMDg4NCwxLjAwMDIgTDI1Mi4wNjM0LDEuMDAwMiBMMjUyLjA2MzQsNTkuMTI1MiBMMjc1LjM0NTQsMzMuMDQzMiBMMjk2Ljg1NzQsMzMuMDQzMiBMMjcyLjk4NjQsNjAuMTU2MiBMMzAxLjg2ODQsMTA0LjM2MTIgTDI3OS45MTM0LDEwNC4zNjEyIFogTTM2OS41MDQyLDMzLjA0MzMgTDM2OS41MDQyLDEwNC4zNjEzIEwzNTEuNTI4MiwxMDQuMzYxMyBMMzUxLjUyODIsOTkuMDU2MyBDMzQ3LjI1NTIsMTAzLjQ3ODMgMzQxLjA2NzIsMTA1LjgzNjMgMzMzLjU1MzIsMTA1LjgzNjMgQzMxNy4zNDUyLDEwNS44MzYzIDMwNi41ODgyLDk1LjIyNjMgMzA2LjU4ODIsNzcuODM3MyBMMzA2LjU4ODIsMzMuMDQzMyBMMzI0LjU2NDIsMzMuMDQzMyBMMzI0LjU2NDIsNzQuMTU2MyBDMzI0LjU2NDIsODQuMDI3MyAzMjkuNTc0Miw4OS42MjUzIDMzNy45NzMyLDg5LjYyNTMgQzM0Ni4yMjQyLDg5LjYyNTMgMzUxLjUyODIsODMuODc5MyAzNTEuNTI4Miw3NC4xNTYzIEwzNTEuNTI4MiwzMy4wNDMzIEwzNjkuNTA0MiwzMy4wNDMzIFogTTIyMS4yNjEsMTMxLjMyNSBMMzY5LjUwNCwxMzEuMzI1IEwzNjkuNTA0LDE0OS4zMDEgTDIyMS4yNjEsMTQ5LjMwMSBDMjEzLjA3OCwxNDkuMzAxIDIwNS40MDcsMTUxLjUxIDE5OC43OTEsMTU1LjM0NiBDMTkzLjU0NiwxNTguMzg5IDE4OC45NjQsMTYyLjQ1MiAxODUuMzM0LDE2Ny4yNzcgTDE4NS4yODQsMTY3LjI3NyBDMTgxLjY1NSwxNjIuNDUyIDE3Ny4wNzMsMTU4LjM4OSAxNzEuODI3LDE1NS4zNDYgQzE2NS4yMTIsMTUxLjUxIDE1Ny41NCwxNDkuMzAxIDE0OS4zNTgsMTQ5LjMwMSBMMSwxNDkuMzAxIEwxLDEzMS4zMjUgTDE0OS4zNTgsMTMxLjMyNSBDMTYyLjcyOSwxMzEuMzI1IDE3NS4xMTYsMTM1LjUwOSAxODUuMzEsMTQyLjYyMSBDMTk1LjUwMiwxMzUuNTA5IDIwNy44OSwxMzEuMzI1IDIyMS4yNjEsMTMxLjMyNSBaIiBpZD0iQ29tYmluZWQtU2hhcGUiIGZpbGw9IiM2MTU2OTkiPjwvcGF0aD4KICAgIDwvZz4KPC9zdmc+" style="margin-left: 45%; margin-right: 31%;">
      </div>
    </header>
    <section class="products">
        <Product
        v-for="product in products"
        :key="product.color"
        :product="product"
        />
    </section>
    <div class="container">
      <div class="conten">
        <div class="tabs">
          <input id="tab-1" class="input" name="tabs" type="radio" checked="checked"></div>
          <label class="label" for="tab-1">
            <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIvPgogICAgICAgIDxwYXRoIGZpbGw9IiM2MTU2OTkiIGZpbGwtcnVsZT0ibm9uemVybyIgZD0iTTE4LjYyNyAyQzE5LjM4NCAyIDIwIDIuNjQgMjAgMy40MjZ2MTQuODFjMCAuNzg3LS42MTYgMS40MjctMS4zNzMgMS40MjdoLTEuMjV2LjkxYzAgLjc4Ny0uNjE1IDEuNDI3LTEuMzcyIDEuNDI3SDUuMzczQzQuNjE2IDIyIDQgMjEuMzYgNCAyMC41NzRWNS43NjRjMC0uNzg3LjYxNi0xLjQyNyAxLjM3My0xLjQyN2gxLjI1di0uOTFDNi42MjIgMi42NCA3LjIzNyAyIDcuOTk0IDJoMTAuNjMyek0xNi4yOCAyMC41NzR2LS45MTFINy45OTVjLS43NTcgMC0xLjM3My0uNjQtMS4zNzMtMS40MjdWNS40NzhoLTEuMjVhLjI4LjI4IDAgMCAwLS4yNzQuMjg2djE0LjgxYS4yOC4yOCAwIDAgMCAuMjc1LjI4NWgxMC42MzJhLjI4LjI4IDAgMCAwIC4yNzUtLjI4NXptMi42MjItMi4zMzhWMy40MjZhLjI4LjI4IDAgMCAwLS4yNzUtLjI4NUg3Ljk5NWEuMjguMjggMCAwIDAtLjI3NC4yODV2MTQuODFhLjI4LjI4IDAgMCAwIC4yNzQuMjg2aDEwLjYzMmEuMjguMjggMCAwIDAgLjI3NS0uMjg2ek0xNi41OCA1LjE1OGMuMjMyIDAgLjQyLjIzNi40Mi41MjYgMCAuMjkxLS4xODguNTI3LS40Mi41MjdoLTYuMTZjLS4yMzIgMC0uNDItLjIzNi0uNDItLjUyNyAwLS4yOS4xODgtLjUyNi40Mi0uNTI2aDYuMTZ6bTAgMy4xNThjLjIzMiAwIC40Mi4yMzYuNDIuNTI2IDAgLjI5MS0uMTg4LjUyNi0uNDIuNTI2aC02LjE2Yy0uMjMyIDAtLjQyLS4yMzUtLjQyLS41MjYgMC0uMjkuMTg4LS41MjYuNDItLjUyNmg2LjE2em0wIDMuMTU4Yy4yMzIgMCAuNDIuMjM2LjQyLjUyNiAwIC4yOS0uMTg4LjUyNi0uNDIuNTI2aC02LjE2Yy0uMjMyIDAtLjQyLS4yMzUtLjQyLS41MjYgMC0uMjkuMTg4LS41MjYuNDItLjUyNmg2LjE2em0wIDMuMTU4Yy4yMzIgMCAuNDIuMjM1LjQyLjUyNiAwIC4yOS0uMTg4LjUyNi0uNDIuNTI2aC02LjE2Yy0uMjMyIDAtLjQyLS4yMzUtLjQyLS41MjYgMC0uMjkuMTg4LS41MjYuNDItLjUyNmg2LjE2eiIvPgogICAgPC9nPgo8L3N2Zz4K" alt="">
            Deskripsi
          </label>
          <br>
          <br>
          <div class="sinopsis">
            <div class="Stitle">Sinopsis</div>
            <br>
            <div class="desc">
              <span>{{desc}}</span>
            </div>
          </div>
      </div>
    </div>
    <div class="add-to-cart">
      <div class="price">
        <div class="row">
          <div class="col-6 nominal">{{price}}</div>
          <div class="col-6 count">
            <div class="input-box">
              <div class="count-action">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIvPgogICAgICAgIDxjaXJjbGUgY3g9IjEyIiBjeT0iMTIiIHI9IjEwIiBmaWxsPSIjRjJGMkY0Ii8+CiAgICAgICAgPHBhdGggZmlsbD0iI0I5QjlCOSIgZD0iTTE2IDEyLjVIOFYxMWg4eiIvPgogICAgPC9nPgo8L3N2Zz4K" alt="minus">
              </div>
              <div class="result">1</div>
              <div class="count-action">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIvPgogICAgICAgIDxjaXJjbGUgY3g9IjEyIiBjeT0iMTIiIHI9IjEwIiBmaWxsPSIjRjJGMkY0Ii8+CiAgICAgICAgPHBhdGggZmlsbD0iIzYxNTY5OSIgZD0iTTEyLjc1MyAxMS4yNUgxNnYxLjVoLTMuMjQ3VjE2SDExLjI1di0zLjI1SDh2LTEuNWgzLjI1VjhoMS41MDN6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=" alt="plus">
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="action">
        <div class="row">
          <div class="col-6 action-cart">
            <a class="button-cart">
              <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGZpbGw9IiM2MTU2OTkiIGZpbGwtcnVsZT0iZXZlbm9kZCIgZD0iTTEyIDcuNDM4YTUuMzEgNS4zMSAwIDAgMSAuNDMtMi4xMSA1LjQ3IDUuNDcgMCAwIDEgMS4xNzYtMS43MzVBNS41MjEgNS41MjEgMCAwIDEgMTcuNSAyYTUuNTIxIDUuNTIxIDAgMCAxIDMuODk0IDEuNTkzIDUuNDcgNS40NyAwIDAgMSAxLjE3NiAxLjczNWMuMjg3LjY2NS40MyAxLjM3NS40MyAyLjEyNyAwIC43NTEtLjE0MyAxLjQ2LS40MyAyLjEyNmE1LjQ3IDUuNDcgMCAwIDEtMS4xNzYgMS43MzUgNS41MjEgNS41MjEgMCAwIDEtMy4wMyAxLjUyOWwtLjQ2MSAyLjU2NWEuNjk1LjY5NSAwIDAgMS0uNjk1LjU2OGwtMTAuMTU4LjAyLS42MTMgMS4yMzdoMTIuMTgxYy4yMDQgMCAuMzc1LjA3LjUxLjIxMy4xMzcuMTQyLjIwNS4zMS4yMDUuNTA3YS42OTYuNjk2IDAgMCAxLS43MTUuN2gtMi4zMWMuMjczLjM3OC40MS43OTcuNDEgMS4yNTYgMCAuNTgyLS4yMDUgMS4wNzUtLjYxNCAxLjQ4YTIuMDI3IDIuMDI3IDAgMCAxLTEuNDgyLjYwOWMtLjU3OSAwLTEuMDczLS4yMDMtMS40ODItLjYwOGEyLjAwNyAyLjAwNyAwIDAgMS0uNjEzLTEuNDhjMC0uNDYuMTQzLS44OC40My0xLjI1OEg5LjY2NmMuMjcyLjM3OS40MDkuNzk4LjQwOSAxLjI1NyAwIC41ODItLjIwNSAxLjA3NS0uNjEzIDEuNDhBMi4wMjcgMi4wMjcgMCAwIDEgNy45OCAyMmMtLjU4IDAtMS4wNzMtLjIwMy0xLjQ4Mi0uNjA4YTIuMDA3IDIuMDA3IDAgMCAxLS42MTMtMS40OGMwLS40Ni4xNDMtLjg4LjQyOS0xLjI1OEg1LjAyNmMtLjMgMC0uNTE3LS4xMjgtLjY1NC0uMzg1LS4xMzYtLjI1Ny0uMTE1LS41MDcuMDYyLS43NWwxLjUzMy0yLjQ3NEw0Ljc4IDkuMzQ3bC0uNDktMi4yNzFIMS43MTVhLjY4OS42ODkgMCAwIDEtLjUtLjIxM0EuNjkuNjkgMCAwIDEgMSA2LjM1NmEuNjkuNjkgMCAwIDEgLjIxNS0uNTA3LjY4OS42ODkgMCAwIDEgLjUtLjIxM2gzLjE2OGMuMTY0IDAgLjMxNC4wNTQuNDUuMTYzYS43MzcuNzM3IDAgMCAxIC4yNjYuNDA1bC4xMDIuNTA3IDYuMzQ0LjAzYy0uMDMuMjI4LS4wNDUuNDYtLjA0NS42OTd6bS4wNDMuNzEzbC02LjAzNi0uMDIgMS4zNyA2LjQ2OCA5LjIzOC0uMDIuMzA5LTEuNjk4YTUuNTIxIDUuNTIxIDAgMCAxLTMuMzE3LTEuNTY1IDUuNDcgNS40NyAwIDAgMS0xLjE3Ny0xLjczNSA1LjIxOSA1LjIxOSAwIDAgMS0uMzg3LTEuNDN6TTguNDQgMjAuMzc4YS42NzQuNjc0IDAgMCAwIDAtLjkyMy41OTguNTk4IDAgMCAwLS40NS0uMTkyLjYzMS42MzEgMCAwIDAtLjQ2LjE5Mi42MjEuNjIxIDAgMCAwLS4xOTQuNDU2YzAgLjE3Ni4wNjUuMzI4LjE5NC40NTcuMTMuMTI4LjI4My4xOTIuNDYuMTkyLjE3NyAwIC4zMjctLjA2LjQ1LS4xODJ6bTYuNjQyIDBhLjY3NC42NzQgMCAwIDAgMC0uOTIzLjU5OC41OTggMCAwIDAtLjQ1LS4xOTIuNjMxLjYzMSAwIDAgMC0uNDYuMTkyLjYyMS42MjEgMCAwIDAtLjE5NC40NTZjMCAuMTc2LjA2NS4zMjguMTk1LjQ1Ny4xMy4xMjguMjgyLjE5Mi40Ni4xOTIuMTc3IDAgLjMyNi0uMDYuNDUtLjE4MnpNMTcuNSAxMS43NWE0LjE5IDQuMTkgMCAwIDAgMS42OC0uMzM4IDQuMzY2IDQuMzY2IDAgMCAwIDIuMy0yLjI5IDQuMDk2IDQuMDk2IDAgMCAwIC4zNDEtMS42NjdjMC0uNTk0LS4xMTMtMS4xNS0uMzQxLTEuNjY3YTQuMzcgNC4zNyAwIDAgMC0uOTI3LTEuMzYxIDQuNDEgNC40MSAwIDAgMC0xLjM3Mi0uOTJBNC4xOSA0LjE5IDAgMCAwIDE3LjUgMy4xN2E0LjE5IDQuMTkgMCAwIDAtMS42OC4zMzggNC40MSA0LjQxIDAgMCAwLTEuMzczLjkyIDQuMzcgNC4zNyAwIDAgMC0uOTI3IDEuMzYgNC4wOTYgNC4wOTYgMCAwIDAtLjM0MSAxLjY2OGMwIC41OTMuMTEzIDEuMTQ4LjM0MSAxLjY2Ni4yMy41MjIuNTM4Ljk3Ny45MjggMS4zNjcuMzg5LjM4OS44NDYuNjk3IDEuMzcxLjkyNGE0LjE5IDQuMTkgMCAwIDAgMS42ODEuMzM4em0uNTktNC44OGgxLjcwMmMuMTU4IDAgLjMwMi4wNi40MTUuMTczYS41Ny41NyAwIDAgMSAuMTc0LjQxMmMwIC4xNTctLjA2LjI5OS0uMTc0LjQxMWEuNTc5LjU3OSAwIDAgMS0uNDE1LjE3M2gtMS43MDN2MS42ODhjMCAuMTU4LS4wNi4zLS4xNzQuNDEyYS41NzkuNTc5IDAgMCAxLS40MTUuMTczLjU3OS41NzkgMCAwIDEtLjQxNS0uMTczLjU3LjU3IDAgMCAxLS4xNzQtLjQxMlY4LjA0aC0xLjcwM2EuNTc5LjU3OSAwIDAgMS0uNDE1LS4xNzMuNTcuNTcgMCAwIDEtLjE3NC0uNDExYzAtLjE1OC4wNi0uMy4xNzQtLjQxMmEuNTc5LjU3OSAwIDAgMSAuNDE1LS4xNzNoMS43MDNWNS4xODJjMC0uMTU4LjA2LS4zLjE3NC0uNDEyYS41NzkuNTc5IDAgMCAxIC40MTUtLjE3M2MuMTU5IDAgLjMwMi4wNi40MTUuMTczYS41Ny41NyAwIDAgMSAuMTc0LjQxMlY2Ljg3eiIvPgo8L3N2Zz4K" alt="cart">
              <span>Add to Cart</span>
            </a>
          </div>
          <div class="col-6">
            <a class="btn button-buy">Beli</a>
          </div>  
        </div>
      </div>
    </div>
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
      products:[
        {
          title: 'Gevano',
          color: 'blue',
          bgtext: 'Zahra Vita',
          name: 'Zahra Vita',
          price: 'Rp 99.000',
          kategori:'Buku Novel',
          bahasa: 'Indonesia',
          status:'promo',
          src: require('./assets/bku-10940.png'),
        },
      ],
      price: 'Rp 99.000',
      bigTitle:'New Book',
      desc: 'Satria Geovano Brawijaya adalah pemimpin The Marvel, Geng yang menguasai SMA Pelita. Geovano hanya memiliki dua hal yang paling berharga dalam hidupnya, yaitu Omah, Nenek yang mengurusnya sejak kecil dan seluruh anggota The Marvel. Namun semua berubah saat Geovano menolong seorang Pria dan bertemu dengan anak gadisnya yang langsung membuatnya jatuh cinta. Melody Safira Aditama. Kehidupan Geovano sebagai pemimpin The Marvel tak pernah setenang senja, ia memiliki kehidupan yang keras dan selalu dibayangi musuh. Namun kehadiran Safira mampu membuatnya menjadi pribadi yang berbeda. Tapi tak ada manusia yang sempurna. Dengan segala kekurangan Safira yang bisa menyulitkannya, akankah Geovano membiarkan Safira tetap masuk ke dalam hidupnya? Lalu bagaimana dengan Safira? Sanggupkah ia berada di sisi seorang Geovano, Sang Ketua The Marvel?',
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
    flex-direction: column;
    justify-content: center;
    align-items: center;
    position: relative;
    max-width: 650px;
    margin: 0 auto;
    overflow:hidden;
    box-shadow:0 2px 5px 0 rgba(0,0,0,0.16),0 2px 10px 0 rgba(0,0,0,0.12);
  }
  .products {
    display: flex;
    max-width: 1280px;
    padding: 25px;
    margin: 0 auto;
  }
  header{
    position:fixed;
    height:50px;
    width: 100%;
    max-width: 650px;
    background-color:#fff;
    color: rgb(64, 96, 145);
    top:0;
    z-index:99;
    border-bottom:3px solid beige;
    padding: 8px 16px !important;
   }
   #app-logo{
    position: relative;
    top:0;
    width:78px;
    margin:auto
   }
   
</style>