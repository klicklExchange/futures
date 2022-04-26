# IDCM Futures Api


**简介**:IDCM Futures Api


**HOST**:https://ctapi.klickl.com/


**联系人**:


**Version**:1.0.0


**接口路径**:SwaggerDocument/Swagger


[TOC]






# futures api


## 批量限价市价委托开仓


**接口地址**:`/api/v1/batchOpenOrder`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded,application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
[
  {
    "symbol": "",
    "side": "",
    "price": 0,
    "type": "",
    "size": 0,
    "reduceOnly": true,
    "ioc": true,
    "postOnly": true,
    "clientId": "",
    "unitMode": "",
    "marginMode": ""
  }
]
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|openOrderRequests|openOrderRequest|body|true|array|openOrderRequest|
|&emsp;&emsp;symbol|合约符号名称||false|string||
|&emsp;&emsp;side|开单方向 0=多 1=空 【多空方向:多=0,空=1】||false|ContractSide|ContractSide|
|&emsp;&emsp;price|价格||false|number(decimal)||
|&emsp;&emsp;type|定单类型 5=市场价 6=限价 【交易类型:市场价=5,限价=6】||false|OrderType|OrderType|
|&emsp;&emsp;size|数量||false|number(decimal)||
|&emsp;&emsp;clientId|客户自定义单号||false|string||
|&emsp;&emsp;unitMode|交易单位模式  0=张 1=币【交易单位模式:张=0,币=1】||false|TradingUnitMode|TradingUnitMode|
|&emsp;&emsp;marginMode|持仓模式【全仓保证金模式=0,逐仓保证金模式=1】||false|MarginMode|MarginMode|


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||orderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|单号|string||
|createTime|委托时间|string(date-time)|string(date-time)|
|contractId||string||
|customerId|客户Id|string||
|orderType|交易类型【交易类型:市场价=5,限价=6】|OrderType|OrderType|
|price|委托价|number(decimal)|number(decimal)|
|totalQty|委托总量|number(decimal)|number(decimal)|
|cumQty|已成交数量|number(decimal)|number(decimal)|
|avgExecutionPrice|成交均价|number(decimal)|number(decimal)|
|status|状态【单状态:挂单=0,部分成交=1,全部成交=2,已撤消=3,无效单=99】|OrderStatus|OrderStatus|
|side|交易类型 0=开多 1=开空  2平=空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】|ContractTradeSide|ContractTradeSide|
|clientId|客户自定义单号|string||
|lastUpdateTime|最后操作时间|string(date-time)|string(date-time)|
|multiple|杠杆倍数|number(decimal)|number(decimal)|
|uFee|手续费|number(decimal)|number(decimal)|
|pnl|收益|number(decimal)|number(decimal)|
|marginMode|保证金模式【全仓保证金模式=0,逐仓保证金模式=1】|MarginMode|MarginMode|
|symbol|合约符号名称|string||
|pnlRate|收益率|number(decimal)|number(decimal)|


**响应示例**:
```javascript
[
	{
		"id": "",
		"createTime": "",
		"contractId": "",
		"customerId": "",
		"orderType": "",
		"price": 0,
		"totalQty": 0,
		"cumQty": 0,
		"avgExecutionPrice": 0,
		"status": "",
		"side": "",
		"clientId": "",
		"lastUpdateTime": "",
		"multiple": 0,
		"uFee": 0,
		"pnl": 0,
		"marginMode": "",
		"symbol": "",
		"pnlRate": 0
	}
]
```


## 批量限价市价委托平仓


**接口地址**:`/api/v1/batchCloseOrder`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded,application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
[
  {
    "symbol": "",
    "side": "",
    "size": 0,
    "price": 0,
    "type": "",
    "clientId": "",
    "unitMode": "",
    "marginMode": ""
  }
]
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|closeOrderRequests|closeOrderRequest|body|true|array|closeOrderRequest|
|&emsp;&emsp;symbol|合约符号名称||false|string||
|&emsp;&emsp;side|多空方向 0=多 1=空【多空方向:多=0,空=1】||false|ContractSide|ContractSide|
|&emsp;&emsp;size|数量||false|number(decimal)||
|&emsp;&emsp;price|价格||false|number(decimal)||
|&emsp;&emsp;type|定单类型 5=市场价 6=限价【交易类型:市场价=5,限价=6】||false|OrderType|OrderType|
|&emsp;&emsp;clientId|客户自定义单号 ||false|string||
|&emsp;&emsp;unitMode|交易单位模式  0=张 1=币【交易单位模式:张=0,币=1】||false|TradingUnitMode|TradingUnitMode|
|&emsp;&emsp;marginMode|持仓模式【全仓保证金模式=0,逐仓保证金模式=1】||false|MarginMode|MarginMode|
|X-RECVWINDOW|recvwindow|header|false|||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||orderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|单号|string||
|createTime|委托时间|string(date-time)|string(date-time)|
|contractId||string||
|customerId|客户Id|string||
|orderType|交易类型【交易类型:市场价=5,限价=6】|OrderType|OrderType|
|price|委托价|number(decimal)|number(decimal)|
|totalQty|委托总量|number(decimal)|number(decimal)|
|cumQty|已成交数量|number(decimal)|number(decimal)|
|avgExecutionPrice|成交均价|number(decimal)|number(decimal)|
|status|状态【单状态:挂单=0,部分成交=1,全部成交=2,已撤消=3,无效单=99】|OrderStatus|OrderStatus|
|side|交易类型 0=开多 1=开空  2平=空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】|ContractTradeSide|ContractTradeSide|
|clientId|客户自定义单号|string||
|lastUpdateTime|最后操作时间|string(date-time)|string(date-time)|
|multiple|杠杆倍数|number(decimal)|number(decimal)|
|uFee|手续费|number(decimal)|number(decimal)|
|pnl|收益|number(decimal)|number(decimal)|
|marginMode|保证金模式【全仓保证金模式=0,逐仓保证金模式=1】|MarginMode|MarginMode|
|symbol|合约符号名称|string||
|pnlRate|收益率|number(decimal)|number(decimal)|


**响应示例**:
```javascript
[
	{
		"id": "",
		"createTime": "",
		"contractId": "",
		"customerId": "",
		"orderType": "",
		"price": 0,
		"totalQty": 0,
		"cumQty": 0,
		"avgExecutionPrice": 0,
		"status": "",
		"side": "",
		"clientId": "",
		"lastUpdateTime": "",
		"multiple": 0,
		"uFee": 0,
		"pnl": 0,
		"marginMode": "",
		"symbol": "",
		"pnlRate": 0
	}
]
```


## 批量止盈止损委托开仓


**接口地址**:`/api/v1/batchOpenKillOrFillOrder`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded,application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
[
  {
    "symbol": "",
    "side": "",
    "fillTriggerPrice": 0,
    "fillTrustPrice": 0,
    "killTriggerPrice": 0,
    "killTrustPrice": 0,
    "tradeSide": "",
    "trustQty": 0,
    "triggerPriceKind": "",
    "unitMode": "",
    "marginMode": ""
  }
]
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|fillOrKillOrderRequests|fillOrKillOrderRequest|body|true|array|fillOrKillOrderRequest|
|&emsp;&emsp;symbol|合约符号名称||true|string||
|&emsp;&emsp;side|方向 0=单向止盈止损  1=双向止盈止损【止盈止损委托单方向:单向止盈止损=0,双向止盈止损=1】||false|FillOrKillOrderSide|FillOrKillOrderSide|
|&emsp;&emsp;fillTriggerPrice|止盈触发价格||false|number(decimal)||
|&emsp;&emsp;fillTrustPrice|止盈委托价格||false|number(decimal)||
|&emsp;&emsp;killTriggerPrice|止损触发价格||false|number(decimal)||
|&emsp;&emsp;killTrustPrice|止损委托价格||false|number(decimal)||
|&emsp;&emsp;tradeSide|交易类型 0=开多 1=开空  2平=空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】||false|ContractTradeSide|ContractTradeSide|
|&emsp;&emsp;trustQty|数量||false|number(decimal)||
|&emsp;&emsp;triggerPriceKind|价格源类型 0=市场 1=标记 2=Index(指数)【K线价格源类型:市场=0,标记=1,Index=2】||false|KLineType|KLineType|
|&emsp;&emsp;unitMode|交易单位 0=张 1=币【交易单位模式:张=0,币=1】||false|TradingUnitMode|TradingUnitMode|
|&emsp;&emsp;marginMode|持仓模式【全仓保证金模式=0,逐仓保证金模式=1】||false|MarginMode|MarginMode|
|X-RECVWINDOW|recvwindow|header|false|||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||fillOrKillOrderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|单号|string||
|createTime|委托时间|string(date-time)|string(date-time)|
|contractId|合约Id|string||
|customerId|客户Id|string||
|multiple|杠杆倍数|number(decimal)|number(decimal)|
|status|状态【止盈止损委托单状态:待生效=0,已撤单=1,已生效=2,触发失败=3】|FillOrKillOrderStatus|FillOrKillOrderStatus|
|side|方向【止盈止损委托单方向:单向止盈止损=0,双向止盈止损=1】|FillOrKillOrderSide|FillOrKillOrderSide|
|tradeSide|交易类型 0=开多 1=开空  2平=空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】|ContractTradeSide|ContractTradeSide|
|marginMode|保证金模式【全仓保证金模式=0,逐仓保证金模式=1】|MarginMode|MarginMode|
|fillTriggerPrice|止盈触发价格|number(decimal)|number(decimal)|
|fillTrustPrice|止盈委托价格 空为市价|number(decimal)|number(decimal)|
|killTriggerPrice|止损触发价格|number(decimal)|number(decimal)|
|killTrustPrice|止损委托价格 空为市价|number(decimal)|number(decimal)|
|trustQty|委托数量|number(decimal)|number(decimal)|
|realTrustQty|实际委托数量|number(decimal)|number(decimal)|
|cumQty|已委托量 |number(decimal)|number(decimal)|
|triggerDirection|触发方向【触发方向:止赢=0,止损=1】|FillOrKillTriggerDirection|FillOrKillTriggerDirection|
|triggerPriceKind|触发价格种类【K线价格源类型:市场=0,标记=1,Index=2】|KLineType|KLineType|
|realTrustPrice|实际委托价格|number(decimal)|number(decimal)|
|lastUpdateTime|最后操作时间|string(date-time)|string(date-time)|
|clientId|客户自定义单号|string||
|orderId|触发生成单号|string||
|symbol|合约符号名称|string||


