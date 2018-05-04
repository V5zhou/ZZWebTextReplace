# ZZWebTextReplace
替换H5中指定关键字

## 经过
早上有同学问我，他们在做马甲包，用户服务协议页面是H5做的，每个包都对应有个不同的公司名，app名称，有没有办法批量替换关键字。我就试了下NSURLProtocol，果然可以，有此需求的同学可以直接拖走用。

## 重点说明
**LisenURL不一定为你发起请求的入口源URL，因为一个请求包含有css，js，html，公共js文件，每个文件都是一个URL。监听的为对应文件的URL，才能替换对应文件内文本。** 也有可能返回的页面是个重定向页面，如不确定想替换文本存在于哪个文件中，可以charles先抓下包来看。

## 指定替换
```
//格式如下：外层字典key指定生效的URL，value中宝典指定替换规则。
NSDictionary *lisenURLS = @{
                                @"https://www.jianshu.com/p/bff75ce137fc" :
                                    @{
                                        @"我": @"❌",
                                        @"你": @"💢",
                                        @"的": @"💤",
                                        },
                                };
```

## 替换效果

![效果图](https://upload-images.jianshu.io/upload_images/3913024-b0fef65c37c402cd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)
