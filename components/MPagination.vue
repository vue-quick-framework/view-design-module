<template>
  <div class="m-pagination">
    <Page :current="data.current" :page-size="data.pageSize" :total="data.total" @on-change="pageChange" @on-page-size-change="pageSizeChange" show-total show-elevator show-sizer></Page>
  </div>
</template>

<script>
  import { Page } from 'view-design'
  export default {
    props: {
      data: {
        type: Object,
        default () {
          return {
            // 当前页码
            current: 1,
            pageSize: 10,
            // 总条目数
            total: 0
          }
        }
      },
    },
    methods: {
      pageChange (page) {
        this.data.current = page
      },
      pageSizeChange (pageSize) {
        this.data.pageSize = pageSize
      }
    },
    components: {
      Page
    }
  }
</script>

<style lang="scss" scoped>
  .m-pagination {
    padding: 15px;
  }
</style>
