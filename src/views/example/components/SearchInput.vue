<template>
  <div class="searchInput">
    <input type="search" class="searchInputBar" placeholder="搜尋關鍵字" /><button
      class="searchIcon"
    >
      <SvgIcon class="icon" name="search"></SvgIcon>
    </button>
    {{ value }}
  </div>
</template>
<script>
export default {
  name: 'SearchInputExample',
}
</script>
<script setup>
</script>
<style lang="scss" scoped>
.searchInput {
  display: flex;
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
