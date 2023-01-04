<template>
  <div class="card">
    <div class="card__image"><img src="../assets/images/img1.png" /></div>
    <div class="card__content">
      <h2 class="title">2021臺北燈節</h2>
      <p class="date"><SvgIcon class="icon" name="clock"></SvgIcon>2021-12-17 ~ 2021-12-26</p>
      <p class="location"><SvgIcon class="icon" name="location"></SvgIcon>臺北市 萬華區</p>
    </div>
  </div>
</template>
<script>
export default {
  name: 'CardArea',
}
</script>
<style lang="scss" scoped>
.card {
  width: 330px;
  border-radius: 16px;
  background: $white;
  transition: box-shadow 0.5s;
  box-shadow: 0px 0px 1.5rem #00000019;
  cursor: pointer;

  .card__image {
    width: 100%;
    height: 182px;
    object-fit:cover;
    img{
      border-radius: 16px 16px 0 0;
    }
  }

  .card__content {
    padding: 6px 17px 17px 10px;
    .title {
      font-size: $title;
      line-height: 1.5rem;
      letter-spacing: 0.15px;
      margin: 0 6px;
    }
    .date {
      font-size: $font-note;
      letter-spacing: 0.25px;
      text-align: left;
      padding: 4px 0;
      margin: 0%;
    }
    .location {
      @extend.date;
      color: $text-2;
    }
  }
}

.icon {
  width: 18px;
  height: 18px;
}
</style>
