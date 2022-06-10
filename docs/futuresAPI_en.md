# IDCM Futures Api


**Description**:IDCM Futures Api


**HOST**:https://ctapi.klickl.com/


**Contacts**:


**Version**:1.0.0


**URL**:SwaggerDocument/Swagger


[TOC]

 


## Batch limit market price order opening


**url**:`/api/v1/batchOpenOrder`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded,application/json`


**consumes**:`*/*`


**Note**:


**Example**:


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


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|openOrderRequests|openOrderRequest|body|true|array|openOrderRequest|
|&emsp;&emsp;symbol|Symbol Name||false|string||
|&emsp;&emsp;side|Billing direction 0=Long 1=Short 【Long/short direction:Long=0,short=1】||false|ContractSide|ContractSide|
|&emsp;&emsp;price|price||false|number(decimal)||
|&emsp;&emsp;type|Order Type 5=Market Price 6=Limit【Transaction Type:Market price=5,Limit price=6】||false|OrderType|OrderType|
|&emsp;&emsp;size|Quantity||false|number(decimal)||
|&emsp;&emsp;clientId|Customized by customerSingle No.||false|string||
|&emsp;&emsp;unitMode|Trading unit mode 0=const 1=coin【Trading unit mode: cont=0,coin=1】||false|TradingUnitMode|TradingUnitMode|
|&emsp;&emsp;marginMode|Positioning Model 【Full margin mode=0,Position by position margin mode=1】||false|MarginMode|MarginMode|
|X-RECVWINDOW|recvwindow|header|false|||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||orderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|Single No.|string||
|createTime|Entrusted time|string(date-time)|string(date-time)|
|contractId||string||
|customerId|Customer Id|string||
|orderType|Transaction Type【Transaction Type:Market price=5,Limit price=6】|OrderType|OrderType|
|price|Commissioning Price|number(decimal)|number(decimal)|
|totalQty|Total number of commissions|number(decimal)|number(decimal)|
|cumQty|Number of transactions|number(decimal)|number(decimal)|
|avgExecutionPrice|Average transaction price|number(decimal)|number(decimal)|
|status|Status【 OrderStatus:Pending orders=0,Partially filled=1,Fully filled=2,Withdrawn=3,Invalid orders=99】|OrderStatus|OrderStatus|
|side|Transaction Type 0=open long 1=open short 2flat=short 3=flat long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】|ContractTradeSide|ContractTradeSide|
|clientId|Customized by customerSingle No.|string||
|lastUpdateTime|Last operation time|string(date-time)|string(date-time)|
|multiple|Leverage multiplier|number(decimal)|number(decimal)|
|uFee|Handling fee|number(decimal)|number(decimal)|
|pnl|Earnings|number(decimal)|number(decimal)|
|marginMode|Margin mode [Full margin mode=0,Position by position margin mode=1]|MarginMode|MarginMode|
|symbol|Symbol Name|string||
|pnlRate|Earnings Rate|number(decimal)|number(decimal)|


**Response Example**:
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


## Lot Limit Price Market Entrusted Closeout


**url**:`/api/v1/batchCloseOrder`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded,application/json`


**consumes**:`*/*`


**Note**:


**Example**:


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


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|closeOrderRequests|closeOrderRequest|body|true|array|closeOrderRequest|
|&emsp;&emsp;symbol|Symbol Name||false|string||
|&emsp;&emsp;side|Long/short direction 0=Long 1=Short【Long/short direction:Long=0,short=1】||false|ContractSide|ContractSide|
|&emsp;&emsp;size|Quantity||false|number(decimal)||
|&emsp;&emsp;price|price||false|number(decimal)||
|&emsp;&emsp;type|Order Type 5=Market Price 6=Limit【Transaction Type:Market price=5,Limit price=6】||false|OrderType|OrderType|
|&emsp;&emsp;clientId|Customized by customerSingle No. ||false|string||
|&emsp;&emsp;unitMode|Trading unit mode 0=const 1=coin【Trading unit mode: cont=0,coin=1】||false|TradingUnitMode|TradingUnitMode|
|&emsp;&emsp;marginMode|Positioning Model 【Full margin mode=0,Position by position margin mode=1】||false|MarginMode|MarginMode|
|X-RECVWINDOW|recvwindow|header|false|||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||orderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|Single No.|string||
|createTime|Entrusted time|string(date-time)|string(date-time)|
|contractId||string||
|customerId|Customer Id|string||
|orderType|Transaction Type【Transaction Type:Market price=5,Limit price=6】|OrderType|OrderType|
|price|Commissioning Price|number(decimal)|number(decimal)|
|totalQty|Total number of commissions|number(decimal)|number(decimal)|
|cumQty|Number of transactions|number(decimal)|number(decimal)|
|avgExecutionPrice|Average transaction price|number(decimal)|number(decimal)|
|status|Status【 OrderStatus:Pending orders=0,Partially filled=1,Fully filled=2,Withdrawn=3,Invalid orders=99】|OrderStatus|OrderStatus|
|side|Transaction Type 0=open long 1=open short 2flat=short 3=flat long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】|ContractTradeSide|ContractTradeSide|
|clientId|Customized by customerSingle No.|string||
|lastUpdateTime|Last operation time|string(date-time)|string(date-time)|
|multiple|Leverage multiplier|number(decimal)|number(decimal)|
|uFee|Handling fee|number(decimal)|number(decimal)|
|pnl|Earnings|number(decimal)|number(decimal)|
|marginMode|Margin mode [Full margin mode=0,Position by position margin mode=1]|MarginMode|MarginMode|
|symbol|Symbol Name|string||
|pnlRate|Earnings Rate|number(decimal)|number(decimal)|


**Response Example**:
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


## Batch Stop profit Stop Loss Entrusted Open 


**url**:`/api/v1/batchOpenKillOrFillOrder`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded,application/json`


**consumes**:`*/*`


**Note**:


**Example**:


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


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|fillOrKillOrderRequests|fillOrKillOrderRequest|body|true|array|fillOrKillOrderRequest|
|&emsp;&emsp;symbol|Symbol Name||true|string||
|&emsp;&emsp;side| Direction 0=One-way Stop profit Stop Loss   1=Bidirectional Stop profit Stop Loss 【Stop Loss Order Direction:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3】||false|FillOrKillOrderSide|FillOrKillOrderSide|
|&emsp;&emsp;fillTriggerPrice|Stop profit Trigger price||false|number(decimal)||
|&emsp;&emsp;fillTrustPrice|Stop profit Entrusted price||false|number(decimal)||
|&emsp;&emsp;killTriggerPrice|Stop Loss Trigger price||false|number(decimal)||
|&emsp;&emsp;killTrustPrice|Stop Loss Entrusted price||false|number(decimal)||
|&emsp;&emsp;tradeSide|Transaction Type 0=open long 1=open short 2flat=short 3=flat long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】||false|ContractTradeSide|ContractTradeSide|
|&emsp;&emsp;trustQty|Quantity||false|number(decimal)||
|&emsp;&emsp;triggerPriceKind|price Source Type 0=Market 1=Marker 2=Index【K-line price Source Type:Market=0,Marker=1,Index=2】||false|KLineType|KLineType|
|&emsp;&emsp;unitMode|Trading unit 0=const 1=coin【Trading unit mode: cont=0,coin=1】||false|TradingUnitMode|TradingUnitMode|
|&emsp;&emsp;marginMode|Positioning Model 【Full margin mode=0,Position by position margin mode=1】||false|MarginMode|MarginMode|
|X-RECVWINDOW|recvwindow|header|false|||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||fillOrKillOrderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|Single No.|string||
|createTime|Entrusted time|string(date-time)|string(date-time)|
|contractId|futures Id|string||
|customerId|Customer Id|string||
|multiple|Leverage multiplier|number(decimal)|number(decimal)|
|status|Status【Stop Loss OrderStatus:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3】|FillOrKillOrderStatus|FillOrKillOrderStatus|
|side| Direction【Stop Loss Order Direction:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3】|FillOrKillOrderSide|FillOrKillOrderSide|
|tradeSide|Transaction Type 0=open long 1=open short 2flat=short 3=flat long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】|ContractTradeSide|ContractTradeSide|
|marginMode|Margin mode [Full margin mode=0,Position by position margin mode=1]|MarginMode|MarginMode|
|fillTriggerPrice|Stop profit Trigger price|number(decimal)|number(decimal)|
|fillTrustPrice|Stop profit Entrusted price Empty for market price|number(decimal)|number(decimal)|
|killTriggerPrice|Stop Loss Trigger price|number(decimal)|number(decimal)|
|killTrustPrice|Stop Loss Entrusted price Empty for market price|number(decimal)|number(decimal)|
|trustQty|Entrusted Quantity|number(decimal)|number(decimal)|
|realTrustQty|Actual Entrusted Quantity|number(decimal)|number(decimal)|
|cumQty|Entrusted volume |number(decimal)|number(decimal)|
|triggerDirection|Trigger  Direction【Trigger  Direction:止赢=0,Stop Loss =1】|FillOrKillTriggerDirection|FillOrKillTriggerDirection|
|triggerPriceKind|Trigger price Category【K-line price Source Type:Market=0,Marker=1,Index=2】|KLineType|KLineType|
|realTrustPrice|Actual Entrusted price|number(decimal)|number(decimal)|
|lastUpdateTime|Last operation time|string(date-time)|string(date-time)|
|clientId|Customized by customerSingle No.|string||
|orderId|Trigger Generate Single No.|string||
|symbol|Symbol Name|string||