**响应示例**:
```javascript
[
	{
		"id": "",
		"createTime": "",
		"contractId": "",
		"customerId": "",
		"multiple": 0,
		"status": "",
		"side": "",
		"tradeSide": "",
		"marginMode": "",
		"fillTriggerPrice": 0,
		"fillTrustPrice": 0,
		"killTriggerPrice": 0,
		"killTrustPrice": 0,
		"trustQty": 0,
		"realTrustQty": 0,
		"cumQty": 0,
		"triggerDirection": "",
		"triggerPriceKind": "",
		"realTrustPrice": 0,
		"lastUpdateTime": "",
		"clientId": "",
		"orderId": "",
		"symbol": ""
	}
]
```


## 批量止盈止损委托平仓


**接口地址**:`/api/v1/batchCloseKillOrFillOrder`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded,application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
[
  {
    "symbol": "",
    "side": "",
    "fillTriggerPrice": 0,
    "fillTrustPrice": 0,
    "killTriggerPrice": 0,
    "killTrustPrice": 0,
    "tradeSide": "",
    "trustQty": 0,
    "triggerPriceKind": "",
    "unitMode": "",
    "marginMode": ""
  }
]
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|fillOrKillOrderRequests|fillOrKillOrderRequest|body|true|array|fillOrKillOrderRequest|
|&emsp;&emsp;symbol|合约符号名称||true|string||
|&emsp;&emsp;side|方向 0=单向止盈止损  1=双向止盈止损【止盈止损委托单方向:单向止盈止损=0,双向止盈止损=1】||false|FillOrKillOrderSide|FillOrKillOrderSide|
|&emsp;&emsp;fillTriggerPrice|止盈触发价格||false|number(decimal)||
|&emsp;&emsp;fillTrustPrice|止盈委托价格||false|number(decimal)||
|&emsp;&emsp;killTriggerPrice|止损触发价格||false|number(decimal)||
|&emsp;&emsp;killTrustPrice|止损委托价格||false|number(decimal)||
|&emsp;&emsp;tradeSide|交易类型 0=开多 1=开空  2平=空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】||false|ContractTradeSide|ContractTradeSide|
|&emsp;&emsp;trustQty|数量||false|number(decimal)||
|&emsp;&emsp;triggerPriceKind|价格源类型 0=市场 1=标记 2=Index(指数)【K线价格源类型:市场=0,标记=1,Index=2】||false|KLineType|KLineType|
|&emsp;&emsp;unitMode|交易单位 0=张 1=币【交易单位模式:张=0,币=1】||false|TradingUnitMode|TradingUnitMode|
|&emsp;&emsp;marginMode|持仓模式【全仓保证金模式=0,逐仓保证金模式=1】||false|MarginMode|MarginMode|
|X-RECVWINDOW|recvwindow|header|false|||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||fillOrKillOrderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|单号|string||
|createTime|委托时间|string(date-time)|string(date-time)|
|contractId|合约Id|string||
|customerId|客户Id|string||
|multiple|杠杆倍数|number(decimal)|number(decimal)|
|status|状态【止盈止损委托单状态:待生效=0,已撤单=1,已生效=2,触发失败=3】|FillOrKillOrderStatus|FillOrKillOrderStatus|
|side|方向【止盈止损委托单方向:单向止盈止损=0,双向止盈止损=1】|FillOrKillOrderSide|FillOrKillOrderSide|
|tradeSide|交易类型 0=开多 1=开空  2平=空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】|ContractTradeSide|ContractTradeSide|
|marginMode|保证金模式【全仓保证金模式=0,逐仓保证金模式=1】|MarginMode|MarginMode|
|fillTriggerPrice|止盈触发价格|number(decimal)|number(decimal)|
|fillTrustPrice|止盈委托价格 空为市价|number(decimal)|number(decimal)|
|killTriggerPrice|止损触发价格|number(decimal)|number(decimal)|
|killTrustPrice|止损委托价格 空为市价|number(decimal)|number(decimal)|
|trustQty|委托数量|number(decimal)|number(decimal)|
|realTrustQty|实际委托数量|number(decimal)|number(decimal)|
|cumQty|已委托量 |number(decimal)|number(decimal)|
|triggerDirection|触发方向【触发方向:止赢=0,止损=1】|FillOrKillTriggerDirection|FillOrKillTriggerDirection|
|triggerPriceKind|触发价格种类【K线价格源类型:市场=0,标记=1,Index=2】|KLineType|KLineType|
|realTrustPrice|实际委托价格|number(decimal)|number(decimal)|
|lastUpdateTime|最后操作时间|string(date-time)|string(date-time)|
|clientId|客户自定义单号|string||
|orderId|触发生成单号|string||
|symbol|合约符号名称|string||


**响应示例**:
```javascript
[
	{
		"id": "",
		"createTime": "",
		"contractId": "",
		"customerId": "",
		"multiple": 0,
		"status": "",
		"side": "",
		"tradeSide": "",
		"marginMode": "",
		"fillTriggerPrice": 0,
		"fillTrustPrice": 0,
		"killTriggerPrice": 0,
		"killTrustPrice": 0,
		"trustQty": 0,
		"realTrustQty": 0,
		"cumQty": 0,
		"triggerDirection": "",
		"triggerPriceKind": "",
		"realTrustPrice": 0,
		"lastUpdateTime": "",
		"clientId": "",
		"orderId": "",
		"symbol": ""
	}
]
```


## 批量计划委托单开仓


**接口地址**:`/api/v1/batchOpenPlanOrder`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded,application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
[
  {
    "symbol": "",
    "clientId": "",
    "trustPrice": 0,
    "triggerPrice": 0,
    "trustQty": 0,
    "side": "",
    "triggerPriceKind": "",
    "unitMode": "",
    "marginMode": ""
  }
]
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|planOrderRequests|planOrderRequest|body|true|array|planOrderRequest|
|&emsp;&emsp;symbol|合约符号名称||true|string||
|&emsp;&emsp;clientId|自定义单号||false|string||
|&emsp;&emsp;trustPrice|委托价格 空为市价\n ||false|number(decimal)||
|&emsp;&emsp;triggerPrice|触发价格||false|number(decimal)||
|&emsp;&emsp;trustQty|委托数量||false|number(decimal)||
|&emsp;&emsp;side|交易类型 0=开多仓 1=开空仓  2=平空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】||false|ContractTradeSide|ContractTradeSide|
|&emsp;&emsp;triggerPriceKind|价格源类型 0=市场 1=标记 2=Index(指数) 【K线价格源类型:市场=0,标记=1,Index=2】||false|KLineType|KLineType|
|&emsp;&emsp;unitMode|交易单位 0=张 1=币【交易单位模式:张=0,币=1】||false|TradingUnitMode|TradingUnitMode|
|&emsp;&emsp;marginMode|持仓模式【全仓保证金模式=0,逐仓保证金模式=1】||false|MarginMode|MarginMode|
|X-RECVWINDOW|recvwindow|header|false|||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||planOrderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|单号|string||
|createTime|委托时间|string(date-time)|string(date-time)|
|contractId|合约Id|string||
|customerId|客户Id|string||
|lastUpdateTime|最后操作时间|string(date-time)|string(date-time)|
|multiple|杠杆倍数|number(decimal)|number(decimal)|
|status|状态【计划单状态:待生效=0,已撤单=1,已生效=2,触发失败=3】|PlanOrderStatus|PlanOrderStatus|
|tradeSide|交易类型 0=开多 1=开空  2平=空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】|ContractTradeSide|ContractTradeSide|
|marginMode|保证金模式【全仓保证金模式=0,逐仓保证金模式=1】|MarginMode|MarginMode|
|triggerPrice|触发价格|number(decimal)|number(decimal)|
|trustPrice|委托价格 空为市价\n |number(decimal)|number(decimal)|
|trustQty|委托数量|number(decimal)|number(decimal)|
|realTrustQty|实际委托数量|number(decimal)|number(decimal)|
|triggerPriceKind|触发价格种类【K线价格源类型:市场=0,标记=1,Index=2】|KLineType|KLineType|
|realTrustPrice|实际委托价格|number(decimal)|number(decimal)|
|clientId|客户自定义单号|string||
|orderId|触发生成单号|string||
|symbol|合约符号名称|string||


**响应示例**:
```javascript
[
	{
		"id": "",
		"createTime": "",
		"contractId": "",
		"customerId": "",
		"lastUpdateTime": "",
		"multiple": 0,
		"status": "",
		"tradeSide": "",
		"marginMode": "",
		"triggerPrice": 0,
		"trustPrice": 0,
		"trustQty": 0,
		"realTrustQty": 0,
		"triggerPriceKind": "",
		"realTrustPrice": 0,
		"clientId": "",
		"orderId": "",
		"symbol": ""
	}
]
```


