<template>
  <div>
    <div class="container">
      
      <div class="page-title-container-new hidden">
        <div class="page-title">
          <h3>Transactions</h3>
        </div>

        <div class="search-block">
          <block-search></block-search>
        </div>
      </div>


      <div class="page-title-container">
        <div class="page-title">
          <h3>Transactions</h3>
          <h6 class="text-muted">Last transactions of all time</h6>
        </div>

        <div class="search-block">
          <block-search></block-search>
        </div>
      </div>

      <div class="row small-blocks">
        <div class="col-md-3"><block-last-block></block-last-block></div>
        <div class="col-md-3"><successful-tx-small-block></successful-tx-small-block></div>
        <div class="col-md-3"><failed-tx-small-block></failed-tx-small-block></div>
        <div class="col-md-3"><pending-tx-small-block></pending-tx-small-block></div>
      </div>
        
      <div class="last-transactions-header">
        <li>TXn#</li>
        <li class="eth">ETH</li>
        <li class="gas">GAS</li>
        <li>WEI</li>
        <li></li>
      </div>

      <div class="row">
        <div class="col-md-12 table-data ">
        
          <div class="latest-blocks-data">
            <block-last-transactions :transactions="txs"></block-last-transactions>
          </div>

   
        </div>
        
      </div>

    </div>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'
  const MAX_ITEMS = 20
  export default Vue.extend({
    name: 'FramesHome',
    data () {
      return {}
    },
    created (){},
    computed:{
      txs(){
           if(this.$store.getters.getTxs.length) return this.$store.getters.getTxs.slice(0, MAX_ITEMS)
          else return []
      }
    }
  })
</script>

<style scoped lang="less">
  @import "~lessPath/sunil/frames/transactions.less";
</style>
