# A+office-SPA-WebApp

> 本页面需要在服务器环境下通过域名访问,勿直接浏览静态页面

### 使用技术:
| 技术名称                                           | 作用           |  版本  |
| --------                                          | -----:         | :----:  |
| Vuejs                                             | 框架            |   2.1.10     |
| Vuex                                              | 状态管理        |   2.1.1   |
| Vue-router                                        | 路由管理        |  2.1.3  |
| Axios                                             | 交互处理        |  0.15.3  |
| Sass (node-sass)                                  | 样式预处理器     |  4.1.1  |
| Webpack                                           | 模块打包         |  1.13.2  |
| Gulp                                              | 自动构建工具     |  3.9.1  |
| Babel                                             | ES6转译ES5      |  6.0.0  |
| Yarn                                              | 模块依赖安装     |  0.17.6  |
| [Muse UI](https://museui.github.io/#/index)       | UI框架          |  2.0.0-rc.5  |

## Build Setup / 开发流程

``` bash
# install dependencies/拉取项目,在项目路径下执行
# 国内环境建议使用cnpm install
npm install

# *推荐Yarn
yarn install

# serve with hot reload at localhost:8080
# npm安装依赖后,运行node服务器,打开 localhost:80 预览 (已运行热更新功能)
npm run dev

# build for production with minification
# 当修改代码后,需要手动打包发布时,运行npm run build命令进行打包
npm run build
```


## Components Structure / 组件结构说明:

```bash
App.vue ( 根节点 )
    |
    |- Discover.vue                         ( "发现" )
        |
        |- DiscoverAppBar.vue               ( "发现" AppBar独有组件 )
        |
        |- Swiper.vue                       ( Banner轮播组件 )
        |
        |- EnterpriseService.vue            ( "企业服务"组件 )
            |
            |- Title.vue                    ( 通用标题组件 —— "企业服务" )
            |
            |- EnterpriseService_box        ( 通用 "企业服务"组件 —— 内容盒子 )
        |
        |- Title.vue                        ( 通用标题组件 —— "热门房源" )
        |
        |- BuildingList.vue                 ( 通用楼盘组件 —— "热门房源" )
            |
            |- BuildingList_details.vue     ( 通用楼盘组件 —— "细节展示" )
    |
    |- HouseResource.vue                    ( "房源" )
        |
        |- Auto_AppBar.vue                  ( 通用组件 —— AppBar )
        |
        |- Building_Tabs.vue                ( "房源" 切换Tabs )
        |
        |- BuildingList.vue                 ( 通用楼盘组件 —— "全部房源" )
            |
            |- BuildingList_details.vue     ( 通用楼盘组件 —— "细节展示" )
    |
    |- Map.vue                              ( "地图" )
    |
    |- Service.vue                          ( "服务" )
        |
        |- Service_router.vue               ( "服务" - 路由页面 )
            |
            |- FindProperties.vue           ( 条件渲染: "委托找房" )
            |
            |- PutInProperties.vue          ( 条件渲染："投放房源" )
            |
            |- Furniture.vue                ( 条件渲染："办公家具" )
            |
            |- Decoration.vue               ( 条件渲染："办公装修" )
            |
            |- Research.vue                 ( 条件渲染："外出考察" )
            |
            |- Training.vue                 ( 条件渲染："员工培训" —— 静态页 )
            |
            |- Computer.vue                 ( 条件渲染："办公电脑" —— 静态页 )
    |
    |- 404.vue                              ( "404" )
```

- [ ] **Aoffice-SPA-WebApp-Vue待完成内容**
    - [x] 家具详情 - 接口数据
    - [ ] 外出考察详情 - 接口数据
    - [ ] 关于艾迦办公 详情页面
    - [ ] 办公电脑 - 内容图片修改( 静态页 )
    - [ ] 员工培训( 静态页面 )
    - [ ] 委托找房( 表单提交 )
    - [ ] 后期将modules 分出
    - [ ] 根据静态View需求,将改好的内容 合并起来
    - [ ] 房源详情页的JSON数据需要增加List列表图片Url
    - [ ] 房源详情页 '查看更多'按钮功能 无限期延后 ( 没必要做... )
    - [ ] 房源详情页,待售房源的价格如果为空,样式怎么处理?( 能否避免删除这个数据节点? 否则会造成样式上下不对齐 )
    - [ ] 房源详情页, 列表图片如果为空: 不要返回null,而要返回 "" 空字符串; 否则无法判断
    - [ ] 房源详情页 地图禁止放大( 双击 )
    - [ ] 首页 state结构 和 绑定需要优化( 调整mutations.js )
    - [ ] HTML 房源详情页 特殊接口地址
    - [ ] 房源详情页 list列表如果为空,添加隐藏状态
    - [ ] 房源详情页 当交互完成时再执行高度修正事件( 不要使用计时器判断 )
- [ ] **Aoffice-SPA-WebApp-Vue性能优化**
    - [ ] 可复用组件改为`render`组件形式
    - [ ] 优化项目结构列表
    - [ ] 提出`content--box`盒子作为通用内容盒子,减少样式描述
    - [ ] 整理`Sass`样式表内容,删除多余代码
    - [ ] 减少HTML内容重复描述样式
    - [ ] 增加`Gulp`构建流,优化静态图片( 进行无损压缩,避免资源加载过慢问题 )
    - [ ] 测试Router动态加载组件方案,如果性能优于单一JS加载速度,那么全部拆为动态加载
    - [ ] 增加Router切换动画,避免加载延迟空白
    - [ ] 使用H5的history改善ajax列表请求体验
    - [ ] 使用全局混合Mixins减少代码量
    - [ ] 优化Vuex的state结构; 分模块存放状态数据
    - [ ] 后台返回当前城市的中心坐标点或者字符串城市名称,然后放置到state当中储存。 在'地图'页面内进行渲染中心点

***

## API接口目录
* 房源详情页数据
    > http://app.aplusoffice.cn/api/building/getH5BuildingByCode
***

## 命名约定
> Vue文件

1. 组件名称开头需大写
2. 组件引用名称开头需大写
3. 路由页面首字母需小写

***

> Sass文件( 禁止使用CSS文件编写样式 )

1. 颜色值需大写 ( 例子'#FFF' )
2. 类名需严格遵循BEM命名法
3. 减少使用驼峰命名( 引用混合 / 继承方法除外 )

***

> JS文件

1. 变量名 / 方法名 开头需小写
2. 使用驼峰命名法( 避免使用 破折号 / 下划线 连接两个单词 )

***

> 房源详情返回数据 ( 房源详情 / 联合办公 ) 同一个
```js
{
    "resultCode": 1,
    "resultMsg": "楼盘详情加载成功",
    "resultData": {
        "typeASearch": [],                          // 独立空间LIST
        "typeBSearch": [                            // 工位LIST
            {
                "code": "R000000148",
                "type": "B",
                "area": 1,                          // 面积
                "floor": 3,
                "remark": "此处为备注",              // 备注
                "priceSale": null,                  // 总价
                "priceMonth": 700,                  // 月价
                "priceDay": 23.33,                  // 日价
                "appPic": null,                     // 手机图片
                "decoration": "B",
                "status": "1",
                "amount": 1,                        // 剩余数量（仅工位有）
                "seatCount": "D40",                 //  ---可容纳工位数（仅独立空间有）
                "isSave": false,                    // 是否收藏
                "appBuilding": null,
                "buildingType": null,
                "buildingName": null,
                "decorationStr": "精装",
                "floorStr": "低层",
                "statusStr": "待租",
                "areaStr": "1.0"
            }
        ],
        "status12Search": [                         // 待租LIST
            {
                "code": "R000000080",
                "type": "C",
                "area": 94.82,
                "floor": 25,
                "remark": "此处为备注",
                "priceSale": null,
                "priceMonth": 7965,
                "priceDay": 2.8,
                "appPic": null,
                "decoration": "C",
                "status": "1",
                "amount": 1,
                "seatCount": null,
                "isSave": false,
                "appBuilding": null,
                "buildingType": null,
                "buildingName": null,
                "decorationStr": "简装",
                "floorStr": "高层",
                "statusStr": "待租",
                "areaStr": "94.82"
            }
        ],
        "status3Search": [],                        // 待售LIST
        "buildingRelationList": [                   // 联合办公或者所属大夏
            {
                "code": "B000000008",
                "name": "长江中心A座",
                "type": "A",
                "subTitle": "因为向往大海，所以汇入长江",
                "appListUrl": "images/app/building2/B000000008/list/app_list_url.jpg",
                "description": "长江中心位于人杰地灵的青岛西海岸，是岛城首座高层钢结构商务写字楼，也是开发区目前最高级别的5A甲级写字楼，成为开发区CBD长江路上的标志性代表建筑。\r长江中心总建筑面积54000平方米，由主楼和裙楼两部分组成，其中地下2层为停车场可容纳386个车位。主楼28层，以写字楼为主，主楼一楼大堂及2、3层规划建设有高级餐厅、咖啡厅、票务及商务中心等商务配套服务，更特别设计多个多功能会议厅及仅开放给楼内企业的大小不同规模的会议室，为入驻企业提供360°国际化全面商务支持。裙楼5层，招商银行业已进驻，还有大型餐饮休闲企业，为整个CBD提供全面高端的金融、餐饮、娱乐服务。"
            }
        ],
        "buildingPicList": [
            {
                "realAppUrl": "images/building2/B000000016/real/real10.jpg"
            },
            {
                "realAppUrl": "images/building2/B000000016/real/real2.jpg"
            },
            {
                "realAppUrl": "images/building2/B000000016/real/real3.jpg"
            },
            {
                "realAppUrl": "images/building2/B000000016/real/real4.jpg"
            },
            {
                "realAppUrl": "images/building2/B000000016/real/real5.jpg"
            },
            {
                "realAppUrl": "images/building2/B000000016/real/real1.jpg"
            }
        ],
        "buildingDetails": {
            "code": "B000000016",
            "name": "欢乐颂创意办公空间",
            "type": "B",
            "address": "开发区，长江中路517号",
            "description": "欢乐颂创意办公空间配备专业秘书接受入住客户的呼叫服务，提供打印/复印服务、会务服务、接送服务、商务/法务服务、财税服务、安保服务、管理咨询等个性化一站式服务，灵动满足个性需求，达成“有限空间,无限链接”的事业愿景。",
            "propertyCompany": "长江物业；管理费：7元/平米/月",
            "floorHeight": "净高2.6m",
            "parkingNum": "地下车位数：500个",
            "longitude": 120.188076,                //  经度
            "latitude": 35.9578795,                 //  维度
            "areaMin": 1,                           //  最小面积
            "areaMax": 165,                         //  最大面积
            "priceMonthMin": null,
            "priceDayMin": 3,                       // 天最小
            "priceDayMax": 23.33,                   //  天最大
            "parentCode": "B000000008",
            "amountA": 0,                           //  ------独立空间数量
            "amountB": 40,                          // ------工位数量
            "city": "开发区",                        // ------城市
            "reg": "长江中路517号",                  // ------区
            "road": ""                              //  --------路
        }
    }
}
```

### 关于Axios跨域 提交参数总是失败问题测试结果( 通过一下代码测试百度音乐返回数据 )
```js
// 测试开放接口数据( 参数是否提交成功: 已成功! )
axios.get('http://api.jirengu.com/fm/getSong.php/', qs.stringify({
    // axios.post('http://localhost:3003/clients', qs.stringify({
    'channel': "333"
}))
.then(function (response) {
    let get_data = response
    console.log('get_data值' + get_data)
    console.dir(get_data)
    // commit('addState',get_data)
})
.catch(function (error) {
    console.log(error)
});


// 在一个Vuex的actions.js 的 任务中添加以上代码 ,当触发事件时执行这个请求
```

> 经过测试 这个请求可以返回正确的数据. 所以服务器端需要修改配置


#### 参考链接:

[How does Access-Control-Allow-Origin header work?](http://stackoverflow.com/questions/10636611/how-does-access-control-allow-origin-header-work)

[cannot get cross-site POST to work #191](https://github.com/mzabriskie/axios/issues/191)

[npm.js Axios](https://www.npmjs.com/package/axios)

[Axios 中文说明](https://www.kancloud.cn/yunye/axios/234845)

[Axios请求文档](https://zq99299.gitbooks.io/vue-note/chapter/axios.html)