**Response Example**:
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


## Batch Stop profit Stop Loss Entrusted close


**url**:`/api/v1/batchCloseKillOrFillOrder`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded,application/json`


**consumes**:`*/*`


**Note**:


**Example**:


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


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|fillOrKillOrderRequests|fillOrKillOrderRequest|body|true|array|fillOrKillOrderRequest|
|&emsp;&emsp;symbol|Symbol Name||true|string||
|&emsp;&emsp;side| Direction 0=One-way Stop profit Stop Loss   1=Bidirectional Stop profit Stop Loss 【Stop Loss Order Direction:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3】||false|FillOrKillOrderSide|FillOrKillOrderSide|
|&emsp;&emsp;fillTriggerPrice|Stop profit Trigger price||false|number(decimal)||
|&emsp;&emsp;fillTrustPrice|Stop profit Entrusted price||false|number(decimal)||
|&emsp;&emsp;killTriggerPrice|Stop Loss Trigger price||false|number(decimal)||
|&emsp;&emsp;killTrustPrice|Stop Loss Entrusted price||false|number(decimal)||
|&emsp;&emsp;tradeSide|Transaction Type 0=open long 1=open short 2flat=short 3=flat long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】||false|ContractTradeSide|ContractTradeSide|
|&emsp;&emsp;trustQty|Quantity||false|number(decimal)||
|&emsp;&emsp;triggerPriceKind|price Source Type 0=Market 1=Marker 2=Index【K-line price Source Type:Market=0,Marker=1,Index=2】||false|KLineType|KLineType|
|&emsp;&emsp;unitMode|Trading unit 0=const 1=coin【Trading unit mode: cont=0,coin=1】||false|TradingUnitMode|TradingUnitMode|
|&emsp;&emsp;marginMode|Positioning Model 【Full margin mode=0,Position by position margin mode=1】||false|MarginMode|MarginMode|
|X-RECVWINDOW|recvwindow|header|false|||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||fillOrKillOrderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|Single No.|string||
|createTime|Entrusted time|string(date-time)|string(date-time)|
|contractId|futures Id|string||
|customerId|Customer Id|string||
|multiple|Leverage multiplier|number(decimal)|number(decimal)|
|status|Status【Stop Loss OrderStatus:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3】|FillOrKillOrderStatus|FillOrKillOrderStatus|
|side| Direction【Stop Loss Order Direction:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3】|FillOrKillOrderSide|FillOrKillOrderSide|
|tradeSide|Transaction Type 0=open long 1=open short 2flat=short 3=flat long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】|ContractTradeSide|ContractTradeSide|
|marginMode|Margin mode [Full margin mode=0,Position by position margin mode=1]|MarginMode|MarginMode|
|fillTriggerPrice|Stop profit Trigger price|number(decimal)|number(decimal)|
|fillTrustPrice|Stop profit Entrusted price Empty for market price|number(decimal)|number(decimal)|
|killTriggerPrice|Stop Loss Trigger price|number(decimal)|number(decimal)|
|killTrustPrice|Stop Loss Entrusted price Empty for market price|number(decimal)|number(decimal)|
|trustQty|Entrusted Quantity|number(decimal)|number(decimal)|
|realTrustQty|Actual Entrusted Quantity|number(decimal)|number(decimal)|
|cumQty|Entrusted volume |number(decimal)|number(decimal)|
|triggerDirection|Trigger  Direction【Trigger  Direction:止赢=0,Stop Loss =1】|FillOrKillTriggerDirection|FillOrKillTriggerDirection|
|triggerPriceKind|Trigger price Category【K-line price Source Type:Market=0,Marker=1,Index=2】|KLineType|KLineType|
|realTrustPrice|Actual Entrusted price|number(decimal)|number(decimal)|
|lastUpdateTime|Last operation time|string(date-time)|string(date-time)|
|clientId|Customized by customerSingle No.|string||
|orderId|Trigger Generate Single No.|string||
|symbol|Symbol Name|string||


**Response Example**:
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


## Batch Program Entrusted Single Open Position


**url**:`/api/v1/batchOpenPlanOrder`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded,application/json`


**consumes**:`*/*`


**Note**:


**Example**:


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


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|planOrderRequests|planOrderRequest|body|true|array|planOrderRequest|
|&emsp;&emsp;symbol|Symbol Name||true|string||
|&emsp;&emsp;clientId|Customization Single No.||false|string||
|&emsp;&emsp;trustPrice|Entrusted price Empty for market price\n ||false|number(decimal)||
|&emsp;&emsp;triggerPrice|Trigger price||false|number(decimal)||
|&emsp;&emsp;trustQty|Entrusted Quantity||false|number(decimal)||
|&emsp;&emsp;side|Transaction Type 0=open long position 1=open short position 2=close short 3=close long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】||false|ContractTradeSide|ContractTradeSide|
|&emsp;&emsp;triggerPriceKind|price Source Type 0=Market 1=Marker 2=Index 【K-line price Source Type:Market=0,Marker=1,Index=2】||false|KLineType|KLineType|
|&emsp;&emsp;unitMode|Trading unit 0=const 1=coin【Trading unit mode: cont=0,coin=1】||false|TradingUnitMode|TradingUnitMode|
|&emsp;&emsp;marginMode|Positioning Model 【Full margin mode=0,Position by position margin mode=1】||false|MarginMode|MarginMode|
|X-RECVWINDOW|recvwindow|header|false|||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||planOrderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|Single No.|string||
|createTime|Entrusted time|string(date-time)|string(date-time)|
|contractId|futures Id|string||
|customerId|Customer Id|string||
|lastUpdateTime|Last operation time|string(date-time)|string(date-time)|
|multiple|Leverage multiplier|number(decimal)|number(decimal)|
|status|Status【Plan orderStatus:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3】|PlanOrderStatus|PlanOrderStatus|
|tradeSide|Transaction Type 0=open long 1=open short 2flat=short 3=flat long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】|ContractTradeSide|ContractTradeSide|
|marginMode|Margin mode [Full margin mode=0,Position by position margin mode=1]|MarginMode|MarginMode|
|triggerPrice|Trigger price|number(decimal)|number(decimal)|
|trustPrice|Entrusted price Empty for market price\n |number(decimal)|number(decimal)|
|trustQty|Entrusted Quantity|number(decimal)|number(decimal)|
|realTrustQty|Actual Entrusted Quantity|number(decimal)|number(decimal)|
|triggerPriceKind|Trigger price Category【K-line price Source Type:Market=0,Marker=1,Index=2】|KLineType|KLineType|
|realTrustPrice|Actual Entrusted price|number(decimal)|number(decimal)|
|clientId|Customized by customerSingle No.|string||
|orderId|Trigger Generate Single No.|string||
|symbol|Symbol Name|string||


**Response Example**:
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


## Batch Plan Entrusted order closing


**url**:`/api/v1/batchClosePlanOrder`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded,application/json`


**consumes**:`*/*`


**Note**:


