<template>
  <div :class="['vuetable-pagination-info', css.infoClass]">
    <div v-if="tablePagination!=null && tablePagination.total!=0">
      <span v-text="'显示第 '+tablePagination.from+' 到第 '+tablePagination.to+' 条记录，总共 '+tablePagination.total+' 条记录 每页显示 '"></span>
      <select class="form-control" name="size" style="width: auto;display: inline;margin: 0 5px;" @change="setPageSize">
        <option :value="item" v-for="item in tablePageList" v-text="item"></option>
      </select>
      <span> 条记录</span>
    </div>
    <div v-else>
      显示第 0 到第 0 条记录，总共 0 条记录
    </div>
  </div>
</template>

<script>
import PaginationInfoMixin from './VuetablePaginationInfoMixin.vue'

export default {
  mixins: [PaginationInfoMixin],
}
</script>
