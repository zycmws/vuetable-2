<template>
  <ul v-show="tablePagination && tablePagination.last_page > 1" :class="css.wrapperClass">
    <li @click="loadPage(1)" :class="[ css.linkClass, isOnFirstPage ? css.disabledClass : '']">
        <a href="" v-if="css.icons.first != ''" :class="[css.icons.first]"></a>
        <a v-else>&laquo;</a>
    </li>
    <li @click="loadPage('prev')" :class="[ css.linkClass, isOnFirstPage ? css.disabledClass : '']">
        <a v-if="css.icons.next != ''" :class="[css.icons.prev]"></a>
        <a v-else>&nbsp;&lsaquo;</a>
    </li>
    <template v-if="notEnoughPages">
      <template v-for="n in totalPage">
        <li :class="[css.pageClass, isCurrentPage(n) ? css.activeClass : '']">
          <a href="" @click="loadPage(n)" v-html="n"></a>
        </li>
      </template>
    </template>
    <template v-else>
      <template v-for="n in windowSize">
        <li :class="[css.pageClass, isCurrentPage(windowStart+n-1) ? css.activeClass : '']">
          <a href="" @click="loadPage(windowStart+n-1)"  v-html="windowStart+n-1"></a>
        </li>
      </template>
    </template>
    <li @click="loadPage('next')" :class="[ css.linkClass, isOnLastPage ? css.disabledClass : '']">
      <a href="" v-if="css.icons.next != ''" :class="[css.icons.next]"></a>
      <a v-else>&rsaquo;&nbsp;</a>
    </li>
    <li @click="loadPage(totalPage)" :class="[ css.linkClass, isOnLastPage ? css.disabledClass : '']">
      <a href="" v-if="css.icons.last != ''" :class="[css.icons.last]"></a>
      <a v-else>&raquo;</a>
    </li>
  </ul>
</template>

<script>
import PaginationMixin from './VuetablePaginationMixin.vue'

export default {
  mixins: [PaginationMixin],
}
</script>
