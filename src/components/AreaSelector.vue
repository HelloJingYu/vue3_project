<template>
  <div class="searchInput">
    <input v-model="inputValue" type="search" class="searchInputBar" placeholder="目的地" @keyup="checkValue"/><button
      class="searchIcon"
    >
      <SvgIcon v-if="visible" class="icon" name="search"></SvgIcon>
    </button>
  </div>
  <div class="searchInput">
    <input v-model="inputValue" type="search" class="searchInputBar" placeholder="搜尋關鍵字" @keyup="checkValue"/><button
      class="searchIcon"
    >
      <SvgIcon v-if="visible" class="icon" name="search"></SvgIcon>
    </button>
  </div>
  <div class="searchInput">
    <input v-model="inputValue" type="search" class="searchInputBar" placeholder="這是啥?" @keyup="checkValue"/><button
      class="searchIcon"
    >
      <SvgIcon v-if="visible" class="icon" name="search"></SvgIcon>
    </button>
  </div>

</template>
<script>
export default {
  name: 'AreaSelector',
}
</script>
<script setup>
const visible=true;</script>
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

.searchInput {
  display: flex;
  padding: 24px 0;
}

.searchIcon {
  margin: -2.3rem;
  background: none;
  border: none;
}

.icon {
  width: 18px;
}

.searchInputBar {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding: 8px 12px;
  background: #fafafa;
  min-width: 306px;

  /* line 8% */

  border: 1px solid rgba(0, 0, 0, 0.08);
  border-radius: 8px;

  &:focus {
    outline: none !important;
  }

  ::placeholder {
    color: $text-2;
  }
}
</style>