**Example**:


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


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|planOrderRequests|planOrderRequest|body|true|array|planOrderRequest|
|&emsp;&emsp;symbol|Symbol Name||true|string||
|&emsp;&emsp;clientId|Customization Single No.||false|string||
|&emsp;&emsp;trustPrice|Entrusted price Empty for market price\n ||false|number(decimal)||
|&emsp;&emsp;triggerPrice|Trigger price||false|number(decimal)||
|&emsp;&emsp;trustQty|Entrusted Quantity||false|number(decimal)||
|&emsp;&emsp;side|Transaction Type 0=open long position 1=open short position 2=close short 3=close long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】||false|ContractTradeSide|ContractTradeSide|
|&emsp;&emsp;triggerPriceKind|price Source Type 0=Market 1=Marker 2=Index 【K-line price Source Type:Market=0,Marker=1,Index=2】||false|KLineType|KLineType|
|&emsp;&emsp;unitMode|Trading unit 0=const 1=coin【Trading unit mode: cont=0,coin=1】||false|TradingUnitMode|TradingUnitMode|
|&emsp;&emsp;marginMode|Positioning Model 【Full margin mode=0,Position by position margin mode=1】||false|MarginMode|MarginMode|
|X-RECVWINDOW|recvwindow|header|false|||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||planOrderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|Single No.|string||
|createTime|Entrusted time|string(date-time)|string(date-time)|
|contractId|futures Id|string||
|customerId|Customer Id|string||
|lastUpdateTime|Last operation time|string(date-time)|string(date-time)|
|multiple|Leverage multiplier|number(decimal)|number(decimal)|
|status|Status【Plan orderStatus:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3】|PlanOrderStatus|PlanOrderStatus|
|tradeSide|Transaction Type 0=open long 1=open short 2flat=short 3=flat long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】|ContractTradeSide|ContractTradeSide|
|marginMode|Margin mode [Full margin mode=0,Position by position margin mode=1]|MarginMode|MarginMode|
|triggerPrice|Trigger price|number(decimal)|number(decimal)|
|trustPrice|Entrusted price Empty for market price\n |number(decimal)|number(decimal)|
|trustQty|Entrusted Quantity|number(decimal)|number(decimal)|
|realTrustQty|Actual Entrusted Quantity|number(decimal)|number(decimal)|
|triggerPriceKind|Trigger price Category【K-line price Source Type:Market=0,Marker=1,Index=2】|KLineType|KLineType|
|realTrustPrice|Actual Entrusted price|number(decimal)|number(decimal)|
|clientId|Customized by customerSingle No.|string||
|orderId|Trigger Generate Single No.|string||
|symbol|Symbol Name|string||


**Response Example**:
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


## Limit market price Entrusted open position


**url**:`/api/v1/openOrder`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|symbol|Symbol Name|query|false|string||
|side|Long/short direction:Long=0,short=1|query|false|contractSide|contractSide|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|price|price|query|false|number(decimal)||
|type|Transaction Type:Market price=5,Limit price=6|query|false|orderType|orderType|
|&emsp;&emsp;undefined|Available values:2,3,4,5,6,7,8,9||false|integer||
|size|Quantity|query|false|number(decimal)|| 
|clientId|Customized by customerSingle No.|query|false|string||
|unitMode|Trading unit mode: cont=0,coin=1|query|false|tradingUnitMode|tradingUnitMode|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|marginMode|Full margin mode=0,Position by position margin mode=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||orderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|Single No.|string||
|createTime|Entrusted time|string(date-time)|string(date-time)|
|contractId||string||
|customerId|Customer Id|string||
|orderType|Transaction Type【Transaction Type:Market price=5,Limit price=6】|OrderType|OrderType|
|price|Commissioning Price|number(decimal)|number(decimal)|
|totalQty|Total number of commissions|number(decimal)|number(decimal)|
|cumQty|Number of transactions|number(decimal)|number(decimal)|
|avgExecutionPrice|Average transaction price|number(decimal)|number(decimal)|
|status|Status【Order Status:Pending orders=0,Partially filled=1,Fully filled=2,Withdrawn=3,Invalid orders=99】|OrderStatus|OrderStatus|
|side|Transaction Type 0=open long 1=open short 2flat=short 3=flat long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】|ContractTradeSide|ContractTradeSide|
|clientId|Customized by customerSingle No.|string||
|lastUpdateTime|Last operation time|string(date-time)|string(date-time)|
|multiple|Leverage multiplier|number(decimal)|number(decimal)|
|uFee|Handling fee|number(decimal)|number(decimal)|
|pnl|Earnings|number(decimal)|number(decimal)|
|marginMode|Margin mode [Full margin mode=0,Position by position margin mode=1]|MarginMode|MarginMode|
|symbol|Symbol Name|string||
|pnlRate|Earnings Rate|number(decimal)|number(decimal)|


**Response Example**:
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


## Price limit market price Entrusted close


**url**:`/api/v1/closeOrder`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|Symbol Name|query|false|string||
|Side|Long/short direction:Long=0,short=1|query|false|contractSide|contractSide|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|Size|Quantity|query|false|number(decimal)||
|Price|price|query|false|number(decimal)||
|Type|Transaction Type:Market price=5,Limit price=6|query|false|orderType|orderType|
|&emsp;&emsp;undefined|Available values:2,3,4,5,6,7,8,9||false|integer||
|ClientId|Customized by customerSingle No. |query|false|string||
|UnitMode|Trading unit mode: cont=0,coin=1|query|false|tradingUnitMode|tradingUnitMode|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|marginMode|Full margin mode=0,Position by position margin mode=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||orderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|Single No.|string||
|createTime|Entrusted time|string(date-time)|string(date-time)|
|contractId||string||
|customerId|Customer Id|string||
|orderType|Transaction Type【Transaction Type:Market price=5,Limit price=6】|OrderType|OrderType|
|price|Commissioning Price|number(decimal)|number(decimal)|
|totalQty|Total number of commissions|number(decimal)|number(decimal)|
|cumQty|Number of transactions|number(decimal)|number(decimal)|
|avgExecutionPrice|Average transaction price|number(decimal)|number(decimal)|
|status|Status【 OrderStatus:Pending orders=0,Partially filled=1,Fully filled=2,Withdrawn=3,Invalid orders=99】|OrderStatus|OrderStatus|
|side|Transaction Type 0=open long 1=open short 2flat=short 3=flat long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】|ContractTradeSide|ContractTradeSide|
|clientId|Customized by customerSingle No.|string||
|lastUpdateTime|Last operation time|string(date-time)|string(date-time)|
|multiple|Leverage multiplier|number(decimal)|number(decimal)|
|uFee|Handling fee|number(decimal)|number(decimal)|
|pnl|Earnings|number(decimal)|number(decimal)|
|marginMode|Margin mode [Full margin mode=0,Position by position margin mode=1]|MarginMode|MarginMode|
|symbol|Symbol Name|string||
|pnlRate|Earnings Rate|number(decimal)|number(decimal)|


**Response Example**:
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


## Cancellation of limit market price order


**url**:`/api/v1/cancelOrder`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|symbol||query|false|string||
|orderId||query|false|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200|||


**Response Params**:


None


**Response Example**:
```javascript

```


## Withdrawal of all limit market price orders


**url**:`/api/v1/cancelAllOpenOrders`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|symbol||query|false|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200|||


**Response Params**:


None


**Response Example**:
```javascript

```


## Get the limit market order for the current commission


**url**:`/api/v1/getActiveOrders`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|Symbol Name|query|false|string||
|Side|Open long position=0,Open short position=1,Close short position=2,Close long position=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|Available values:0,1,2,3||false|integer||
|PageIndex|Current page number|query|false|integer(int32)||
|PageSize|Number of lines per page|query|false|integer(int32)||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||pageResultOfOrderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|success|Success or failure|boolean||
|errorCode|Error Code|integer(int32)|integer(int32)|
|msg|Return Message|string||
|total|Total number of records|integer(int32)|integer(int32)|
|data|Orders List|OrderDTO|OrderDTO|


**Response Example**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## Get limit market orders for historical orders


**url**:`/api/v1/getHistoryOrders`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|Symbol Name|query|false|string||
|Side|Open long position=0,Open short position=1,Close short position=2,Close long position=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|Available values:0,1,2,3||false|integer||
|PageIndex|Current page number|query|false|integer(int32)||
|PageSize|Number of lines per page|query|false|integer(int32)||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||pageResultOfOrderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|success|Success or failure|boolean||
|errorCode|Error Code|integer(int32)|integer(int32)|
|msg|Return Message|string||
|total|Total number of records|integer(int32)|integer(int32)|
|data|Orders List|OrderDTO|OrderDTO|


