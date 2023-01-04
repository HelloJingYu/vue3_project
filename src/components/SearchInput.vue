<template>
  <div class="searchInput">
    <input v-model="inputValue" class="searchInputBar" placeholder="搜尋關鍵字" @keyup="checkValue"/><button
      class="searchIcon"
    >
      <SvgIcon v-if="visible" class="icon" name="search"></SvgIcon>
      <SvgIcon v-else class="icon" name="delete" @click="deleteInput"></SvgIcon>
    </button>
  </div>
</template>
<script>
export default {
  name: 'SearchInputExample',
}
</script>
<script setup>
import { ref } from 'vue'
const inputValue = ref('')
const visible = ref(true)
const checkValue = () =>{
  if(inputValue.value == '')
   visible.value = true
   else
   visible.value = false
}
const deleteInput=()=>{
  inputValue.value = ""
   visible.value = true
}
</script>
<style lang="scss" scoped>
.searchInput {
  display: flex;
  max-width: 306px;//隨便取的
}

.searchIcon {
  margin-left:-2.3rem;
  background: none;
  border: none;
  display: flex;
  align-items: center;
}

.icon {
  width: 18px;
  
}

.searchInputBar {
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding: 8px 12px;
  background: #fafafa;
  line-height: 0%;

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
