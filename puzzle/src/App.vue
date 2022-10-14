<script setup>
</script>

<template>
  <main class="main">
    <div class="puzzle_show">
      <img class="bg_pic" src="@/assets/rabbit.jpg" alt="">
      <div class="piece piece_1"></div>
      <div class="piece piece_2"></div>
      <div class="piece piece_3"></div>
      <div class="piece piece_4"></div>
      <div class="piece piece_5"></div>
      <div class="piece piece_6"></div>
      <div class="piece piece_7"></div>
      <div class="piece piece_8"></div>
      <div class="piece piece_9"></div>
    </div>
    <div class="breakUp_box">
      <div class="piece piece_1"></div>
      <div class="piece piece_2"></div>
      <div class="piece piece_3"></div>
      <div class="piece piece_4"></div>
      <div class="piece piece_5"></div>
      <div class="piece piece_6"></div>
      <div class="piece piece_7"></div>
      <div class="piece piece_8"></div>
      <div class="piece piece_9"></div>
    </div>
  </main>
</template>

<style scoped lang="scss">
img {
  max-width: 100%;
  vertical-align: middle;
}

.puzzle_show {
  margin: auto;
  max-width: 900px;
  width: calc(100% - 60px);
  position: relative;

  .bg_pic {
    opacity: .3;
  }

  .piece {
    max-width: 300px;
    width: 33.333%;
    height: 33.333%;
    padding-bottom: 33.333%;
    background-image: url(assets/rabbit.jpg);
    background-size: 300%;
    position: absolute;

    &.piece_1 {
      top: 0;
      left: 0;
      background-position: 0 0;
    }

    &.piece_2 {
      top: 0;
      left: 33.333%;
      background-position: 49.333% 0;
    }

    &.piece_3 {
      top: 0;
      left: 66.666%;
      background-position: 100% 0;
    }

    &.piece_4 {
      top: 33.333%;
      left: 0;
      background-position: 0 49.333%;
    }

    &.piece_5 {
      top: 33.333%;
      left: 33.333%;
      background-position: 49.333% 49.333%;
    }

    &.piece_6 {
      top: 33.333%;
      left: 66.666%;
      background-position: 100% 49.333%;
    }

    &.piece_7 {
      top: 66.666%;
      left: 0;
      background-position: 0% 100%;
    }

    &.piece_8 {
      top: 66.666%;
      left: 33.333%;
      background-position: 49.333% 100%;
    }

    &.piece_9 {
      top: 66.666%;
      left: 66.666%;
      background-position: 100% 100%;
    }
  }

  .breakUp_box{
    .piece{
      
    }
  }
}
</style>