**Response Example**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## Get Price limit market price Entrusted  Order Details


**url**:`/api/v1/getOrderDetail`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|orderId||query|false|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||orderDetailDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|Single No.|string||
|createTime|Entrusted time|string(date-time)|string(date-time)|
|contractId||string||
|customerId|Customer Id|string||
|orderType|Transaction Type【Transaction Type:Market price=5,Limit price=6】|OrderType|OrderType|
|price|Commissioning Price|number(decimal)|number(decimal)|
|totalQty|Total number of commissions|number(decimal)|number(decimal)|
|cumQty|Number of transactions|number(decimal)|number(decimal)|
|avgExecutionPrice|Average transaction price|number(decimal)|number(decimal)|
|status|Status【 OrderStatus:Pending orders=0,Partially filled=1,Fully filled=2,Withdrawn=3,Invalid orders=99】|OrderStatus|OrderStatus|
|side|Transaction Type 0=open long 1=open short 2flat=short 3=flat long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】|ContractTradeSide|ContractTradeSide|
|clientId|Customized by customerSingle No.|string||
|lastUpdateTime|Last operation time|string(date-time)|string(date-time)|
|multiple|Leverage multiplier|number(decimal)|number(decimal)|
|uFee|Handling fee|number(decimal)|number(decimal)|
|pnl|Earnings|number(decimal)|number(decimal)|
|marginMode|Margin mode [Full margin mode=0,Position by position margin mode=1]|MarginMode|MarginMode|
|symbol|Symbol Name|string||
|pnlRate|Earnings Rate|number(decimal)|number(decimal)|
|orderFilleds|Details of the transaction list|OrderFilledDTO|OrderFilledDTO|


**Response Example**:
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


## Stop profit Stop Loss Entrusted Open 


**url**:`/api/v1/openKillOrFillOrder`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|Symbol Name|query|false|string||
|Side|Stop Loss Order Direction:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3|query|false|fillOrKillOrderSide|fillOrKillOrderSide|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|FillTriggerPrice|Stop profit Trigger price|query|false|number(decimal)||
|FillTrustPrice|Stop profit Entrusted price|query|false|number(decimal)||
|KillTriggerPrice|Stop Loss Trigger price|query|false|number(decimal)||
|KillTrustPrice|Stop Loss Entrusted price|query|false|number(decimal)||
|TradeSide|Open long position=0,Open short position=1,Close short position=2,Close long position=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|Available values:0,1,2,3||false|integer||
|TrustQty|Quantity|query|false|number(decimal)||
|TriggerPriceKind|K-line price Source Type:Market=0,Marker=1,Index=2|query|false|kLineType|kLineType|
|&emsp;&emsp;undefined|Available values:0,1,2||false|integer||
|UnitMode|Trading unit mode: cont=0,coin=1|query|false|tradingUnitMode|tradingUnitMode|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|marginMode|Full margin mode=0,Position by position margin mode=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||fillOrKillOrderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|Single No.|string||
|createTime|Entrusted time|string(date-time)|string(date-time)|
|contractId|futures Id|string||
|customerId|Customer Id|string||
|multiple|Leverage multiplier|number(decimal)|number(decimal)|
|status|Status【Stop Loss OrderStatus:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3】|FillOrKillOrderStatus|FillOrKillOrderStatus|
|side| Direction【Stop Loss Order Direction:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3】|FillOrKillOrderSide|FillOrKillOrderSide|
|tradeSide|Transaction Type 0=open long 1=open short 2flat=short 3=flat long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】|ContractTradeSide|ContractTradeSide|
|marginMode|Margin mode [Full margin mode=0,Position by position margin mode=1]|MarginMode|MarginMode|
|fillTriggerPrice|Stop profit Trigger price|number(decimal)|number(decimal)|
|fillTrustPrice|Stop profit Entrusted price Empty for market price|number(decimal)|number(decimal)|
|killTriggerPrice|Stop Loss Trigger price|number(decimal)|number(decimal)|
|killTrustPrice|Stop Loss Entrusted price Empty for market price|number(decimal)|number(decimal)|
|trustQty|Entrusted Quantity|number(decimal)|number(decimal)|
|realTrustQty|Actual Entrusted Quantity|number(decimal)|number(decimal)|
|cumQty|Entrusted volume |number(decimal)|number(decimal)|
|triggerDirection|Trigger  Direction【Trigger  Direction:Stop win=0,Stop Loss =1】|FillOrKillTriggerDirection|FillOrKillTriggerDirection|
|triggerPriceKind|Trigger price Category【K-line price Source Type:Market=0,Marker=1,Index=2】|KLineType|KLineType|
|realTrustPrice|Actual Entrusted price|number(decimal)|number(decimal)|
|lastUpdateTime|Last operation time|string(date-time)|string(date-time)|
|clientId|Customized by customerSingle No.|string||
|orderId|Trigger Generate Single No.|string||
|symbol|Symbol Name|string||


**Response Example**:
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


## Stop profit Stop Loss Entrusted Closeout


**url**:`/api/v1/closeKillOrFillOrder`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|Symbol Name|query|false|string||
|Side|Stop Loss Order Direction:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3|query|false|fillOrKillOrderSide|fillOrKillOrderSide|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|FillTriggerPrice|Stop profit Trigger price|query|false|number(decimal)||
|FillTrustPrice|Stop profit Entrusted price|query|false|number(decimal)||
|KillTriggerPrice|Stop Loss Trigger price|query|false|number(decimal)||
|KillTrustPrice|Stop Loss Entrusted price|query|false|number(decimal)||
|TradeSide|Open long position=0,Open short position=1,Close short position=2,Close long position=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|Available values:0,1,2,3||false|integer||
|TrustQty|Quantity|query|false|number(decimal)||
|TriggerPriceKind|K-line price Source Type:Market=0,Marker=1,Index=2|query|false|kLineType|kLineType|
|&emsp;&emsp;undefined|Available values:0,1,2||false|integer||
|UnitMode|Trading unit mode: cont=0,coin=1|query|false|tradingUnitMode|tradingUnitMode|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|marginMode|Full margin mode=0,Position by position margin mode=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||fillOrKillOrderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|Single No.|string||
|createTime|Entrusted time|string(date-time)|string(date-time)|
|contractId|futures Id|string||
|customerId|Customer Id|string||
|multiple|Leverage multiplier|number(decimal)|number(decimal)|
|status|Status【Stop Loss OrderStatus:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3】|FillOrKillOrderStatus|FillOrKillOrderStatus|
|side| Direction【Stop Loss Order Direction:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3】|FillOrKillOrderSide|FillOrKillOrderSide|
|tradeSide|Transaction Type 0=open long 1=open short 2flat=short 3=flat long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】|ContractTradeSide|ContractTradeSide|
|marginMode|Margin mode [Full margin mode=0,Position by position margin mode=1]|MarginMode|MarginMode|
|fillTriggerPrice|Stop profit Trigger price|number(decimal)|number(decimal)|
|fillTrustPrice|Stop profit Entrusted price Empty for market price|number(decimal)|number(decimal)|
|killTriggerPrice|Stop Loss Trigger price|number(decimal)|number(decimal)|
|killTrustPrice|Stop Loss Entrusted price Empty for market price|number(decimal)|number(decimal)|
|trustQty|Entrusted Quantity|number(decimal)|number(decimal)|
|realTrustQty|Actual Entrusted Quantity|number(decimal)|number(decimal)|
|cumQty|Entrusted volume |number(decimal)|number(decimal)|
|triggerDirection|Trigger  Direction【Trigger  Direction:止赢=0,Stop Loss =1】|FillOrKillTriggerDirection|FillOrKillTriggerDirection|
|triggerPriceKind|Trigger price Category【K-line price Source Type:Market=0,Marker=1,Index=2】|KLineType|KLineType|
|realTrustPrice|Actual Entrusted price|number(decimal)|number(decimal)|
|lastUpdateTime|Last operation time|string(date-time)|string(date-time)|
|clientId|Customized by customerSingle No.|string||
|orderId|Trigger Generate Single No.|string||
|symbol|Symbol Name|string||


**Response Example**:
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


## Stop profit Stop Loss Entrusted Orders Cancellation 


**url**:`/api/v1/cancelKillOrFillOrder`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|Symbol Name|query|false|string||
|OrderId|Ordersid|query|false|string||
|ClientOrderId|client Orders id|query|false|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200|||