## 批量计划委托单平仓


**接口地址**:`/api/v1/batchClosePlanOrder`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded,application/json`


**响应数据类型**:`*/*`


**接口描述**:


**请求示例**:


```javascript
[
  {
    "symbol": "",
    "clientId": "",
    "trustPrice": 0,
    "triggerPrice": 0,
    "trustQty": 0,
    "side": "",
    "triggerPriceKind": "",
    "unitMode": "",
    "marginMode": ""
  }
]
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|planOrderRequests|planOrderRequest|body|true|array|planOrderRequest|
|&emsp;&emsp;symbol|合约符号名称||true|string||
|&emsp;&emsp;clientId|自定义单号||false|string||
|&emsp;&emsp;trustPrice|委托价格 空为市价\n ||false|number(decimal)||
|&emsp;&emsp;triggerPrice|触发价格||false|number(decimal)||
|&emsp;&emsp;trustQty|委托数量||false|number(decimal)||
|&emsp;&emsp;side|交易类型 0=开多仓 1=开空仓  2=平空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】||false|ContractTradeSide|ContractTradeSide|
|&emsp;&emsp;triggerPriceKind|价格源类型 0=市场 1=标记 2=Index(指数) 【K线价格源类型:市场=0,标记=1,Index=2】||false|KLineType|KLineType|
|&emsp;&emsp;unitMode|交易单位 0=张 1=币【交易单位模式:张=0,币=1】||false|TradingUnitMode|TradingUnitMode|
|&emsp;&emsp;marginMode|持仓模式【全仓保证金模式=0,逐仓保证金模式=1】||false|MarginMode|MarginMode|
|X-RECVWINDOW|recvwindow|header|false|||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||planOrderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|单号|string||
|createTime|委托时间|string(date-time)|string(date-time)|
|contractId|合约Id|string||
|customerId|客户Id|string||
|lastUpdateTime|最后操作时间|string(date-time)|string(date-time)|
|multiple|杠杆倍数|number(decimal)|number(decimal)|
|status|状态【计划单状态:待生效=0,已撤单=1,已生效=2,触发失败=3】|PlanOrderStatus|PlanOrderStatus|
|tradeSide|交易类型 0=开多 1=开空  2平=空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】|ContractTradeSide|ContractTradeSide|
|marginMode|保证金模式【全仓保证金模式=0,逐仓保证金模式=1】|MarginMode|MarginMode|
|triggerPrice|触发价格|number(decimal)|number(decimal)|
|trustPrice|委托价格 空为市价\n |number(decimal)|number(decimal)|
|trustQty|委托数量|number(decimal)|number(decimal)|
|realTrustQty|实际委托数量|number(decimal)|number(decimal)|
|triggerPriceKind|触发价格种类【K线价格源类型:市场=0,标记=1,Index=2】|KLineType|KLineType|
|realTrustPrice|实际委托价格|number(decimal)|number(decimal)|
|clientId|客户自定义单号|string||
|orderId|触发生成单号|string||
|symbol|合约符号名称|string||


**响应示例**:
```javascript
[
	{
		"id": "",
		"createTime": "",
		"contractId": "",
		"customerId": "",
		"lastUpdateTime": "",
		"multiple": 0,
		"status": "",
		"tradeSide": "",
		"marginMode": "",
		"triggerPrice": 0,
		"trustPrice": 0,
		"trustQty": 0,
		"realTrustQty": 0,
		"triggerPriceKind": "",
		"realTrustPrice": 0,
		"clientId": "",
		"orderId": "",
		"symbol": ""
	}
]
```

## 限价市价委托开仓


**接口地址**:`/api/v1/openOrder`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|合约符号名称|query|false|string||
|Side|多空方向:多=0,空=1|query|false|contractSide|contractSide|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|Price|价格|query|false|number(decimal)||
|Type|交易类型:市场价=5,限价=6|query|false|orderType|orderType|
|&emsp;&emsp;undefined|可用值:2,3,4,5,6,7,8,9||false|integer||
|Size|数量|query|false|number(decimal)||
|ClientId|客户自定义单号|query|false|string||
|UnitMode|交易单位模式:张=0,币=1|query|false|tradingUnitMode|tradingUnitMode|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|marginMode|全仓保证金模式=0,逐仓保证金模式=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||orderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|单号|string||
|createTime|委托时间|string(date-time)|string(date-time)|
|contractId||string||
|customerId|客户Id|string||
|orderType|交易类型【交易类型:市场价=5,限价=6】|OrderType|OrderType|
|price|委托价|number(decimal)|number(decimal)|
|totalQty|委托总量|number(decimal)|number(decimal)|
|cumQty|已成交数量|number(decimal)|number(decimal)|
|avgExecutionPrice|成交均价|number(decimal)|number(decimal)|
|status|状态【单状态:挂单=0,部分成交=1,全部成交=2,已撤消=3,无效单=99】|OrderStatus|OrderStatus|
|side|交易类型 0=开多 1=开空  2平=空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】|ContractTradeSide|ContractTradeSide|
|clientId|客户自定义单号|string||
|lastUpdateTime|最后操作时间|string(date-time)|string(date-time)|
|multiple|杠杆倍数|number(decimal)|number(decimal)|
|uFee|手续费|number(decimal)|number(decimal)|
|pnl|收益|number(decimal)|number(decimal)|
|marginMode|保证金模式【全仓保证金模式=0,逐仓保证金模式=1】|MarginMode|MarginMode|
|symbol|合约符号名称|string||
|pnlRate|收益率|number(decimal)|number(decimal)|


**响应示例**:
```javascript
{
	"id": "",
	"createTime": "",
	"contractId": "",
	"customerId": "",
	"orderType": "",
	"price": 0,
	"totalQty": 0,
	"cumQty": 0,
	"avgExecutionPrice": 0,
	"status": "",
	"side": "",
	"clientId": "",
	"lastUpdateTime": "",
	"multiple": 0,
	"uFee": 0,
	"pnl": 0,
	"marginMode": "",
	"symbol": "",
	"pnlRate": 0
}
```


## 限价市价委托平仓


**接口地址**:`/api/v1/closeOrder`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|合约符号名称|query|false|string||
|Side|多空方向:多=0,空=1|query|false|contractSide|contractSide|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|Size|数量|query|false|number(decimal)||
|Price|价格|query|false|number(decimal)||
|Type|交易类型:市场价=5,限价=6|query|false|orderType|orderType|
|&emsp;&emsp;undefined|可用值:2,3,4,5,6,7,8,9||false|integer||
|ClientId|客户自定义单号 |query|false|string||
|UnitMode|交易单位模式:张=0,币=1|query|false|tradingUnitMode|tradingUnitMode|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|marginMode|全仓保证金模式=0,逐仓保证金模式=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||orderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|单号|string||
|createTime|委托时间|string(date-time)|string(date-time)|
|contractId||string||
|customerId|客户Id|string||
|orderType|交易类型【交易类型:市场价=5,限价=6】|OrderType|OrderType|
|price|委托价|number(decimal)|number(decimal)|
|totalQty|委托总量|number(decimal)|number(decimal)|
|cumQty|已成交数量|number(decimal)|number(decimal)|
|avgExecutionPrice|成交均价|number(decimal)|number(decimal)|
|status|状态【单状态:挂单=0,部分成交=1,全部成交=2,已撤消=3,无效单=99】|OrderStatus|OrderStatus|
|side|交易类型 0=开多 1=开空  2平=空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】|ContractTradeSide|ContractTradeSide|
|clientId|客户自定义单号|string||
|lastUpdateTime|最后操作时间|string(date-time)|string(date-time)|
|multiple|杠杆倍数|number(decimal)|number(decimal)|
|uFee|手续费|number(decimal)|number(decimal)|
|pnl|收益|number(decimal)|number(decimal)|
|marginMode|保证金模式【全仓保证金模式=0,逐仓保证金模式=1】|MarginMode|MarginMode|
|symbol|合约符号名称|string||
|pnlRate|收益率|number(decimal)|number(decimal)|


**响应示例**:
```javascript
{
	"id": "",
	"createTime": "",
	"contractId": "",
	"customerId": "",
	"orderType": "",
	"price": 0,
	"totalQty": 0,
	"cumQty": 0,
	"avgExecutionPrice": 0,
	"status": "",
	"side": "",
	"clientId": "",
	"lastUpdateTime": "",
	"multiple": 0,
	"uFee": 0,
	"pnl": 0,
	"marginMode": "",
	"symbol": "",
	"pnlRate": 0
}
```


## 撤销限价市价委托订单


**接口地址**:`/api/v1/cancelOrder`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|symbol||query|false|string||
|orderId||query|false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|||


**响应参数**:


暂无


**响应示例**:
```javascript

```


## 撤销全部限价市价委托订单


**接口地址**:`/api/v1/cancelAllOpenOrders`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|symbol||query|false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|||


**响应参数**:


暂无


**响应示例**:
```javascript

```


## 获取当前委托的限价市价单


**接口地址**:`/api/v1/getActiveOrders`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|合约符号名称|query|false|string||
|Side|开多仓=0,开空仓=1,平空仓=2,平多仓=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|可用值:0,1,2,3||false|integer||
|PageIndex|当前页码|query|false|integer(int32)||
|PageSize|每页行数|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||pageResultOfOrderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|success|是否成功|boolean||
|errorCode|错误代码|integer(int32)|integer(int32)|
|msg|返回消息|string||
|total|总记录数|integer(int32)|integer(int32)|
|data|订单列表|OrderDTO|OrderDTO|


**响应示例**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## 获取历史委托的限价市价单


**接口地址**:`/api/v1/getHistoryOrders`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|合约符号名称|query|false|string||
|Side|开多仓=0,开空仓=1,平空仓=2,平多仓=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|可用值:0,1,2,3||false|integer||
|PageIndex|当前页码|query|false|integer(int32)||
|PageSize|每页行数|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||pageResultOfOrderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|success|是否成功|boolean||
|errorCode|错误代码|integer(int32)|integer(int32)|
|msg|返回消息|string||
|total|总记录数|integer(int32)|integer(int32)|
|data|订单列表|OrderDTO|OrderDTO|


**响应示例**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## 获取限价市价委托单详细


**接口地址**:`/api/v1/getOrderDetail`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|orderId||query|false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||orderDetailDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|单号|string||
|createTime|委托时间|string(date-time)|string(date-time)|
|contractId||string||
|customerId|客户Id|string||
|orderType|交易类型【交易类型:市场价=5,限价=6】|OrderType|OrderType|
|price|委托价|number(decimal)|number(decimal)|
|totalQty|委托总量|number(decimal)|number(decimal)|
|cumQty|已成交数量|number(decimal)|number(decimal)|
|avgExecutionPrice|成交均价|number(decimal)|number(decimal)|
|status|状态【单状态:挂单=0,部分成交=1,全部成交=2,已撤消=3,无效单=99】|OrderStatus|OrderStatus|
|side|交易类型 0=开多 1=开空  2平=空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】|ContractTradeSide|ContractTradeSide|
|clientId|客户自定义单号|string||
|lastUpdateTime|最后操作时间|string(date-time)|string(date-time)|
|multiple|杠杆倍数|number(decimal)|number(decimal)|
|uFee|手续费|number(decimal)|number(decimal)|
|pnl|收益|number(decimal)|number(decimal)|
|marginMode|保证金模式【全仓保证金模式=0,逐仓保证金模式=1】|MarginMode|MarginMode|
|symbol|合约符号名称|string||
|pnlRate|收益率|number(decimal)|number(decimal)|
|orderFilleds|成交单明细|OrderFilledDTO|OrderFilledDTO|


**响应示例**:
```javascript
{
	"id": "",
	"createTime": "",
	"contractId": "",
	"customerId": "",
	"orderType": "",
	"price": 0,
	"totalQty": 0,
	"cumQty": 0,
	"avgExecutionPrice": 0,
	"status": "",
	"side": "",
	"clientId": "",
	"lastUpdateTime": "",
	"multiple": 0,
	"uFee": 0,
	"pnl": 0,
	"marginMode": "",
	"symbol": "",
	"pnlRate": 0,
	"orderFilleds": ""
}
```


## 止盈止损委托开仓


**接口地址**:`/api/v1/openKillOrFillOrder`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|合约符号名称|query|false|string||
|Side|止盈止损委托单方向:单向止盈止损=0,双向止盈止损=1|query|false|fillOrKillOrderSide|fillOrKillOrderSide|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|FillTriggerPrice|止盈触发价格|query|false|number(decimal)||
|FillTrustPrice|止盈委托价格|query|false|number(decimal)||
|KillTriggerPrice|止损触发价格|query|false|number(decimal)||
|KillTrustPrice|止损委托价格|query|false|number(decimal)||
|TradeSide|开多仓=0,开空仓=1,平空仓=2,平多仓=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|可用值:0,1,2,3||false|integer||
|TrustQty|数量|query|false|number(decimal)||
|TriggerPriceKind|K线价格源类型:市场=0,标记=1,Index=2|query|false|kLineType|kLineType|
|&emsp;&emsp;undefined|可用值:0,1,2||false|integer||
|UnitMode|交易单位模式:张=0,币=1|query|false|tradingUnitMode|tradingUnitMode|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|marginMode|全仓保证金模式=0,逐仓保证金模式=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||fillOrKillOrderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|单号|string||
|createTime|委托时间|string(date-time)|string(date-time)|
|contractId|合约Id|string||
|customerId|客户Id|string||
|multiple|杠杆倍数|number(decimal)|number(decimal)|
|status|状态【止盈止损委托单状态:待生效=0,已撤单=1,已生效=2,触发失败=3】|FillOrKillOrderStatus|FillOrKillOrderStatus|
|side|方向【止盈止损委托单方向:单向止盈止损=0,双向止盈止损=1】|FillOrKillOrderSide|FillOrKillOrderSide|
|tradeSide|交易类型 0=开多 1=开空  2平=空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】|ContractTradeSide|ContractTradeSide|
|marginMode|保证金模式【全仓保证金模式=0,逐仓保证金模式=1】|MarginMode|MarginMode|
|fillTriggerPrice|止盈触发价格|number(decimal)|number(decimal)|
|fillTrustPrice|止盈委托价格 空为市价|number(decimal)|number(decimal)|
|killTriggerPrice|止损触发价格|number(decimal)|number(decimal)|
|killTrustPrice|止损委托价格 空为市价|number(decimal)|number(decimal)|
|trustQty|委托数量|number(decimal)|number(decimal)|
|realTrustQty|实际委托数量|number(decimal)|number(decimal)|
|cumQty|已委托量 |number(decimal)|number(decimal)|
|triggerDirection|触发方向【触发方向:止赢=0,止损=1】|FillOrKillTriggerDirection|FillOrKillTriggerDirection|
|triggerPriceKind|触发价格种类【K线价格源类型:市场=0,标记=1,Index=2】|KLineType|KLineType|
|realTrustPrice|实际委托价格|number(decimal)|number(decimal)|
|lastUpdateTime|最后操作时间|string(date-time)|string(date-time)|
|clientId|客户自定义单号|string||
|orderId|触发生成单号|string||
|symbol|合约符号名称|string||


**响应示例**:
```javascript
{
	"id": "",
	"createTime": "",
	"contractId": "",
	"customerId": "",
	"multiple": 0,
	"status": "",
	"side": "",
	"tradeSide": "",
	"marginMode": "",
	"fillTriggerPrice": 0,
	"fillTrustPrice": 0,
	"killTriggerPrice": 0,
	"killTrustPrice": 0,
	"trustQty": 0,
	"realTrustQty": 0,
	"cumQty": 0,
	"triggerDirection": "",
	"triggerPriceKind": "",
	"realTrustPrice": 0,
	"lastUpdateTime": "",
	"clientId": "",
	"orderId": "",
	"symbol": ""
}
```


## 止盈止损委托平仓


**接口地址**:`/api/v1/closeKillOrFillOrder`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|合约符号名称|query|false|string||
|Side|止盈止损委托单方向:单向止盈止损=0,双向止盈止损=1|query|false|fillOrKillOrderSide|fillOrKillOrderSide|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|FillTriggerPrice|止盈触发价格|query|false|number(decimal)||
|FillTrustPrice|止盈委托价格|query|false|number(decimal)||
|KillTriggerPrice|止损触发价格|query|false|number(decimal)||
|KillTrustPrice|止损委托价格|query|false|number(decimal)||
|TradeSide|开多仓=0,开空仓=1,平空仓=2,平多仓=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|可用值:0,1,2,3||false|integer||
|TrustQty|数量|query|false|number(decimal)||
|TriggerPriceKind|K线价格源类型:市场=0,标记=1,Index=2|query|false|kLineType|kLineType|
|&emsp;&emsp;undefined|可用值:0,1,2||false|integer||
|UnitMode|交易单位模式:张=0,币=1|query|false|tradingUnitMode|tradingUnitMode|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|marginMode|全仓保证金模式=0,逐仓保证金模式=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||fillOrKillOrderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|单号|string||
|createTime|委托时间|string(date-time)|string(date-time)|
|contractId|合约Id|string||
|customerId|客户Id|string||
|multiple|杠杆倍数|number(decimal)|number(decimal)|
|status|状态【止盈止损委托单状态:待生效=0,已撤单=1,已生效=2,触发失败=3】|FillOrKillOrderStatus|FillOrKillOrderStatus|
|side|方向【止盈止损委托单方向:单向止盈止损=0,双向止盈止损=1】|FillOrKillOrderSide|FillOrKillOrderSide|
|tradeSide|交易类型 0=开多 1=开空  2平=空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】|ContractTradeSide|ContractTradeSide|
|marginMode|保证金模式【全仓保证金模式=0,逐仓保证金模式=1】|MarginMode|MarginMode|
|fillTriggerPrice|止盈触发价格|number(decimal)|number(decimal)|
|fillTrustPrice|止盈委托价格 空为市价|number(decimal)|number(decimal)|
|killTriggerPrice|止损触发价格|number(decimal)|number(decimal)|
|killTrustPrice|止损委托价格 空为市价|number(decimal)|number(decimal)|
|trustQty|委托数量|number(decimal)|number(decimal)|
|realTrustQty|实际委托数量|number(decimal)|number(decimal)|
|cumQty|已委托量 |number(decimal)|number(decimal)|
|triggerDirection|触发方向【触发方向:止赢=0,止损=1】|FillOrKillTriggerDirection|FillOrKillTriggerDirection|
|triggerPriceKind|触发价格种类【K线价格源类型:市场=0,标记=1,Index=2】|KLineType|KLineType|
|realTrustPrice|实际委托价格|number(decimal)|number(decimal)|
|lastUpdateTime|最后操作时间|string(date-time)|string(date-time)|
|clientId|客户自定义单号|string||
|orderId|触发生成单号|string||
|symbol|合约符号名称|string||


**响应示例**:
```javascript
{
	"id": "",
	"createTime": "",
	"contractId": "",
	"customerId": "",
	"multiple": 0,
	"status": "",
	"side": "",
	"tradeSide": "",
	"marginMode": "",
	"fillTriggerPrice": 0,
	"fillTrustPrice": 0,
	"killTriggerPrice": 0,
	"killTrustPrice": 0,
	"trustQty": 0,
	"realTrustQty": 0,
	"cumQty": 0,
	"triggerDirection": "",
	"triggerPriceKind": "",
	"realTrustPrice": 0,
	"lastUpdateTime": "",
	"clientId": "",
	"orderId": "",
	"symbol": ""
}
```


## 止盈止损委托订单撤销


**接口地址**:`/api/v1/cancelKillOrFillOrder`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|合约符号名称|query|false|string||
|OrderId|订单id|query|false|string||
|ClientOrderId|客户订单id|query|false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|||


**响应参数**:


暂无


**响应示例**:
```javascript

```


## 获取当前委托的止盈止损单


**接口地址**:`/api/v1/getActiveKillOrFillOrders`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|合约符号名称|query|false|string||
|Side|开多仓=0,开空仓=1,平空仓=2,平多仓=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|可用值:0,1,2,3||false|integer||
|PageIndex|当前页码|query|false|integer(int32)||
|PageSize|每页行数|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||pageResultOfFillOrKillOrderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|success|是否成功|boolean||
|errorCode|错误代码|integer(int32)|integer(int32)|
|msg|返回消息|string||
|total|总记录数|integer(int32)|integer(int32)|
|data|止盈止损单列表|FillOrKillOrderDTO|FillOrKillOrderDTO|


**响应示例**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## 获取历史委托的止盈止损单


**接口地址**:`/api/v1/getHistoryKillOrFillOrders`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|合约符号名称|query|false|string||
|Side|开多仓=0,开空仓=1,平空仓=2,平多仓=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|可用值:0,1,2,3||false|integer||
|PageIndex|当前页码|query|false|integer(int32)||
|PageSize|每页行数|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||pageResultOfFillOrKillOrderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|success|是否成功|boolean||
|errorCode|错误代码|integer(int32)|integer(int32)|
|msg|返回消息|string||
|total|总记录数|integer(int32)|integer(int32)|
|data|止盈止损单列表|FillOrKillOrderDTO|FillOrKillOrderDTO|


**响应示例**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## 获取止盈止损单


**接口地址**:`/api/v1/getKillOrFillOrder`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|orderId||query|false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||fillOrKillOrderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|单号|string||
|createTime|委托时间|string(date-time)|string(date-time)|
|contractId|合约Id|string||
|customerId|客户Id|string||
|multiple|杠杆倍数|number(decimal)|number(decimal)|
|status|状态【止盈止损委托单状态:待生效=0,已撤单=1,已生效=2,触发失败=3】|FillOrKillOrderStatus|FillOrKillOrderStatus|
|side|方向【止盈止损委托单方向:单向止盈止损=0,双向止盈止损=1】|FillOrKillOrderSide|FillOrKillOrderSide|
|tradeSide|交易类型 0=开多 1=开空  2平=空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】|ContractTradeSide|ContractTradeSide|
|marginMode|保证金模式【全仓保证金模式=0,逐仓保证金模式=1】|MarginMode|MarginMode|
|fillTriggerPrice|止盈触发价格|number(decimal)|number(decimal)|
|fillTrustPrice|止盈委托价格 空为市价|number(decimal)|number(decimal)|
|killTriggerPrice|止损触发价格|number(decimal)|number(decimal)|
|killTrustPrice|止损委托价格 空为市价|number(decimal)|number(decimal)|
|trustQty|委托数量|number(decimal)|number(decimal)|
|realTrustQty|实际委托数量|number(decimal)|number(decimal)|
|cumQty|已委托量 |number(decimal)|number(decimal)|
|triggerDirection|触发方向【触发方向:止赢=0,止损=1】|FillOrKillTriggerDirection|FillOrKillTriggerDirection|
|triggerPriceKind|触发价格种类【K线价格源类型:市场=0,标记=1,Index=2】|KLineType|KLineType|
|realTrustPrice|实际委托价格|number(decimal)|number(decimal)|
|lastUpdateTime|最后操作时间|string(date-time)|string(date-time)|
|clientId|客户自定义单号|string||
|orderId|触发生成单号|string||
|symbol|合约符号名称|string||


**响应示例**:
```javascript
{
	"id": "",
	"createTime": "",
	"contractId": "",
	"customerId": "",
	"multiple": 0,
	"status": "",
	"side": "",
	"tradeSide": "",
	"marginMode": "",
	"fillTriggerPrice": 0,
	"fillTrustPrice": 0,
	"killTriggerPrice": 0,
	"killTrustPrice": 0,
	"trustQty": 0,
	"realTrustQty": 0,
	"cumQty": 0,
	"triggerDirection": "",
	"triggerPriceKind": "",
	"realTrustPrice": 0,
	"lastUpdateTime": "",
	"clientId": "",
	"orderId": "",
	"symbol": ""
}
```


## 计划委托单开仓


**接口地址**:`/api/v1/openPlanOrder`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|合约符号名称|query|false|string||
|ClientId|自定义单号|query|false|string||
|TrustPrice|委托价格 空为市价\n |query|false|number(decimal)||
|TriggerPrice|触发价格|query|false|number(decimal)||
|TrustQty|委托数量|query|false|number(decimal)||
|Side|开多仓=0,开空仓=1,平空仓=2,平多仓=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|可用值:0,1,2,3||false|integer||
|TriggerPriceKind|K线价格源类型:市场=0,标记=1,Index=2|query|false|kLineType|kLineType|
|&emsp;&emsp;undefined|可用值:0,1,2||false|integer||
|UnitMode|交易单位模式:张=0,币=1|query|false|tradingUnitMode|tradingUnitMode|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|marginMode|全仓保证金模式=0,逐仓保证金模式=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||planOrderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|单号|string||
|createTime|委托时间|string(date-time)|string(date-time)|
|contractId|合约Id|string||
|customerId|客户Id|string||
|lastUpdateTime|最后操作时间|string(date-time)|string(date-time)|
|multiple|杠杆倍数|number(decimal)|number(decimal)|
|status|状态【计划单状态:待生效=0,已撤单=1,已生效=2,触发失败=3】|PlanOrderStatus|PlanOrderStatus|
|tradeSide|交易类型 0=开多 1=开空  2平=空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】|ContractTradeSide|ContractTradeSide|
|marginMode|保证金模式【全仓保证金模式=0,逐仓保证金模式=1】|MarginMode|MarginMode|
|triggerPrice|触发价格|number(decimal)|number(decimal)|
|trustPrice|委托价格 空为市价\n |number(decimal)|number(decimal)|
|trustQty|委托数量|number(decimal)|number(decimal)|
|realTrustQty|实际委托数量|number(decimal)|number(decimal)|
|triggerPriceKind|触发价格种类【K线价格源类型:市场=0,标记=1,Index=2】|KLineType|KLineType|
|realTrustPrice|实际委托价格|number(decimal)|number(decimal)|
|clientId|客户自定义单号|string||
|orderId|触发生成单号|string||
|symbol|合约符号名称|string||


**响应示例**:
```javascript
{
	"id": "",
	"createTime": "",
	"contractId": "",
	"customerId": "",
	"lastUpdateTime": "",
	"multiple": 0,
	"status": "",
	"tradeSide": "",
	"marginMode": "",
	"triggerPrice": 0,
	"trustPrice": 0,
	"trustQty": 0,
	"realTrustQty": 0,
	"triggerPriceKind": "",
	"realTrustPrice": 0,
	"clientId": "",
	"orderId": "",
	"symbol": ""
}
```


## 计划委托单平仓


**接口地址**:`/api/v1/closePlanOrder`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|合约符号名称|query|false|string||
|ClientId|自定义单号|query|false|string||
|TrustPrice|委托价格 空为市价\n |query|false|number(decimal)||
|TriggerPrice|触发价格|query|false|number(decimal)||
|TrustQty|委托数量|query|false|number(decimal)||
|Side|开多仓=0,开空仓=1,平空仓=2,平多仓=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|可用值:0,1,2,3||false|integer||
|TriggerPriceKind|K线价格源类型:市场=0,标记=1,Index=2|query|false|kLineType|kLineType|
|&emsp;&emsp;undefined|可用值:0,1,2||false|integer||
|UnitMode|交易单位模式:张=0,币=1|query|false|tradingUnitMode|tradingUnitMode|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|marginMode|全仓保证金模式=0,逐仓保证金模式=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||planOrderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|单号|string||
|createTime|委托时间|string(date-time)|string(date-time)|
|contractId|合约Id|string||
|customerId|客户Id|string||
|lastUpdateTime|最后操作时间|string(date-time)|string(date-time)|
|multiple|杠杆倍数|number(decimal)|number(decimal)|
|status|状态【计划单状态:待生效=0,已撤单=1,已生效=2,触发失败=3】|PlanOrderStatus|PlanOrderStatus|
|tradeSide|交易类型 0=开多 1=开空  2平=空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】|ContractTradeSide|ContractTradeSide|
|marginMode|保证金模式【全仓保证金模式=0,逐仓保证金模式=1】|MarginMode|MarginMode|
|triggerPrice|触发价格|number(decimal)|number(decimal)|
|trustPrice|委托价格 空为市价\n |number(decimal)|number(decimal)|
|trustQty|委托数量|number(decimal)|number(decimal)|
|realTrustQty|实际委托数量|number(decimal)|number(decimal)|
|triggerPriceKind|触发价格种类【K线价格源类型:市场=0,标记=1,Index=2】|KLineType|KLineType|
|realTrustPrice|实际委托价格|number(decimal)|number(decimal)|
|clientId|客户自定义单号|string||
|orderId|触发生成单号|string||
|symbol|合约符号名称|string||


**响应示例**:
```javascript
{
	"id": "",
	"createTime": "",
	"contractId": "",
	"customerId": "",
	"lastUpdateTime": "",
	"multiple": 0,
	"status": "",
	"tradeSide": "",
	"marginMode": "",
	"triggerPrice": 0,
	"trustPrice": 0,
	"trustQty": 0,
	"realTrustQty": 0,
	"triggerPriceKind": "",
	"realTrustPrice": 0,
	"clientId": "",
	"orderId": "",
	"symbol": ""
}
```


## 计划委托订单撤销


**接口地址**:`/api/v1/cancelPlanOrder`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|合约符号名称|query|false|string||
|OrderId|订单id|query|false|string||
|ClientOrderId|客户订单id|query|false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|||


**响应参数**:


暂无


**响应示例**:
```javascript

```


## 获取当前委托的计划委托单


**接口地址**:`/api/v1/getPlanOrders`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|合约符号名称|query|false|string||
|Side|开多仓=0,开空仓=1,平空仓=2,平多仓=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|可用值:0,1,2,3||false|integer||
|PageIndex|当前页码|query|false|integer(int32)||
|PageSize|每页行数|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||pageResultOfPlanOrderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|success|是否成功|boolean||
|errorCode|错误代码|integer(int32)|integer(int32)|
|msg|返回消息|string||
|total|总记录数|integer(int32)|integer(int32)|
|data|计划单列表|PlanOrderDTO|PlanOrderDTO|


**响应示例**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## 获取历史委托的计划委托单


**接口地址**:`/api/v1/getHistoryPlanOrders`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|合约符号名称|query|false|string||
|Side|开多仓=0,开空仓=1,平空仓=2,平多仓=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|可用值:0,1,2,3||false|integer||
|PageIndex|当前页码|query|false|integer(int32)||
|PageSize|每页行数|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||pageResultOfPlanOrderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|success|是否成功|boolean||
|errorCode|错误代码|integer(int32)|integer(int32)|
|msg|返回消息|string||
|total|总记录数|integer(int32)|integer(int32)|
|data|计划单列表|PlanOrderDTO|PlanOrderDTO|


**响应示例**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## 获取计划委托单


**接口地址**:`/api/v1/getPlanOrder`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|orderId||query|false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||planOrderDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|单号|string||
|createTime|委托时间|string(date-time)|string(date-time)|
|contractId|合约Id|string||
|customerId|客户Id|string||
|lastUpdateTime|最后操作时间|string(date-time)|string(date-time)|
|multiple|杠杆倍数|number(decimal)|number(decimal)|
|status|状态【计划单状态:待生效=0,已撤单=1,已生效=2,触发失败=3】|PlanOrderStatus|PlanOrderStatus|
|tradeSide|交易类型 0=开多 1=开空  2平=空   3=平多【开多仓=0,开空仓=1,平空仓=2,平多仓=3】|ContractTradeSide|ContractTradeSide|
|marginMode|保证金模式【全仓保证金模式=0,逐仓保证金模式=1】|MarginMode|MarginMode|
|triggerPrice|触发价格|number(decimal)|number(decimal)|
|trustPrice|委托价格 空为市价\n |number(decimal)|number(decimal)|
|trustQty|委托数量|number(decimal)|number(decimal)|
|realTrustQty|实际委托数量|number(decimal)|number(decimal)|
|triggerPriceKind|触发价格种类【K线价格源类型:市场=0,标记=1,Index=2】|KLineType|KLineType|
|realTrustPrice|实际委托价格|number(decimal)|number(decimal)|
|clientId|客户自定义单号|string||
|orderId|触发生成单号|string||
|symbol|合约符号名称|string||


**响应示例**:
```javascript
{
	"id": "",
	"createTime": "",
	"contractId": "",
	"customerId": "",
	"lastUpdateTime": "",
	"multiple": 0,
	"status": "",
	"tradeSide": "",
	"marginMode": "",
	"triggerPrice": 0,
	"trustPrice": 0,
	"trustQty": 0,
	"realTrustQty": 0,
	"triggerPriceKind": "",
	"realTrustPrice": 0,
	"clientId": "",
	"orderId": "",
	"symbol": ""
}
```


## 获取K线数据


**接口地址**:`/api/v1/candles`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|Symbol|合约品种符号|query|false|string||
|Interval|每分钟=100,5分钟=101,15分钟=102,30分钟=103,每小时=200,2小时=201,4小时=202,8小时=203,每天=300,每周=400,每月=500|query|false|candleInterval|candleInterval|
|&emsp;&emsp;undefined|可用值:100,101,102,103,200,201,202,203,300,400,500||false|integer||
|StartTime|开始时间|query|false|integer(int64)||
|kLineType|K线价格源类型:市场=0,标记=1,Index=2|query|false|kLineType|kLineType|
|&emsp;&emsp;undefined|可用值:0,1,2||false|integer||
|EndTime|结束时间|query|false|integer(int64)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||candleDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|kLineType|K线类型【K线价格源类型:市场=0,标记=1,Index=2】|KLineType|KLineType|
|interval|蜡烛间隔【每分钟=100,5分钟=101,15分钟=102,30分钟=103,每小时=200,2小时=201,4小时=202,8小时=203,每天=300,每周=400,每月=500】|CandleInterval|CandleInterval|
|close|收盘价|number(decimal)|number(decimal)|
|high|最高价|number(decimal)|number(decimal)|
|low|最低价|number(decimal)|number(decimal)|
|open|开盘价|number(decimal)|number(decimal)|
|volume|张数|number(decimal)|number(decimal)|
|timestamp|时间戳|integer(int64)|integer(int64)|
|dateTime|瞬时时间|string(date-time)|string(date-time)|


**响应示例**:
```javascript
[
	{
		"kLineType": "",
		"interval": "",
		"close": 0,
		"high": 0,
		"low": 0,
		"open": 0,
		"volume": 0,
		"timestamp": 0,
		"dateTime": ""
	}
]
```


## 根据合约Id获取合约品种最新行情


**接口地址**:`/api/v1/realTimeHandicap`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|contractId|合约Id|query|false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||realTimeHandicapFullDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|contractId|合约品种Id|string||
|symbol|合约标识|string||
|createTime||string(date-time)|string(date-time)|
|timestamp||integer(int64)|integer(int64)|
|firstBid|第一买价|number(decimal)|number(decimal)|
|firstAsk|第一卖价|number(decimal)|number(decimal)|
|marketPrice|最新市场价|number(decimal)|number(decimal)|
|triggerType|内外盘【成交触发类型:内盘=1,外盘=2】|TriggerType|TriggerType|
|sort|序号|integer(int64)|integer(int64)|
|changeAmount24H|24小时涨跌额|number(decimal)|number(decimal)|
|changeRate24H|24小时涨跌幅|number(decimal)|number(decimal)|
|high24H|24小时最高价|number(decimal)|number(decimal)|
|low24H|24小时最低价|number(decimal)|number(decimal)|
|volume24H|24小时成交量|number(decimal)|number(decimal)|
|turnover24H|24小时成交额|number(decimal)|number(decimal)|
|markPrice|最新标记价|number(decimal)|number(decimal)|
|indexPrice|最新指数价|number(decimal)|number(decimal)|
|distanceSettlementTime|距费用结算时间|string(time-span)|string(time-span)|
|currentFundRate|当期资金费率|number(decimal)|number(decimal)|
|forecastFundRate|预测资金费率|number(decimal)|number(decimal)|


**响应示例**:
```javascript
{
	"contractId": "",
	"symbol": "",
	"createTime": "",
	"timestamp": 0,
	"firstBid": 0,
	"firstAsk": 0,
	"marketPrice": 0,
	"triggerType": "",
	"sort": 0,
	"changeAmount24H": 0,
	"changeRate24H": 0,
	"high24H": 0,
	"low24H": 0,
	"volume24H": 0,
	"turnover24H": 0,
	"markPrice": 0,
	"indexPrice": 0,
	"distanceSettlementTime": "",
	"currentFundRate": 0,
	"forecastFundRate": 0
}
```


## 获取合约品种最新行情


**接口地址**:`/api/v1/realTimeHandicapFull`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||realTimeHandicapFullDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|contractId|合约品种Id|string||
|symbol|合约标识|string||
|createTime||string(date-time)|string(date-time)|
|timestamp||integer(int64)|integer(int64)|
|firstBid|第一买价|number(decimal)|number(decimal)|
|firstAsk|第一卖价|number(decimal)|number(decimal)|
|marketPrice|最新市场价|number(decimal)|number(decimal)|
|triggerType|内外盘【成交触发类型:内盘=1,外盘=2】|TriggerType|TriggerType|
|sort|序号|integer(int64)|integer(int64)|
|changeAmount24H|24小时涨跌额|number(decimal)|number(decimal)|
|changeRate24H|24小时涨跌幅|number(decimal)|number(decimal)|
|high24H|24小时最高价|number(decimal)|number(decimal)|
|low24H|24小时最低价|number(decimal)|number(decimal)|
|volume24H|24小时成交量|number(decimal)|number(decimal)|
|turnover24H|24小时成交额|number(decimal)|number(decimal)|
|markPrice|最新标记价|number(decimal)|number(decimal)|
|indexPrice|最新指数价|number(decimal)|number(decimal)|
|distanceSettlementTime|距费用结算时间|string(time-span)|string(time-span)|
|currentFundRate|当期资金费率|number(decimal)|number(decimal)|
|forecastFundRate|预测资金费率|number(decimal)|number(decimal)|


**响应示例**:
```javascript
[
	{
		"contractId": "",
		"symbol": "",
		"createTime": "",
		"timestamp": 0,
		"firstBid": 0,
		"firstAsk": 0,
		"marketPrice": 0,
		"triggerType": "",
		"sort": 0,
		"changeAmount24H": 0,
		"changeRate24H": 0,
		"high24H": 0,
		"low24H": 0,
		"volume24H": 0,
		"turnover24H": 0,
		"markPrice": 0,
		"indexPrice": 0,
		"distanceSettlementTime": "",
		"currentFundRate": 0,
		"forecastFundRate": 0
	}
]
```


## 获取盘口深度


**接口地址**:`/api/v1/depth`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|contractId|合约品种Id|query|false|string||
|tickSize|精度|query|false|number(decimal)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||orderBookDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|contractId|合约id|string||
|bids|买入盘  价格 数量|array|array|
|asks|卖出盘 价格 数量|array|array|


**响应示例**:
```javascript
{
	"contractId": "",
	"bids": [],
	"asks": []
}
```


## 获取最新交易


**接口地址**:`/api/v1/recentTrades`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|contractId|合约品种Id|query|false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||ticketDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|price|价格|number(decimal)|number(decimal)|
|qty|数量|number(decimal)|number(decimal)|
|triggerType|内外盘【成交触发类型:内盘=1,外盘=2】|TriggerType|TriggerType|
|timeStamp|时间|integer(int64)|integer(int64)|


**响应示例**:
```javascript
[
	{
		"price": 0,
		"qty": 0,
		"triggerType": "",
		"timeStamp": 0
	}
]
```


## 实时资金费率


**接口地址**:`/api/v1/getRealFundingRateList`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||fundingRateReal|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|contractId|Contractid|string||
|predictionRate|预测资金费率|number(decimal)|number(decimal)|
|rate|本期资金费率|number(decimal)|number(decimal)|
|contractName|合约名称|string||
|createTimeOffset|创建时间戳|integer(int64)|integer(int64)|


**响应示例**:
```javascript
[
	{
		"contractId": "",
		"predictionRate": 0,
		"rate": 0,
		"contractName": "",
		"createTimeOffset": 0
	}
]
```


## 历史资金费率


**接口地址**:`/api/v1/getHistoryFundingRateList`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|ContractId|币种名称|query|false|string||
|PageIndex|当前页码|query|false|integer(int32)||
|PageRows|每页行数|query|false|integer(int32)||
|SortField|排序列|query|false|string||
|SortType|排序类型|query|false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||pageResultOfFundingRateView|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|success|是否成功|boolean||
|errorCode|错误代码|integer(int32)|integer(int32)|
|msg|返回消息|string||
|total|总记录数|integer(int32)|integer(int32)|
|data|资金费率列表|FundingRateView|FundingRateView|


**响应示例**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## 获取平台状态


**接口地址**:`/api/v1/getPlatformStatus`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||platformStatus|


**响应参数**:


暂无


**响应示例**:
```javascript
null
```


## 获取仓位档位列表


**接口地址**:`/api/v1/getPositionGearList`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|ContractId|合约Id|query|false|string||
|PageIndex|当前页码|query|false|integer(int32)||
|PageRows|每页行数|query|false|integer(int32)||
|SortField|排序列|query|false|string||
|SortType|排序类型|query|false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||pageResultOfPositionGear|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|success|是否成功|boolean||
|errorCode|错误代码|integer(int32)|integer(int32)|
|msg|返回消息|string||
|total|总记录数|integer(int32)|integer(int32)|
|data|持仓挡位列表|PositionGear|PositionGear|


**响应示例**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## 获取挡位详情


**接口地址**:`/api/v1/getPositionGearDetail`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|symbol|合约对|query|false|string||
|level|杠杆|query|false|number(decimal)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||positionGear|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|Id|string||
|createTime|CreateTime|string(date-time)|string(date-time)|
|creatorId|CreatorId|string||
|deleted|Deleted|boolean||
|gear|持仓挡位|integer(int32)|integer(int32)|
|maxVolumn|最大张数|integer(int32)|integer(int32)|
|minVolumn|最小张数|integer(int32)|integer(int32)|
|keepMargin|维持保证金率|number(decimal)|number(decimal)|
|minInitialMargin|最低初始保证金率|number(decimal)|number(decimal)|
|maxUseLeverage|最高可用杠杆|number(decimal)|number(decimal)|
|contractId|合约Id|string||


**响应示例**:
```javascript
{
	"id": "",
	"createTime": "",
	"creatorId": "",
	"deleted": true,
	"gear": 0,
	"maxVolumn": 0,
	"minVolumn": 0,
	"keepMargin": 0,
	"minInitialMargin": 0,
	"maxUseLeverage": 0,
	"contractId": ""
}
```


## 获取支持币种列表


**接口地址**:`/api/v1/getCoins`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||coinDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|币种Id|string||
|code|币种编码|string||
|openConvertRate|开仓折算率|number(decimal)|number(decimal)|
|holdConvertRate|持仓折算率|number(decimal)|number(decimal)|
|icon|图标|string||
|unitPrecision|单位精度|integer(int32)|integer(int32)|


**响应示例**:
```javascript
[
	{
		"id": "",
		"code": "",
		"openConvertRate": 0,
		"holdConvertRate": 0,
		"icon": "",
		"unitPrecision": 0
	}
]
```


## 获取支持的合约


**接口地址**:`/api/v1/getContracts`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


暂无


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||contractDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|合约Id|string||
|name|合约名称|string||
|priceIncrement|最小报价单位|number(decimal)|number(decimal)|
|sizeIncrement|最小数量单位|number(decimal)|number(decimal)|
|positionLimitWeight|仓位限制加权|number(decimal)|number(decimal)|
|level|杠杆倍数|number(decimal)|number(decimal)|
|tickSize|OrderBook刻度|array||
|faceValue|面值|number(decimal)|number(decimal)|
|minChangeUnit|最小变动单位|number(decimal)|number(decimal)|
|positionModel|支持的持仓模式|array|MarginMode|
|icon|图标|string||
|predictionRate|预测资金费率|number(decimal)|number(decimal)|
|theRate|本期资金费率|number(decimal)|number(decimal)|
|underlying|币种名称|string||
|riskReserverAmount|风险准备金|number(decimal)|number(decimal)|


**响应示例**:
```javascript
[
	{
		"id": "",
		"name": "",
		"priceIncrement": 0,
		"sizeIncrement": 0,
		"positionLimitWeight": 0,
		"level": 0,
		"tickSize": [],
		"faceValue": 0,
		"minChangeUnit": 0,
		"positionModel": [
			""
		],
		"icon": "",
		"predictionRate": 0,
		"theRate": 0,
		"underlying": "",
		"riskReserverAmount": 0
	}
]
```


## 资产划转


**接口地址**:`/api/v1/transferAssets`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|coinId|币种ID|query|false|string||
|amount|数量|query|false|number(decimal)||
|side|从合约转到现货=0,从现货转到合约=1,从合约转到法币=2,从法币转到合约=3|query|false|transferDirection|transferDirection|
|&emsp;&emsp;undefined|可用值:0,1,2,3||false|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|||


**响应参数**:


暂无


**响应示例**:
```javascript

```


## 获取用户在合约平台上币种的可用数量


**接口地址**:`/api/v1/getAvailableQuantity`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|coinId|币种Id|query|false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|||


**响应参数**:


暂无


**响应示例**:
```javascript

```


## 获取第三方平台上的币种可用数量


**接口地址**:`/api/v1/getThirdPartyAvailableQuantity`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|coinId|币种Id|query|false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|||


**响应参数**:


暂无


**响应示例**:
```javascript

```


## 资产划转记录


**接口地址**:`/api/v1/getAssetTransferRecords`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Direction|从合约转到现货=0,从现货转到合约=1,从合约转到法币=2,从法币转到合约=3|query|false|transferDirection|transferDirection|
|&emsp;&emsp;undefined|可用值:0,1,2,3||false|integer||
|Coin|币种|query|false|string||
|PageIndex|当前页码|query|false|integer(int32)||
|PageSize|每页行数|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||pageResultOfAssetTransferRecordDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|success|是否成功|boolean||
|errorCode|错误代码|integer(int32)|integer(int32)|
|msg|返回消息|string||
|total|总记录数|integer(int32)|integer(int32)|
|data|划转记录列表|AssetTransferRecordDTO|AssetTransferRecordDTO|


**响应示例**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## 获取客户资产信息


**接口地址**:`/api/v1/getAsset`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||assetsDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|totalOpenEquities|联合保证金折合-开仓折合USDT|number(decimal)|number(decimal)|
|totalHoldEquities|折合权益-持仓折合USDT|number(decimal)|number(decimal)|
|unrealizedPNL|未实现盈亏|number(decimal)|number(decimal)|
|frozen|占用|number(decimal)|number(decimal)|
|available|可用|number(decimal)|number(decimal)|
|actuallyAvailable|实际可用|number(decimal)|number(decimal)|
|crossMarginRate|全仓保证金率|number(decimal)|number(decimal)|
|detail|币种资产明细|array|AssetsItemDTO|
|maximumOpenPositions|合约品种最大可开仓数量|array|MaximumOpenPositionItem|


**响应示例**:
```javascript
{
	"totalOpenEquities": 0,
	"totalHoldEquities": 0,
	"unrealizedPNL": 0,
	"frozen": 0,
	"available": 0,
	"actuallyAvailable": 0,
	"crossMarginRate": 0,
	"detail": [
		""
	],
	"maximumOpenPositions": [
		""
	]
}
```


## 获取我的持仓


**接口地址**:`/api/v1/getMyPositions`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||PositionDTO|


**响应参数**:


暂无


**响应示例**:
```javascript

```


## 获取账单明细


**接口地址**:`/api/v1/getBillingRecords`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|CoinId|币种|query|false|string||
|billType|账单类型:换币=1,划转=2,交易=3,强平=4,减仓=5,利息=6,资金费=7|query|false|billType|billType|
|&emsp;&emsp;undefined|可用值:1,2,3,4,5,6,7||false|integer||
|pageResultOfBillingRecordView|账单交易类型:买入开多=1,卖出平多=2,卖出开空=3,买入平空=4,强制平多=5,强制平空=6,换币转出=7,换币转入=8,币币到合约=9,合约到币币=10,资金费用支出=11,资金费用收入=12,强制减仓平多=13,强制减仓平空=14,自动减仓平多=15,自动减仓平空=16,利息支出=17,穿仓弥补=18,法币到合约=20,合约到法币=21|query|false|billTradeType|billTradeType|
|&emsp;&emsp;undefined|可用值:1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21||false|integer||
|PageIndex|当前页码|query|false|integer(int32)||
|PageSize|每页行数|query|false|integer(int32)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||pageResultOfbillingTrade|


**响应参数**:


暂无


**响应示例**:
```javascript

```


## 获取账单记录


**接口地址**:`/api/v1/getpcBillingRecords`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|CoinId|币种Id|query|false|string||
|BillType|账单类型:换币=1,划转=2,交易=3,强平=4,减仓=5,利息=6,资金费=7|query|false|BillType|BillType|
|billTradeType|账单交易类型:买入开多=1,卖出平多=2,卖出开空=3,买入平空=4,强制平多=5,强制平空=6,换币转出=7,换币转入=8,币币到合约=9,合约到币币=10,资金费用支出=11,资金费用收入=12,强制减仓平多=13,强制减仓平空=14,自动减仓平多=15,自动减仓平空=16,利息支出=17,穿仓弥补=18,法币到合约=20,合约到法币=21|query|false|billTradeType|billTradeType|
|&emsp;&emsp;undefined|可用值:1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21||false|integer||
|ContractId|合约Id|query|false|string||
|StartTime|查询开始时间|query|false|string(date-time)||
|EndTime|查询结束时间|query|false|string(date-time)||
|PageIndex|当前页码|query|false|integer(int32)||
|PageRows|每页行数|query|false|integer(int32)||
|SortField|排序列|query|false|string||
|SortType|排序类型|query|false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||pageResultOfBillingRecordView|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|success|是否成功|boolean||
|errorCode|错误代码|integer(int32)|integer(int32)|
|msg|返回消息|string||
|total|总记录数|integer(int32)|integer(int32)|
|data|账单记录列表|BillingRecordView|BillingRecordView|


**响应示例**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## 获取指定合约用户配置


**接口地址**:`/api/v1/getContractCustomerSetting`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|contractId|合约Id|query|false|string||
|marginMode|全仓保证金模式=0,逐仓保证金模式=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||contractCustomerSettings|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|主键|string||
|createTime|创建时间|string(date-time)|string(date-time)|
|contractId|合约id|string||
|customerId|客户id|string||
|marginMode|保证金模式【全仓保证金模式=0,逐仓保证金模式=1】|MarginMode|MarginMode|
|leverage|杠杆倍数|number(decimal)|number(decimal)|
|side|多空方向【多空方向:多=0,空=1】|ContractSide|ContractSide|
|isDefault|是否默认|boolean||


**响应示例**:
```javascript
[
	{
		"id": "",
		"createTime": "",
		"contractId": "",
		"customerId": "",
		"marginMode": "",
		"leverage": 0,
		"side": "",
		"isDefault": true
	}
]
```


## 获取默认合约仓模式配置


**接口地址**:`/api/v1/getDefaultContractCustomerSetting`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|contractId|合约Id|query|false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||contractCustomerSettings|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|id|主键|string||
|createTime|创建时间|string(date-time)|string(date-time)|
|contractId|合约id|string||
|customerId|客户id|string||
|marginMode|保证金模式【全仓保证金模式=0,逐仓保证金模式=1】|MarginMode|MarginMode|
|leverage|杠杆倍数|number(decimal)|number(decimal)|
|side|多空方向【多空方向:多=0,空=1】|ContractSide|ContractSide|
|isDefault|是否默认|boolean||


**响应示例**:
```javascript
[
	{
		"id": "",
		"createTime": "",
		"contractId": "",
		"customerId": "",
		"marginMode": "",
		"leverage": 0,
		"side": "",
		"isDefault": true
	}
]
```


## 设置默认保证金模式


**接口地址**:`/api/v1/setDefaultmarginMode`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|contractId|合约Id|query|false|string||
|marginMode|全仓保证金模式=0,逐仓保证金模式=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|||


**响应参数**:


暂无


**响应示例**:
```javascript

```


## 设置杠杆倍数


**接口地址**:`/api/v1/setLeverage`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|contractId|合约Id|query|false|string||
|marginMode|全仓保证金模式=0,逐仓保证金模式=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|side|多空方向:多=0,空=1|query|false|contractSide|contractSide|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|leverage|杠杆倍数|query|false|number(decimal)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|||


**响应参数**:


暂无


**响应示例**:
```javascript

```


## 获取逐仓保证金


**接口地址**:`/api/v1/getIsolatedMargin`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|contractId||query|false|string||
|side|多空方向:多=0,空=1|query|false|contractSide|contractSide|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||positionAssetDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|coin|币种|string||
|quantity|数量|number(decimal)|number(decimal)|
|icon|币种图标|string||


**响应示例**:
```javascript
[
	{
		"coin": "",
		"quantity": 0,
		"icon": ""
	}
]
```


## 逐仓保证金调整


**接口地址**:`/api/v1/adjustIsolatedMargin`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|contractId|合约Id|query|false|string||
|side|多空方向:多=0,空=1|query|false|contractSide|contractSide|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|adjustModel|调整参数类型:数量=0,比例=1|query|false|adjustModel|adjustModel|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|amount|追加/减少保证金|query|false|number(decimal)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|||


**响应参数**:


暂无


**响应示例**:
```javascript

```


## 评估追加保证金


**接口地址**:`/api/v1/estimateCallMargin`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|contractId|合约Id|query|false|string||
|side|多空方向:多=0,空=1|query|false|contractSide|contractSide|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|adjustModel|调整参数类型:数量=0,比例=1|query|false|adjustModel|adjustModel|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|amount|评估数量|query|false|number(decimal)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||estimateIsolatedMarginDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|maximum|最多可操作数量|number(decimal)|number(decimal)|
|leverage|杠杆 |number(decimal)|number(decimal)|
|liquidationPrice|强平价格|number(decimal)|number(decimal)|


**响应示例**:
```javascript
{
	"maximum": 0,
	"leverage": 0,
	"liquidationPrice": 0
}
```


## 评估减少保证金


**接口地址**:`/api/v1/estimateReduceMargin`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|contractId|合约Id|query|false|string||
|side|多空方向:多=0,空=1|query|false|contractSide|contractSide|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|adjustModel|调整参数类型:数量=0,比例=1|query|false|adjustModel|adjustModel|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|amount|评估数量|query|false|number(decimal)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||estimateIsolatedMarginDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|maximum|最多可操作数量|number(decimal)|number(decimal)|
|leverage|杠杆 |number(decimal)|number(decimal)|
|liquidationPrice|强平价格|number(decimal)|number(decimal)|


**响应示例**:
```javascript
{
	"maximum": 0,
	"leverage": 0,
	"liquidationPrice": 0
}
```


## 评估调整合约杠杆


**接口地址**:`/api/v1/estimateAdjustLeverage`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|contractId|合约Id|query|false|string||
|marginMode|全仓保证金模式=0,逐仓保证金模式=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|side|多空方向:多=0,空=1|query|false|contractSide|contractSide|
|&emsp;&emsp;undefined|可用值:0,1||false|integer||
|leverage|杠杆倍数|query|false|number(decimal)||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||estimateAdjustLeverageDTO|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|maximumOpenCont|最大可开张数|integer(int64)|integer(int64)|
|maximumOpenQty|最大可开币数|number(decimal)|number(decimal)|
|requiredMargin|当前仓位所需保证金|number(decimal)|number(decimal)|
|estimatedLiquidationPrice|预估强平价格|number(decimal)|number(decimal)|
|qtyOfMarginChange|保证金变动数量|number(decimal)|number(decimal)|
|maximumHoldCont|最大持仓张数|integer(int64)|integer(int64)|


**响应示例**:
```javascript
{
	"maximumOpenCont": 0,
	"maximumOpenQty": 0,
	"requiredMargin": 0,
	"estimatedLiquidationPrice": 0,
	"qtyOfMarginChange": 0,
	"maximumHoldCont": 0
}
```


## 获取账户手续费


**接口地址**:`/api/v1/getMyHandlingFee`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`*/*`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200||valueTupleOfDecimalAndDecimal|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|item1||number(decimal)|number(decimal)|
|item2||number(decimal)|number(decimal)|


**响应示例**:
```javascript
{
	"item1": 0,
	"item2": 0
}
```