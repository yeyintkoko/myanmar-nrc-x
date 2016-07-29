Myanmar National Registration Card Format Prefix
================================================

Myanmar NRC Format [State Number]\[District]([NAING])[Register No] using Unicode. Fixed all bug, pretty fine and ready to use with myanmar unicode.

*Note*

This is a modified version of https://github.com/greenlikeorange/NRCPrefix


## Usage
```js
var mnrc = require('myanmar-nrc-x')
try{
	var nrc = mnrc("၁၂/ဥကမ(န)၀၂၃၄၅၆")
}catch(error){
	console.log(error.message)
}
```


### Example

```js
var MMNRC = require('myanmar-nrc-x')

function checknrc(nrcno){
	var validity = false;
	try{
		var nrc = MMNRC(nrcno);
		console.log(MMNRC.toMyaNum(12)) //၁၂
		console.log(MMNRC.toEngNum('၁၂')) //12
		console.log(nrc.getFormat()) // 12/OUKAMA(N)123456
		console.log(nrc.getFormat("mm")) // ၁၂/ဥကမ(နိုင်)၁၂၃၄၅၆
		console.log(nrc.getState()) // Yangon
		console.log(nrc.getState("mm")) // ရန်ကုန်တိုင်း
		validity = true;

	}catch(e){
	 console.log(e.message);
	 validity = false;
	}

	return validity;
}


if(checknrc("၁၂/ဥကမ(န)၀၂၃၄၅၆")) console.log('myanmar nrc format is valid')
```
