=========9.26更新========

2个条件：

1、需要会抓手机包

2、我给你的是curl包，要会用


=========9.24更新========

已解决，可正常使用和下单了，可以联系我(eHVlcjI3OTU0)试用，base64解码

只需要2个参数，即可完成自动下单

##只是能正常下单，真实抢购还是买不到的！！##

##只是能正常下单，真实抢购还是买不到的！！##

##只是能正常下单，真实抢购还是买不到的！！##

##只是能正常下单，真实抢购还是买不到的！！##

##只是能正常下单，真实抢购还是买不到的！！##

<img width="773" alt="image" src="https://github.com/gxh27954/damai_requests/assets/24693917/6c3801d2-6f1b-41fb-99cb-6fbe84d66d23">


=========9.23更新========

api写完了，本地也能正常调用购买成功，但是部署到云服务器后，就不行了，看起来是damai对云厂商的ip做了限制...

找了好几家云，发现都一样，只能先部署在我本地了，然后挂了个内网穿透（不稳定）





=========9.22更新========

正在着手写成一个完整的api接口，给我商品信息、座次信息、账号信息，然后可以调用买票流程，预计明天可以开放出来


=========9.16更新========

我把app的加密hook写成了一个api接口，直接给我参数，我会返回加密后的字段给你，可以联系我(eHVlcjI3OTU0)试用

req:

curl --location 'http://x.x.x.x:9000/hook' \
--header 'Content-Type: application/json' \
--data-raw '{
    "params": {
        "data": "{xxx}",
        "sid": "1c749a58222fbfd0c8117a836373215a",
        "uid": "2216311116140",
        "x-features": "27",
        "appKey": "23781390",
        "api": "mtop.common.gettimestamp",
        "utdid": "ZOg1nAq3HFYDA222lgMTdsNX",
        "ttid": "10005884@damai_android_8.6.8",
        "t": "1694760745",
        "v": "2.0"
    },
    "uid": 0
}'

rsp:

{"code": 0, "data": {"wua":
"CofS_LnO9G0xnVCRLEvUH20kI80pheuJfDzfqKX3SBPAwP7RdoBP3Y0EPutrdjmp4/I63eofec+gu+hPJW+DXsU6f6JMz79i1g9YV9JEGYHg03mv9/9jozGLU2BPSfn2p67+mzu6Hjkq1GlbwtA3n+X5tXFy3tN0mO8+L6lT6HcN9ljnP8TrSJCNXuy8Md345MVAtq9t5MzNOW5Bx4G9vdAHiaCEXFMyZPdoVYDnXdkK1JbKO8OG8dqJvEvTjezaYgFll639WvFvj4KdNjmmM+nkzPG7Kq2Vp/x8bd2FWEPnnuu4=",
"x-sgext":
"JBJoAwBzb9BCxKnzlkXazgNZMlg2WSBbNlE6SzFaIEsyXjpcO1swUDVaIFgzWDNYM1gzWDNYM1gzWDNLM0szSzNYIFgzWDNLM0sySzJLMksySzJLMkszSzNLM0szSzNLM0szSzNLM0szSyBaIEszWDNYM1ggWDNYM1ggWCBaZwkgWCBLM0s7SzNLMEt5KUtfIFggSCNIM0gjSDM=",
"x-sign": "azG34N002xAAJLf8qptL3twSmKT2lLf0tr3nsuSx+7EclhflAKAEOxY399weYWDTdN7JkzmTsPmEhnPw58Xz82XDZWS2lLf0tpS39L",
"x-umt": "tioBG3VLPPocNAKKmV1yfDKn5njmcHDT", "x-mini-wua":
"aFwQvuWTw5ga+UKefNwpH7Ju2bYXkOH18V74JS1zL+qLuMrLNoHkvh316NVMwIKLEkH1rLatU6zK02ZXjXXPJF1BvZ7iHeaFK/ZMUTXoJWvbUgXMRj9LKqudRlZnBHS+xPfmEoucf2ANOHqbxMvi2WG7NqlES2uXFLss="}}

=========9.13更新========

