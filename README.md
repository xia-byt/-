# -
天猫订单查询<div style="text-align:center;margin:20px 0;">
  <h3>请输入订单号查询中奖信息</h3>
  <input type="text" id="orderInput" placeholder="请输入订单号" style="font-size:16px;padding:5px 10px;width:60%;">
  <button onclick="checkPrize()" style="padding:6px 12px;font-size:16px;">查询</button>
  <div id="result" style="margin-top:15px;font-size:16px;"></div>
</div>

<script>
  var prizeData = [
    {"订单信息":"4359819746237081339","活动权益":"5折购机","排名":1},
    {"订单信息":"2584951068311927053","活动权益":"5折购机","排名":2},
    {"订单信息":"2584645503743705291","活动权益":"5折购机","排名":3}
    // 此处省略，建议只保留前几条，更多数据推荐托管外链
  ];
  function checkPrize() {
    var input = document.getElementById("orderInput").value.trim();
    var result = prizeData.find(p => p["订单信息"] === input);
    document.getElementById("result").innerHTML = result ?
      `🎉 恭喜，获得：<b>${result["活动权益"]}</b>（排名第 ${result["排名"]} 位）` :
      "未查询到中奖信息，请核对订单号是否正确。";
  }
</script>
