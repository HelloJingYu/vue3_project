<template>
  <h2>不可點</h2>
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
  <h2>可點</h2>
  <div class="pagination">
    <!-- 第一個按鈕 -->
    <button class="pagination__button--hollow" @click="selectedPage(0)">
      {{ 1 }}
    </button>
    <span v-if="predot">...</span>
    <div v-for="(item, index) in totalPage">
      <!-- 顯示當頁前兩頁，for迴圈跑兩個 -->
      <button
        v-if="index != 0 && index != totalPage - 1 && index - pageNow <= 2 && index - pageNow >= 1"
        class="pagination__button--hollow"
        @click="selectedPage(index)"
      >
        {{ index + 1 }}
      </button>
      <!-- 當前頁 -->
      <button
        v-else-if="index != 0 && index != totalPage - 1 && pageNow == index"
        class="pagination__button--solid"
        @click="selectedPage(index)"
      >
        {{ index + 1 }}
      </button>
      <!-- 後兩頁 -->
      <button
        v-else-if="index != 0 && index != totalPage - 1 && pageNow - index <= 2 && pageNow - index >= 1"
        class="pagination__button--hollow"
        @click="selectedPage(index)"
      >
        {{ index + 1 }}
      </button>
    </div>
    <span v-if="nextdot">...</span>
    <!-- 最後一頁 -->
    <button class="pagination__button--hollow" @click="selectedPage(totalPage - 1)">
      {{ totalPage }}
    </button>
  </div>
</template>
<script>
export default {
  name: 'PaginationArea',
}
</script>
<script setup>
import { ref } from 'vue'
// 宣告總頁數、現在頁數
const totalPage = ref(55)
const pageNow = ref(4)
const predot = ref(true)
const nextdot = ref(true)
// 換頁數
const selectedPage = index => {
  pageNow.value = index
  if (index >= 4) predot.value = true
  if (index < 4) predot.value = false
  if (index <= totalPage.value - 4) nextdot.value = true
  if (index > totalPage.value - 4) nextdot.value = false
}
</script>
<style lang="scss" scoped>
.pagination {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin: 16px;

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

  margin: 6px;
  width: 44px;
}

.pagination__button--solid {
  @include button($white, $text-1, $text-1, $primary-1, $bg-1, $bg-1);

  margin: 6px;
  width: 44px;
}
</style>