这里向大家咨询个技术问题，现在小程序监控的场次大概400场了，并发同时有400个http请求，速度很慢，大概10s一把

然后我就用了3台云服务器，每台服务器大概同时请求150场，1.5s可以完成一次

多台服务器配置不高，但是成本不低，有啥更合适的方法吗

特别是如果后面再支持猫眼、票星球、纷玩岛，按现在的方法就得继续加机器，才能做到精准的监控

并发http请求是用的python的grequests框架

=========8.30更新========

小程序昨天居然小火了一下，赶忙上云、买db，好贵！

=========8.27更新========

做了个监控回流票的小程序，免费用

![gh_cd589c707250_258](https://github.com/gxh27954/damai_requests/assets/24693917/7edab18a-ef28-4cb8-a379-7f0ae740ac4f)


=========8.23更新========

以为是ip的问题，然后我用了代理ip来请求，结果发现：order.build的时候正常请求，order.create的时候用代理ip访问会卡住然后超时，难道是被检测到了？


# 记录一下大麦网抢票历程

之前很久就听说过大麦抢票很暴利，然后我是7月底的时候接触到的，这个时候热门的票已经不能在PC web和h5抢了，只能在app

然后在git上一搜，app抢票的代码太少了，h5的倒数不少，于是clone了一个试试手

结果发现大麦又进步了，这个代码已经失效，跑不起来了，那咋办，那就自己弄呗

## H5代码
其实就是俩接口，order.build和order.create，后者的数据依赖于前一个接口的返回

然后从h5入手，抓包，发现和我clone的这份代码里的包结构差不多，字段里也就多了些submitref、signKey、bx-umidtoken、bx-ua，看起来把这些玩意找到就差不多了

submitref和signKey好弄，直接调接口去获取就行了

烦人的是bx-ua和bx-umidtoken，这俩得看js代码去弄怎么生成的，于是不断搜索，这就是ali系的一些加密玩意而已，前人早就搞定了，于是顺利解决

这些点虽然解决了，其实还是调了好多，因为有些数据要urlcode编码，有些又不用，不断调试，花了挺多时间

正确运行起来后，发现经常下单的时候会说太频繁了，出现验证码，那咋搞，原来返回的data下有个url，那个就是验证码的页面

既然是个滑块验证码，最简单的方法那就selenium滑一滑，如果是出现了验证码，我再去滑，那多慢啊，把这个东西前置一下尝试一把，发现可行

于是真正完成了h5的抢票，order.build和order.create

## vx小程序
再一看，有些场次不支持h5，但是支持vx小程序，那高低得弄一下，发现啥也没变，就是channle改改就成了，轻松搞定

## APP
想做一个技术型黄牛，只支持H5+小程序，这是远远不够的，H5的会有频控，请求几下就RGV587_ERROR::SM::哎哟喂,被挤爆啦,请稍后重试!

于是进军APP

首先在git找到一个大牛的文章，大意是app发包里有很多加解密的字段，通过hook安卓机来帮忙加密字段，然后requests请求

那就搞吧

具体过程略了，挺艰难的，就是跟着大佬的成果一步一步走，说说后面遇到的一堆问题吧

### 验证码：
我用和H5一样的办法解决验证码，结果经常在创单那一步卡住，验证码过了也还是给我报错，这个卡了几天，终于解决了

### FAIL_SYS_TRAFFIC_LIMIT
能成功下单了，但是跑太快了，就会被限流，返回FAIL_SYS_TRAFFIC_LIMIT

这个我以为是简单的账号限流，然后我就注册了几个号测试一下：我第一个号不断请求，当被LIMIT限流时，用第二个号去请求，结果发现也限流了？？

说明是有啥共用的字段被检测了，而不只是账号的单因素原因，可能是did、解密的安卓机、ip、验证码等等，一个个试，能随机的都随机，总能解决的，又卡了几天

### 亲，同一时间下单人数过多，建议您稍后再试
现在就变成了，普通的场次可以成功下单

现在又遇到了新的问题：F-10012-01-16-001::亲，同一时间下单人数过多，建议您稍后再试

不知道是账号问题，还是ip等问题，还得继续研究

欢迎来讨论
