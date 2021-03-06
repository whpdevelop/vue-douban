# douban-vue

> A Vue.js project
>
> 完成:
>
> 首页列表(滚动到底部加载数据)
>
> 电影和图书模块的列表、详情(评论的加载更多)

## 豆瓣接口分析

```js
/* 
    获取数据文件
*/

/* 
    豆瓣 api 
    基准路径
    http://127.0.0.1:3000/rexxar/api/v2

    电影模块接口

    首页数据
    参数
    next_date 日期(每条数据中有上一天的日期数据)
    地址
    /recommend_feed?next_date=${this.param}

    影院热映/免费在线观影/新片速递
    参数
    start: 开始位置
    count: 数量
    type:
     -> 获取影院热映数据  movie_showing
     -> 获取免费在线观影 movie_free_stream
     -> 获取新片速递 movie_latest
    地址
    /subject_collection/type/items?start=0&count=20

    影院各电影详情信息
    参数 
    id: 例如(26752088)
    地址
    /elessar/subject/id

    详情中的影人
    参数
    id: 例如(26752088)
    地址
    /movie/${id}/credits

    详情中的评论
    参数
    id: 例如(26752088)
    count: 获取评论的数量
    start: 开始索引
    type : movie/book
    地址
    /type/${id}/interests?count=${count}&&start=${start}

    图书模块接口

    图书信息接口
    参数
    start: 开始位置
    count: 数量
    type:
     -> 虚构类小说 book_fiction
     -> 非虚构类小说 book_nonfiction
     -> 豆瓣书店 market_product_book_mobile_web
    地址
    /subject_collection/type/items?start=0&count=20

    广播模块数据
    参数
    id: (每条评论的id 获取该id 之前的20条数据) 
    地址
    /status/anonymous_timeline?max_id=2023764988

*/

***注意***
    由于豆瓣接口做了referer限制所以配置了代理服务器
	即server文件中的内容(easy)
```



## Build Setup

``` bash
在运行项目之前需要需先将代理服务器运行(server文件夹)

# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
