<template>
  <div class="box bplist-box">
    <div class="rate">
      <span><b>资产总额:</b></span>
      <p class="dec">
       资产总额 = 可用余额 + 投票总额  + 赎回总额 + 待领分红总额 <br>
      </p>
    </div>
    <div class="rate">
      <span><b>分红比例:</b></span>
      <p class="dec">
        分红比例 = 100% - 佣金比例<br>
      </p>
    </div>
    <div class="rate">
      <span><b>年化利率:</b></span>
      <p class="dec">
        链初始发行量为 10 亿 EOS<br>
        每 3s 一个块，每个块为超级节点奖励 9 EOS <br>
        超级节点每日奖励 = 9 * 20 * 60 * 24 = 259,200 EOS <br>
        超级节点每年奖励 =  超级节点每日奖励 * 365 = 94,608,000 EOS <br>
        投票年化利率 = （超级节点每年奖励 / 23 * 分红比例） / 所投节点总得票数 * 100%
      </p>
    </div>
    <div class="rate">
      <span><b>待领分红:</b></span>
      <p class="dec">
        我的最新票龄 = 我的累计票龄 + 我的投票 * (当前时间 - 我的票龄更新时间)<br>
        节点最新票龄 = 节点累计票龄 + 总得票数 * (当前时间 - 节点票龄更新时间)<br>
        待领分红金额 = （我的最新票龄 / 节点最新票龄） * 奖池金额<br>
        每次修改投票会更新我的累计票龄，每次领取分红会清零我的累计票龄
      </p>
    </div>
    <div class="rate">
      <span><b>BlockOne 解锁：</b></span>
      <p class="dec">
        每 3s 一个块，每个块为BlockOne解锁 1 EOS <br>
        BlockOne每年解锁 =  1 * 20 * 60 * 24 * 365 = 10,512,000 EOS<br>
        每10年解锁约 1 亿 EOS，10年以后继续解锁，永不间断
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RateInstructions',
};
</script>

<style scoped>
.button {
  padding-left: calc(0.625em - 1px);
  padding-right: calc(0.625em - 1px);
}
.is-button span {
  background: #408ee1;
  border-radius: 5px;
  color: #fff;
  border: none;
  padding-left: calc(0.625em - 1px);
  padding-right: calc(0.625em - 1px);
  padding-bottom: calc(0.375em - 1px);
  padding-top: calc(0.375em - 1px);
  text-align: center;
  white-space: nowrap;
  cursor: pointer;
}
/* .bplist-box tbody .is-vote{
  display: none;
} */
.rate {
  margin-bottom: 20px;
}

.dec {
  margin-top: 10px;
}
</style>
