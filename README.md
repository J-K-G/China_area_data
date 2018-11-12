# China_area_data
中国省市区数据（含港澳台）

# 前端数据格式

```json
[{
  "value": "110000",
  "label": "北京市",
  "children": [{
    "value": "110100",
    "label": "市辖区",
    "provinceCode": "110000",
    "children": [{
      "value": "110101",
      "label": "东城区",
      "cityCode": "110100",
      "provinceCode": "110000"
    }]
  }]
}]
```

# 省份数据格式

```json
[{
	"value": "11",
	"label": "北京市"
}]
```

# 市数据格式

```json
[{
	"value": "1101",
	"label": "市辖区",
	"provinceCode": "11"
}]
```

# 区数据格式

```json
[{
	"value": "110101",
	"label": "东城区",
	"cityCode": "1101",
	"provinceCode": "11"
}]
```

# 数据格式化为前端用的数据

```js
    const finalList = provinces.map(provinceItem => {
      const cityArr = cities.filter(cityItem => cityItem.provinceCode === provinceItem.value);
      const provinceChildren = cityArr.map(ca => {
        const districtArr = districts.filter(districtItem => districtItem.cityCode === ca.value);
        const cityChildren = districtArr.map(dis => {
          return {
            ...dis,
            value: dis.value,
            cityCode: `${dis.cityCode}00`,
            provinceCode: `${dis.provinceCode}0000`,
          };
        });

        return {
          ...ca,
          value: `${ca.value}00`,
          provinceCode: `${ca.provinceCode}0000`,
          children: cityChildren,
        };
      });

      return {
        ...provinceItem,
        value: `${provinceItem.value}0000`,
        children: provinceChildren,
      };
    });
```

# 港澳台数据

```json
[{
  "value": "710000",
  "label": "台湾省",
  "children": [{
    "value": "710000",
    "label": "台湾",
    "provinceCode": "710000",
    "children": [{
      "value": "710101",
      "label": "金门",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710102",
      "label": "连江",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710103",
      "label": "苗栗",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710104",
      "label": "南投",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710105",
      "label": "澎湖",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710106",
      "label": "屏东",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710107",
      "label": "台东",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710108",
      "label": "台中",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710109",
      "label": "台南",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710110",
      "label": "台北",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710111",
      "label": "桃园",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710112",
      "label": "云林",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710113",
      "label": "新北",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710114",
      "label": "彰化",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710115",
      "label": "嘉义",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710116",
      "label": "新竹",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710117",
      "label": "花莲",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710118",
      "label": "宜兰",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710119",
      "label": "高雄",
      "cityCode": "710000",
      "provinceCode": "710000"
    },{
      "value": "710120",
      "label": "基隆",
      "cityCode": "710000",
      "provinceCode": "710000"
    }]
  }]
}, {
  "value": "910000",
  "label": "港澳",
  "children": [{
    "value": "810000",
    "label": "香港特别行政区",
    "provinceCode": "910000",
    "children": [{
      "value": "810101",
      "label": "中西区",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810102",
      "label": "东区",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810103",
      "label": "九龙城区",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810104",
      "label": "观塘区",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810105",
      "label": "深水埗区",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810106",
      "label": "湾仔区",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810107",
      "label": "黄大仙区",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810108",
      "label": "油尖旺区",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810109",
      "label": "离岛区",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810110",
      "label": "葵青区",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810111",
      "label": "北区",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810112",
      "label": "西贡区",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810113",
      "label": "沙田区",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810114",
      "label": "屯门区",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810115",
      "label": "大埔区",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810116",
      "label": "荃湾区",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810117",
      "label": "元朗区",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810118",
      "label": "香港",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810119",
      "label": "九龙",
      "cityCode": "810000",
      "provinceCode": "910000"
    },{
      "value": "810120",
      "label": "新界",
      "cityCode": "810000",
      "provinceCode": "910000"
    }]
  }, {
    "value": "820000",
    "label": "澳门特别行政区",
    "provinceCode": "910000",
    "children": [{
      "value": "820101",
      "label": "离岛",
      "cityCode": "820000",
      "provinceCode": "910000"
    },{
      "value": "820102",
      "label": "澳门半岛",
      "cityCode": "820000",
      "provinceCode": "910000"
    },{
      "value": "820103",
      "label": "凼仔",
      "cityCode": "820000",
      "provinceCode": "910000"
    },{
      "value": "820104",
      "label": "路凼城",
      "cityCode": "820000",
      "provinceCode": "910000"
    },{
      "value": "820105",
      "label": "路环",
      "cityCode": "820000",
      "provinceCode": "910000"
    }]
  }]
}]
```
