# 说明

vue仿豆瓣app项目 持续更新中....


# 技术栈
vue2 + vuex + vue-router +  ES6+ fetch + sass + flex + svg+vantUI

**版本:**

vue: ^2.6.11,
 vue-router: ^3.1.6,
 vuex: ^3.1.3"，
vant: 1
node:12.16.2.0
#项目运行
git clone [https://github.com/estherzz/vue2-douban](https://github.com/estherzz/vue2-douban.git)
cd vue2-douban
yarn serve (或者 npm ren serve)

# 部分gif效果图

![底部tabnav切换路由.gif](https://upload-images.jianshu.io/upload_images/20110534-d4163139273d14c7.gif?imageMogr2/auto-orient/strip)

![首页话题详情.gif](https://upload-images.jianshu.io/upload_images/20110534-47f9cf6599e796e9.gif?imageMogr2/auto-orient/strip)
![电影+电影详情.gif](https://upload-images.jianshu.io/upload_images/20110534-cb51846a1e1ad427.gif?imageMogr2/auto-orient/strip)

![更多+片单.gif](https://upload-images.jianshu.io/upload_images/20110534-bb0b007e6170b570.gif?imageMogr2/auto-orient/strip)

![小组首页.gif](https://upload-images.jianshu.io/upload_images/20110534-bc98cd11c949768f.gif?imageMogr2/auto-orient/strip)

# 接口
根据本人项目需要 自己总结的一些接口

> get请求

```
热门话题
https://www.douban.com/j/gallery/rec_topics?
  {
     query {
         start：，number 条目开始位置（最大47）
         count：， number 条目数量
     }
  }

热门电影
https://movie.douban.com/j/search_subjects
    {
      query {
          type：movie，
          tag：string ‘热门’，
          page_limit：number 条目数量
          page_start：， number 条目开始位置
      }
  }
```

`以下所有接口的前缀为
https://m.douban.com/rexxar/api/v2`
```
电影
/movie/:id?ck=&for_mobile=1
    {
        id：电影id
    }

电影评论
/movie/:id/interests?ck=&for_mobile=1
 {
        id：电影id,
        query:{
            count: number 评论数量，
            order_by: string 评论类型 例 hot
            start: 评论开始截取的位置
        }
    }

主创人员列表
/movie/:id/credits
   {
        id：电影id
    }

主创人员详情
/celebrity/:id/
   {
        id：主创人员id
    }

主创个人作品
/celebrity/:id/works?sort=vote
     {
        query {
           count：number 条目数量
         }
     }


小组首页列表
/group/explore 

小组话题
/group/:id/topics
   {
        id：小组id
    }
/group/topic/:id/comments  小组评论
   {
        id：话题id
    }

话题
    首页中热门/新话题
/gallery/rec_topics
    {
        query {
           start：number 条目开始的位置
           count：number 条目数量
           sort:  string  hot/new
         }
     }

某话题列表
/gallery/topic/:id/items?status_full_text=1&guest_only=0&ck=null
   {
        id：话题id
    }

片单列表
/skynet/playlists?from_rexxar=&
     {
        query {
           start：number 条目开始的位置
           count：number 条目数量
         }
     }

某片单电影列表
/doulist/:id/items  
   {
        id：片单id
    }

两组分类电影列表
/movie/hot_channels

'找电影'模块列表
/movie/suggestion?new_struct=1&with_review=1&for_mobile=1
     {
        query {
           start：number 条目开始的位置
           count：number 条目数量
         }
     }
```