**Response Params**:


None


**Response Example**:
```javascript

```


## Get current Entrusted Stop profit Stop Loss Order


**url**:`/api/v1/getActiveKillOrFillOrders`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|Symbol Name|query|false|string||
|Side|Open long position=0,Open short position=1,Close short position=2,Close long position=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|Available values:0,1,2,3||false|integer||
|PageIndex|Current page number|query|false|integer(int32)||
|PageSize|Number of lines per page|query|false|integer(int32)||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||pageResultOfFillOrKillOrderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|success|Success or failure|boolean||
|errorCode|Error Code|integer(int32)|integer(int32)|
|msg|Return Message|string||
|total|Total number of records|integer(int32)|integer(int32)|
|data|Stop profit Stop Loss  Order List|FillOrKillOrderDTO|FillOrKillOrderDTO|


**Response Example**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## Get HistoryEntrusted Stop profit Stop Loss  Order


**url**:`/api/v1/getHistoryKillOrFillOrders`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|Symbol Name|query|false|string||
|Side|Open long position=0,Open short position=1,Close short position=2,Close long position=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|Available values:0,1,2,3||false|integer||
|PageIndex|Current page number|query|false|integer(int32)||
|PageSize|Number of lines per page|query|false|integer(int32)||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||pageResultOfFillOrKillOrderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|success|Success or failure|boolean||
|errorCode|Error Code|integer(int32)|integer(int32)|
|msg|Return Message|string||
|total|Total number of records|integer(int32)|integer(int32)|
|data|Stop profit Stop Loss  Order List|FillOrKillOrderDTO|FillOrKillOrderDTO|


**Response Example**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## Get Stop profit Stop Loss  Order


**url**:`/api/v1/getKillOrFillOrder`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|orderId||query|false|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||fillOrKillOrderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|Single No.|string||
|createTime|Entrusted time|string(date-time)|string(date-time)|
|contractId|futures Id|string||
|customerId|Customer Id|string||
|multiple|Leverage multiplier|number(decimal)|number(decimal)|
|status|Status【Stop Loss OrderStatus:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3】|FillOrKillOrderStatus|FillOrKillOrderStatus|
|side| Direction【Stop Loss Order Direction:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3】|FillOrKillOrderSide|FillOrKillOrderSide|
|tradeSide|Transaction Type 0=open long 1=open short 2flat=short 3=flat long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】|ContractTradeSide|ContractTradeSide|
|marginMode|Margin mode [Full margin mode=0,Position by position margin mode=1]|MarginMode|MarginMode|
|fillTriggerPrice|Stop profit Trigger price|number(decimal)|number(decimal)|
|fillTrustPrice|Stop profit Entrusted price Empty for market price|number(decimal)|number(decimal)|
|killTriggerPrice|Stop Loss Trigger price|number(decimal)|number(decimal)|
|killTrustPrice|Stop Loss Entrusted price Empty for market price|number(decimal)|number(decimal)|
|trustQty|Entrusted Quantity|number(decimal)|number(decimal)|
|realTrustQty|Actual Entrusted Quantity|number(decimal)|number(decimal)|
|cumQty|Entrusted volume |number(decimal)|number(decimal)|
|triggerDirection|Trigger  Direction【Trigger  Direction:止赢=0,Stop Loss =1】|FillOrKillTriggerDirection|FillOrKillTriggerDirection|
|triggerPriceKind|Trigger price Category【K-line price Source Type:Market=0,Marker=1,Index=2】|KLineType|KLineType|
|realTrustPrice|Actual Entrusted price|number(decimal)|number(decimal)|
|lastUpdateTime|Last operation time|string(date-time)|string(date-time)|
|clientId|Customized by customerSingle No.|string||
|orderId|Trigger Generate Single No.|string||
|symbol|Symbol Name|string||


**Response Example**:
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


## Plan Entrusted  Order Open


**url**:`/api/v1/openPlanOrder`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|Symbol Name|query|false|string||
|ClientId|Customization Single No.|query|false|string||
|TrustPrice|Entrusted price Empty for market price\n |query|false|number(decimal)||
|TriggerPrice|Trigger price|query|false|number(decimal)||
|TrustQty|Entrusted Quantity|query|false|number(decimal)||
|Side|Open long position=0,Open short position=1,Close short position=2,Close long position=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|Available values:0,1,2,3||false|integer||
|TriggerPriceKind|K-line price Source Type:Market=0,Marker=1,Index=2|query|false|kLineType|kLineType|
|&emsp;&emsp;undefined|Available values:0,1,2||false|integer||
|UnitMode|Trading unit mode: cont=0,coin=1|query|false|tradingUnitMode|tradingUnitMode|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|marginMode|Full margin mode=0,Position by position margin mode=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||planOrderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|Single No.|string||
|createTime|Entrusted time|string(date-time)|string(date-time)|
|contractId|futures Id|string||
|customerId|Customer Id|string||
|lastUpdateTime|Last operation time|string(date-time)|string(date-time)|
|multiple|Leverage multiplier|number(decimal)|number(decimal)|
|status|Status【Plan orderStatus:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3】|PlanOrderStatus|PlanOrderStatus|
|tradeSide|Transaction Type 0=open long 1=open short 2flat=short 3=flat long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】|ContractTradeSide|ContractTradeSide|
|marginMode|Margin mode [Full margin mode=0,Position by position margin mode=1]|MarginMode|MarginMode|
|triggerPrice|Trigger price|number(decimal)|number(decimal)|
|trustPrice|Entrusted price Empty for market price\n |number(decimal)|number(decimal)|
|trustQty|Entrusted Quantity|number(decimal)|number(decimal)|
|realTrustQty|Actual Entrusted Quantity|number(decimal)|number(decimal)|
|triggerPriceKind|Trigger price Category【K-line price Source Type:Market=0,Marker=1,Index=2】|KLineType|KLineType|
|realTrustPrice|Actual Entrusted price|number(decimal)|number(decimal)|
|clientId|Customized by customerSingle No.|string||
|orderId|Trigger Generate Single No.|string||
|symbol|Symbol Name|string||


**Response Example**:
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


## Plan Entrusted order closing


**url**:`/api/v1/closePlanOrder`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|Symbol Name|query|false|string||
|ClientId|Customization Single No.|query|false|string||
|TrustPrice|Entrusted price Empty for market price\n |query|false|number(decimal)||
|TriggerPrice|Trigger price|query|false|number(decimal)||
|TrustQty|Entrusted Quantity|query|false|number(decimal)||
|Side|Open long position=0,Open short position=1,Close short position=2,Close long position=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|Available values:0,1,2,3||false|integer||
|TriggerPriceKind|K-line price Source Type:Market=0,Marker=1,Index=2|query|false|kLineType|kLineType|
|&emsp;&emsp;undefined|Available values:0,1,2||false|integer||
|UnitMode|Trading unit mode: cont=0,coin=1|query|false|tradingUnitMode|tradingUnitMode|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|marginMode|Full margin mode=0,Position by position margin mode=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||planOrderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|Single No.|string||
|createTime|Entrusted time|string(date-time)|string(date-time)|
|contractId|futures Id|string||
|customerId|Customer Id|string||
|lastUpdateTime|Last operation time|string(date-time)|string(date-time)|
|multiple|Leverage multiplier|number(decimal)|number(decimal)|
|status|Status【Plan orderStatus:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3】|PlanOrderStatus|PlanOrderStatus|
|tradeSide|Transaction Type 0=open long 1=open short 2flat=short 3=flat long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】|ContractTradeSide|ContractTradeSide|
|marginMode|Margin mode [Full margin mode=0,Position by position margin mode=1]|MarginMode|MarginMode|
|triggerPrice|Trigger price|number(decimal)|number(decimal)|
|trustPrice|Entrusted price Empty for market price\n |number(decimal)|number(decimal)|
|trustQty|Entrusted Quantity|number(decimal)|number(decimal)|
|realTrustQty|Actual Entrusted Quantity|number(decimal)|number(decimal)|
|triggerPriceKind|Trigger price Category【K-line price Source Type:Market=0,Marker=1,Index=2】|KLineType|KLineType|
|realTrustPrice|Actual Entrusted price|number(decimal)|number(decimal)|
|clientId|Customized by customerSingle No.|string||
|orderId|Trigger Generate Single No.|string||
|symbol|Symbol Name|string||


