<template>
    <div class="services__box">
      <div class="header">
        <span class="batsu"></span>
      </div>
      <div class="content">
        This is our service.<br/>
        This is our service.<br/>
        This is our service.<br/>
        This is our service.<br/>
        This is our service.<br/>
        This is our service.<br/>
        This is our service.<br/>
        </div>
    </div>
</template>

<style lang="scss">

  .services {
    &__box {
      margin-top: 20px;
      border: 2px solid black;
      background-color: $white;
      .header {
        border-bottom: 2px solid black;
        padding: 4px 5px 0px 5px;
        // height: 15px;
        width: 100%;
        .batsu{
            display: block;
            width: 20px;/*枠の大きさ*/
            height: 20px;/*枠の大きさ*/
            position: relative;
            cursor: pointer;
        }
        .batsu::before, .batsu::after{
            content: "";
            display: block;
            width: 100%;/*バツ線の長さ*/
            height: 2px;/*バツ線の太さ*/
            background: #000;
            transform: rotate(45deg);
            transform-origin:0% 50%;
            position: absolute;
            left: 14%;
        }
        .batsu::after{
            transform: rotate(-45deg);
            transform-origin:100% 50%;
            left: auto;
            right: 14%;
        }
      }
      .content {
        padding: 20px;
      }
    }
  }

</style>
