<script>
  export default {
    props: {
      css: {
        type: Object,
        default() {
          return {
            infoClass: 'left floated left aligned six wide column'
          }
        }
      }
    },
    data: function () {
      return {
        eventPrefix: 'vuetable-pagination-info:',
        tablePagination: null,
        tablePageList: [15, 30, 100, 250, 500]
      }
    },
    methods: {
      setPageSize (e) {
        this.$emit(this.eventPrefix+'change-page-size', e.target.value)
      },
      setPaginationData(tablePagination) {
        this.tablePagination = tablePagination
      },
      setPageList(tablePageList) {
        this.tablePageList = tablePageList
      },
      resetData() {
        this.tablePagination = null
      }
    },
  }
</script>