**Response Example**:
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


## Plan Entrusted Orders Cancellation 


**url**:`/api/v1/cancelPlanOrder`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|Symbol Name|query|false|string||
|OrderId|Ordersid|query|false|string||
|ClientOrderId|客户Ordersid|query|false|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200|||


**Response Params**:


None


**Response Example**:
```javascript

```


## Get current Entrusted  plan Entrusted  Order


**url**:`/api/v1/getPlanOrders`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|Symbol Name|query|false|string||
|Side|Open long position=0,Open short position=1,Close short position=2,Close long position=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|Available values:0,1,2,3||false|integer||
|PageIndex|Current page number|query|false|integer(int32)||
|PageSize|Number of lines per page|query|false|integer(int32)||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||pageResultOfPlanOrderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|success|Success or failure|boolean||
|errorCode|Error Code|integer(int32)|integer(int32)|
|msg|Return Message|string||
|total|Total number of records|integer(int32)|integer(int32)|
|data|Plan order  List|PlanOrderDTO|PlanOrderDTO|


**Response Example**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## Get HistoryEntrusted  plan Entrusted  Order


**url**:`/api/v1/getHistoryPlanOrders`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Symbol|Symbol Name|query|false|string||
|Side|Open long position=0,Open short position=1,Close short position=2,Close long position=3|query|false|contractTradeSide|contractTradeSide|
|&emsp;&emsp;undefined|Available values:0,1,2,3||false|integer||
|PageIndex|Current page number|query|false|integer(int32)||
|PageSize|Number of lines per page|query|false|integer(int32)||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||pageResultOfPlanOrderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|success|Success or failure|boolean||
|errorCode|Error Code|integer(int32)|integer(int32)|
|msg|Return Message|string||
|total|Total number of records|integer(int32)|integer(int32)|
|data|Plan order List|PlanOrderDTO|PlanOrderDTO|


**Response Example**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## Get Plan Entrusted  Order


**url**:`/api/v1/getPlanOrder`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|orderId||query|false|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||planOrderDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|Single No.|string||
|createTime|Entrusted time|string(date-time)|string(date-time)|
|contractId|futures Id|string||
|customerId|Customer Id|string||
|lastUpdateTime|Last operation time|string(date-time)|string(date-time)|
|multiple|Leverage multiplier|number(decimal)|number(decimal)|
|status|Status【Plan orderStatus:Pending=0,Withdrawn=1,Effective=2,Trigger failure=3】|PlanOrderStatus|PlanOrderStatus|
|tradeSide|Transaction Type 0=open long 1=open short 2flat=short 3=flat long【Open long position=0,Open short position=1,Close short position=2,Close long position=3】|ContractTradeSide|ContractTradeSide|
|marginMode|Margin mode [Full margin mode=0,Position by position margin mode=1]|MarginMode|MarginMode|
|triggerPrice|Trigger price|number(decimal)|number(decimal)|
|trustPrice|Entrusted price Empty for market price\n |number(decimal)|number(decimal)|
|trustQty|Entrusted Quantity|number(decimal)|number(decimal)|
|realTrustQty|Actual Entrusted Quantity|number(decimal)|number(decimal)|
|triggerPriceKind|Trigger price Category【K-line price Source Type:Market=0,Marker=1,Index=2】|KLineType|KLineType|
|realTrustPrice|Actual Entrusted price|number(decimal)|number(decimal)|
|clientId|Customized by customerSingle No.|string||
|orderId|Trigger Generate Single No.|string||
|symbol|Symbol Name|string||


**Response Example**:
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


## Get K-line  Data


**url**:`/api/v1/candles`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|Symbol| Symbols |query|false|string||
|Interval|Per minute = 100,5 minutes = 101,15 minutes = 102,30 minutes = 103,Hourly = 200,2 hours = 201,4 hours = 202,8 hours = 203,Daily = 300,Weekly = 400,Monthly = 500|query|false|candleInterval|candleInterval|
|&emsp;&emsp;undefined|Available values:100,101,102,103,200,201,202,203,300,400,500||false|integer||
|StartTime|Start time|query|false|integer(int64)||
|kLineType|K-line price Source Type:Market=0,Marker=1,Index=2|query|false|kLineType|kLineType|
|&emsp;&emsp;undefined|Available values:0,1,2||false|integer||
|EndTime|Ending time|query|false|integer(int64)||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||candleDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|kLineType|K-line  Type 【K-line price Source Type:Market=0,Marker=1,Index=2】|KLineType|KLineType|
|interval|Candle interval【Per minute = 100,5 minutes = 101,15 minutes = 102,30 minutes = 103,Hourly = 200,2 hours = 201,4 hours = 202,8 hours = 203,Daily = 300,Weekly = 400,Monthly = 500】|CandleInterval|CandleInterval|
|close|Closed Price|number(decimal)|number(decimal)|
|high|Highest Price|number(decimal)|number(decimal)|
|low|Lowest Price|number(decimal)|number(decimal)|
|open|Opening Price|number(decimal)|number(decimal)|
|volume|Size|number(decimal)|number(decimal)|
|timestamp|timestamp|integer(int64)|integer(int64)|
|dateTime|time|string(date-time)|string(date-time)|


**Response Example**:
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


##  Get the latest quotes of the futures species according to the futures ID


**url**:`/api/v1/realTimeHandicap`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|contractId|futures Id|query|false|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||realTimeHandicapFullDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|contractId|futures Variety Id|string||
|symbol|symbol|string||
|createTime||string(date-time)|string(date-time)|
|timestamp||integer(int64)|integer(int64)|
|firstBid|First buying price|number(decimal)|number(decimal)|
|firstAsk|First selling price|number(decimal)|number(decimal)|
|marketPrice|Latest Market Price|number(decimal)|number(decimal)|
|triggerType|Internal and external trading [Trigger Type :Internal=1,External=2]|TriggerType|TriggerType|
|sort|Serial No.|integer(int64)|integer(int64)|
|changeAmount24H|24 hours up or down amount|number(decimal)|number(decimal)|
|changeRate24H|24 hours up or down|number(decimal)|number(decimal)|
|high24H|24-hour maximum price|number(decimal)|number(decimal)|
|low24H|24 Hour Lowest Price|number(decimal)|number(decimal)|
|volume24H|24 Hour Volume|number(decimal)|number(decimal)|
|turnover24H|24 Hour Turnover|number(decimal)|number(decimal)|
|markPrice|Latest marker price|number(decimal)|number(decimal)|
|indexPrice|Latest Index Price|number(decimal)|number(decimal)|
|distanceSettlementTime|Time until fee settlement|string(time-span)|string(time-span)|
|currentFundRate|Current funding rate|number(decimal)|number(decimal)|
|forecastFundRate|Projected funding rates|number(decimal)|number(decimal)|


**Response Example**:
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


## Get realtime Handicap 


**url**:`/api/v1/realTimeHandicapFull`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


None


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||realTimeHandicapFullDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|contractId|futures Variety Id|string||
|symbol|symbol|string||
|createTime||string(date-time)|string(date-time)|
|timestamp||integer(int64)|integer(int64)|
|firstBid|First buying price|number(decimal)|number(decimal)|
|firstAsk|First selling price|number(decimal)|number(decimal)|
|marketPrice|Latest Market Price|number(decimal)|number(decimal)|
|triggerType|Internal and external trading [Trigger Type :Internal=1,External=2]|TriggerType|TriggerType|
|sort|Serial No.|integer(int64)|integer(int64)|
|changeAmount24H|24 hours up or down amount|number(decimal)|number(decimal)|
|changeRate24H|24 hours up or down|number(decimal)|number(decimal)|
|high24H|24-hour maximum price|number(decimal)|number(decimal)|
|low24H|24 Hour Lowest Price|number(decimal)|number(decimal)|
|volume24H|24 Hour Volume|number(decimal)|number(decimal)|
|turnover24H|24 Hour Turnover|number(decimal)|number(decimal)|
|markPrice|Latest marker price|number(decimal)|number(decimal)|
|indexPrice|Latest Index Price|number(decimal)|number(decimal)|
|distanceSettlementTime|Time until fee settlement|string(time-span)|string(time-span)|
|currentFundRate|Current funding rate|number(decimal)|number(decimal)|
|forecastFundRate|Projected funding rates|number(decimal)|number(decimal)|


**Response Example**:
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


