<template>
  <div class="pagination">
    <button class="pagination__button--hollow">1</button>
    <span>...</span>
    <button class="pagination__button--hollow">3</button>
    <button class="pagination__button--hollow">4</button>
    <button class="pagination__button--solid">5</button>
    <button class="pagination__button--hollow">6</button>
    <button class="pagination__button--hollow">7</button>
    <span>...</span>
    <button class="pagination__button--hollow">10</button>
  </div>
</template>
<script>
export default {
  name: 'PaginationArea',
}
</script>
<script setup></script>
<style lang="scss" scoped>
.pagination {
  margin: 16px;
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 12px;

  span {
    font-style: normal;   
    font-size: 16px;
    font-weight: 400;
    line-height: 24px;
    letter-spacing: 0.5px;
    color: $primary-1;
  }
}

.pagination__button--hollow {
  @include button($primary-1, $white, $white, $bg-1, $primary-1, $primary-1);

  width:44px;
}

.pagination__button--solid {
  @include button($white, $text-1, $text-1, $primary-1, $bg-1, $bg-1);
  
  width:44px;
}
</style>