## Get depth


**url**:`/api/v1/depth`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|contractId|futures Variety Id|query|false|string||
|tickSize|Precision|query|false|number(decimal)||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||orderBookDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|contractId|futures Id|string||
|bids|Buy order  price Quantity|array|array|
|asks|sell order price Quantity|array|array|


**Response Example**:
```javascript
{
	"contractId": "",
	"bids": [],
	"asks": []
}
```


## Get Latest deals


**url**:`/api/v1/recentTrades`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|contractId|futures Variety Id|query|false|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||ticketDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|price|price|number(decimal)|number(decimal)|
|qty|Quantity|number(decimal)|number(decimal)|
|triggerType|Internal and external trading [Trigger Type :Internal=1,External=2]|TriggerType|TriggerType|
|timeStamp|time|integer(int64)|integer(int64)|


**Response Example**:
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


## Real-time funding rates


**url**:`/api/v1/getRealFundingRateList`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


None


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||fundingRateReal|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|contractId|Contractid|string||
|predictionRate|Projected funding rates|number(decimal)|number(decimal)|
|rate|Current funding rate|number(decimal)|number(decimal)|
|contractName|futures name|string||
|createTimeOffset|Create Timestamp|integer(int64)|integer(int64)|


**Response Example**:
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


## Historical funding rates


**url**:`/api/v1/getHistoryFundingRateList`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|ContractId|Coin Name|query|false|string||
|PageIndex|Current page number|query|false|integer(int32)||
|PageRows|Number of lines per page|query|false|integer(int32)||
|SortField|Serialization|query|false|string||
|SortType|Serialization Type |query|false|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||pageResultOfFundingRateView|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|success|Success or failure|boolean||
|errorCode|Error Code|integer(int32)|integer(int32)|
|msg|Return Message|string||
|total|Total number of records|integer(int32)|integer(int32)|
|data|Funding rates List|FundingRateView|FundingRateView|


**Response Example**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## Get Platform Status


**url**:`/api/v1/getPlatformStatus`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


None


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||platformStatus|


**Response Params**:


None


**Response Example**:
```javascript
null
```


## Get Position Stalls List


**url**:`/api/v1/getPositionGearList`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|ContractId|futures Id|query|false|string||
|PageIndex|Current page number|query|false|integer(int32)||
|PageRows|Number of lines per page|query|false|integer(int32)||
|SortField|Serialization|query|false|string||
|SortType|Serialization Type |query|false|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||pageResultOfPositionGear|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|success|Success or failure|boolean||
|errorCode|Error Code|integer(int32)|integer(int32)|
|msg|Return Message|string||
|total|Total number of records|integer(int32)|integer(int32)|
|data|Position Stalls List|PositionGear|PositionGear|


**Response Example**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## Get Gear Detail


**url**:`/api/v1/getPositionGearDetail`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|symbol|futures symbol|query|false|string||
|level|Leverage|query|false|number(decimal)||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||positionGear|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|Id|string||
|createTime|CreateTime|string(date-time)|string(date-time)|
|creatorId|CreatorId|string||
|deleted|Deleted|boolean||
|gear|Position Blocking|integer(int32)|integer(int32)|
|maxVolumn|max Volumn|integer(int32)|integer(int32)|
|minVolumn|min Volumn|integer(int32)|integer(int32)|
|keepMargin|keep Margin|number(decimal)|number(decimal)|
|minInitialMargin|minInitial Margin Rate|number(decimal)|number(decimal)|
|maxUseLeverage|max Use Leverage|number(decimal)|number(decimal)|
|contractId|futures Id|string||


**Response Example**:
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


## Get Coin List


**url**:`/api/v1/getCoins`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


None


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||coinDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|CoinId|string||
|code|Coin code |string||
|openConvertRate|Open Position Conversion Rate|number(decimal)|number(decimal)|
|holdConvertRate|Position Conversion Rate|number(decimal)|number(decimal)|
|icon| Icons |string||
|unitPrecision| Bit Accuracy |integer(int32)|integer(int32)|


**Response Example**:
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


## Get Supported futures


**url**:`/api/v1/getContracts`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


None


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||contractDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|futures Id|string||
|name|futures name|string||
|priceIncrement|Minimum price Increment|number(decimal)|number(decimal)|
|sizeIncrement|sizeIncrement|number(decimal)|number(decimal)|
|positionLimitWeight|position Limit Weight|number(decimal)|number(decimal)|
|level|Leverage multiplier|number(decimal)|number(decimal)|
|tickSize|tick Size|array||
|faceValue|face Value|number(decimal)|number(decimal)|
|minChangeUnit|min Change Unit|number(decimal)|number(decimal)|
|positionModel|Positioning Model |array|MarginMode|
|icon| Icons |string||
|predictionRate|Projected funding rates|number(decimal)|number(decimal)|
|theRate|Current funding rate|number(decimal)|number(decimal)|
|underlying|Coin|string||
|riskReserverAmount|risk Reserver |number(decimal)|number(decimal)|


**Response Example**:
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


## Transfer of assets


**url**:`/api/v1/transferAssets`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|coinId|CoinID|query|false|string||
|amount|Quantity|query|false|number(decimal)||
|side|From futures to spot=0,From spot to futures=1,From futures to fiat=2,From fiat to futures=3|query|false|transferDirection|transferDirection|
|&emsp;&emsp;undefined|Available values:0,1,2,3||false|integer||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200|||


**Response Params**:


None


**Response Example**:
```javascript

```


## Get the number of coins available to users on the futures platform


**url**:`/api/v1/getAvailableQuantity`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|coinId|CoinId|query|false|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200|||


**Response Params**:


None


**Response Example**:
```javascript

```


## Get the number of coins available on third-party platforms


**url**:`/api/v1/getThirdPartyAvailableQuantity`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|coinId|CoinId|query|false|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200|||


**Response Params**:


None


**Response Example**:
```javascript

```


## Transfer of assets Records


**url**:`/api/v1/getAssetTransferRecords`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|Direction|From futures to spot=0,From spot to futures=1,From futures to fiat=2,From fiat to futures=3|query|false|transferDirection|transferDirection|
|&emsp;&emsp;undefined|Available values:0,1,2,3||false|integer||
|Coin|Coin|query|false|string||
|PageIndex|Current page number|query|false|integer(int32)||
|PageSize|Number of lines per page|query|false|integer(int32)||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||pageResultOfAssetTransferRecordDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|success|Success or failure|boolean||
|errorCode|Error Code|integer(int32)|integer(int32)|
|msg|Return Message|string||
|total|Total number of records|integer(int32)|integer(int32)|
|data|Transfer records List|AssetTransferRecordDTO|AssetTransferRecordDTO|


**Response Example**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## Get Customer Asset Information


**url**:`/api/v1/getAsset`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||assetsDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|totalOpenEquities|Joint Margin Conversion - Open Position Conversion USDT|number(decimal)|number(decimal)|
|totalHoldEquities|Discounted equity - position discounted USDT|number(decimal)|number(decimal)|
|unrealizedPNL|Unrealized profit and loss|number(decimal)|number(decimal)|
|frozen|Occupancy|number(decimal)|number(decimal)|
|available|Available|number(decimal)|number(decimal)|
|actuallyAvailable|Actual Available|number(decimal)|number(decimal)|
|crossMarginRate|Full position margin rate|number(decimal)|number(decimal)|
|detail|Coin Asset Details|array|AssetsItemDTO|
|maximumOpenPositions|Maximum open positions for contract varieties Quantity|array|MaximumOpenPositionItem|


**Response Example**:
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


## Get My Positions


**url**:`/api/v1/getMyPositions`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||PositionDTO|


**Response Params**:


None


**Response Example**:
```javascript

```


## Get billing details


**url**:`/api/v1/getBillingRecords`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|CoinId|Coin|query|false|string||
|billType|Billing Type:Currency Exchange=1,Transfer=2,Trade=3,Close=4,Reduce Position=5,Interest=6,Funding Fee=7|query|false|billType|billType|
|&emsp;&emsp;undefined|Available values:1,2,3,4,5,6,7||false|integer||
|pageResultOfBillingRecordView|Billing transaction type: buy open long=1,sell close long=2,sell open short=3,buy close short=4,force close long=5,force close short=6,change currency transfer=7,change currency transfer=8,coin to contract=9,contract to coin=10,fund fee expense=11,fund fee income=12,force close long=13,force close short=14,auto close long =15,automatic position closing short=16,interest expense=17,position penetration compensation=18,fiat to futures =20,futures to fiat=21
|query|false|billTradeType|billTradeType|
|&emsp;&emsp;undefined|Available values:1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21||false|integer||
|PageIndex|Current page number|query|false|integer(int32)||
|PageSize|Number of lines per page|query|false|integer(int32)||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||pageResultOfbillingTrade|


**Response Params**:


None


**Response Example**:
```javascript

```


## Get Billing Records


**url**:`/api/v1/getpcBillingRecords`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|CoinId|CoinId|query|false|string||
|BillType|Billing Type:Currency Exchange=1,Transfer=2,Trade=3,Close=4,Reduce Position=5,Interest=6,Funding Fee=7|query|false|BillType|BillType|
|billTradeType|Billing transaction type: buy open long=1,sell close long=2,sell open short=3,buy close short=4,force close long=5,force close short=6,change currency transfer=7,change currency transfer=8,coin to contract=9,contract to coin=10,fund fee expense=11,fund fee income=12,force close long=13,force close short=14,auto close long =15,automatic position closing short=16,interest expense=17,position penetration compensation=18,fiat to futures =20,futures to fiat=21
|query|false|billTradeType|billTradeType|
|&emsp;&emsp;undefined|Available values:1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21||false|integer||
|ContractId|futures Id|query|false|string||
|StartTime|Query start time|query|false|string(date-time)||
|EndTime|Query end time|query|false|string(date-time)||
|PageIndex|Current page number|query|false|integer(int32)||
|PageRows|Number of lines per page|query|false|integer(int32)||
|SortField|Serialization|query|false|string||
|SortType|Serialization Type |query|false|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||pageResultOfBillingRecordView|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|success|Success or failure|boolean||
|errorCode|Error Code|integer(int32)|integer(int32)|
|msg|Return Message|string||
|total|Total number of records|integer(int32)|integer(int32)|
|data|Billing Records List|BillingRecordView|BillingRecordView|


**Response Example**:
```javascript
{
	"success": true,
	"errorCode": 0,
	"msg": "",
	"total": 0,
	"data": ""
}
```


## Get Specify contract user configuration


**url**:`/api/v1/getContractCustomerSetting`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|contractId|futures Id|query|false|string||
|marginMode|Full margin mode=0,Position by position margin mode=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||contractCustomerSettings|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|Primary Key|string||
|createTime|Creation time|string(date-time)|string(date-time)|
|contractId|futures Id|string||
|customerId|Customer Id|string||
|marginMode|Margin mode [Full margin mode=0,Position by position margin mode=1]|MarginMode|MarginMode|
|leverage|Leverage multiplier|number(decimal)|number(decimal)|
|side|Long/short direction【Long/short direction:Long=0,short=1】|ContractSide|ContractSide|
|isDefault|Default or not|boolean||


**Response Example**:
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


## Get Default contract position mode configuration


**url**:`/api/v1/getDefaultContractCustomerSetting`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|contractId|futures Id|query|false|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||contractCustomerSettings|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|id|Primary Key|string||
|createTime|Creation time|string(date-time)|string(date-time)|
|contractId|futures Id|string||
|customerId|Customer Id|string||
|marginMode|Margin mode [Full margin mode=0,Position by position margin mode=1]|MarginMode|MarginMode|
|leverage|Leverage multiplier|number(decimal)|number(decimal)|
|side|Long/short direction【Long/short direction:Long=0,short=1】|ContractSide|ContractSide|
|isDefault|Default or not|boolean||


**Response Example**:
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


## Set default margin mode


**url**:`/api/v1/setDefaultmarginMode`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|contractId|futures Id|query|false|string||
|marginMode|Full margin mode=0,Position by position margin mode=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200|||


**Response Params**:


None


**Response Example**:
```javascript

```


## set leverage multiplier


**url**:`/api/v1/setLeverage`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|contractId|futures Id|query|false|string||
|marginMode|Full margin mode=0,Position by position margin mode=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|side|Long/short direction:Long=0,short=1|query|false|contractSide|contractSide|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|leverage|Leverage multiplier|query|false|number(decimal)||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200|||


**Response Params**:


None


**Response Example**:
```javascript

```


## Get Position-by-position margin


**url**:`/api/v1/getIsolatedMargin`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|contractId||query|false|string||
|side|Long/short direction:Long=0,short=1|query|false|contractSide|contractSide|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||positionAssetDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|coin|Coin|string||
|quantity|Quantity|number(decimal)|number(decimal)|
|icon|Coin Icons |string||


**Response Example**:
```javascript
[
	{
		"coin": "",
		"quantity": 0,
		"icon": ""
	}
]
```


## Position-by-position margin Adjustment


**url**:`/api/v1/adjustIsolatedMargin`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|contractId|futures Id|query|false|string||
|side|Long/short direction:Long=0,short=1|query|false|contractSide|contractSide|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|adjustModel|Adjustment parameters Type :Quantity=0,Proportion=1|query|false|adjustModel|adjustModel|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|amount|Margin call/reduction|query|false|number(decimal)||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200|||


**Response Params**:


None


**Response Example**:
```javascript

```


## Assessment of additional margin


**url**:`/api/v1/estimateCallMargin`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|contractId|futures Id|query|false|string||
|side|Long/short direction:Long=0,short=1|query|false|contractSide|contractSide|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|adjustModel|Adjustment parameters Type :Quantity=0,Proportion=1|query|false|adjustModel|adjustModel|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|amount|Assessment Quantity|query|false|number(decimal)||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||estimateIsolatedMarginDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|maximum|Maximum operation Quantity|number(decimal)|number(decimal)|
|leverage| Leverage |number(decimal)|number(decimal)|
|liquidationPrice|Forced Closeout Orders price|number(decimal)|number(decimal)|


**Response Example**:
```javascript
{
	"maximum": 0,
	"leverage": 0,
	"liquidationPrice": 0
}
```


## Assessment of margin reduction


**url**:`/api/v1/estimateReduceMargin`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|contractId|futures Id|query|false|string||
|side|Long/short direction:Long=0,short=1|query|false|contractSide|contractSide|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|adjustModel|Adjustment parameters Type :Quantity=0,比例=1|query|false|adjustModel|adjustModel|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|amount|Assessment Quantity|query|false|number(decimal)||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||estimateIsolatedMarginDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|maximum|Maximum operation Quantity|number(decimal)|number(decimal)|
|leverage|Leverage |number(decimal)|number(decimal)|
|liquidationPrice|Forced Closeout Order price|number(decimal)|number(decimal)|


**Response Example**:
```javascript
{
	"maximum": 0,
	"leverage": 0,
	"liquidationPrice": 0
}
```


## Assessment Adjusting contract leverage


**url**:`/api/v1/estimateAdjustLeverage`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||
|contractId|futures Id|query|false|string||
|marginMode|Full margin mode=0,Position by position margin mode=1|query|false|marginMode|marginMode|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|side|Long/short direction:Long=0,short=1|query|false|contractSide|contractSide|
|&emsp;&emsp;undefined|Available values:0,1||false|integer||
|leverage|Leverage multiplier|query|false|number(decimal)||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||estimateAdjustLeverageDTO|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|maximumOpenCont| maximum Open Cont |integer(int64)|integer(int64)|
|maximumOpenQty|maximum Open Qty|number(decimal)|number(decimal)|
|requiredMargin|required Margin|number(decimal)|number(decimal)|
|estimatedLiquidationPrice|estimated Forced Closeout Order price|number(decimal)|number(decimal)|
|qtyOfMarginChange|Margin Change Quantity|number(decimal)|number(decimal)|
|maximumHoldCont|maximum Hold Cont|integer(int64)|integer(int64)|


**Response Example**:
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


## Get My Handling fee


**url**:`/api/v1/getMyHandlingFee`


**method**:`POST`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`*/*`


**Note**:


**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|X-APIKEY|apikey|header|true|||
|X-TIMESTAMP|timestamp|header|true|||
|X-SIGNATURE|signature|header|true|||
|X-RECVWINDOW|recvwindow|header|false|||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200||valueTupleOfDecimalAndDecimal|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|item1||number(decimal)|number(decimal)|
|item2||number(decimal)|number(decimal)|


**Response Example**:
```javascript
{
	"item1": 0,
	"item2": 0
}
```
