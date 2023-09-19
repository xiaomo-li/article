# 滚动定位/a 标签的锚点定位

a 标签的锚点定位很方便，但不够灵活。
但业务菜单固定在顶部，遮挡了一部分内容，a 标签的定位后显示在小标题下方。
想要正常显示，只能自己实现一份跳转效果。

##　用 jq 替代 a 标签的锚点定位

```html
<!-- 跳转链接 -->
<div class="jump-links sticky-top">
  <div class="limit-width">
    <div class="a active" target="#table1">在租房源</div>
    <div class="a" target="#intro">商务中心简介</div>
    <div class="a" target="#where">所属大厦</div>
    <div class="a" target="#around">周边配套</div>
    <div class="a" target="#recommend">推荐周边</div>
  </div>
  <div id="table1">
    <div class="info-title">222艾克商务中心简介</div>
    <div>
      艾克商务中心提供共享办公解决方案，与客户携手建立理想的办公环境，并透过足迹遍布亚洲多个地区的20多个服务式办公空间网络推动创新商业概念。
      总部设于新加坡，艾克商务中心拥有20多个办公空间，覆盖北京、上海、香港、新加坡、马来西亚、仰光共6个城市。艾克商务中心在全球主要城市的重点商业区为会员提供一系列高端精致的商务中心，让当下的领导者在这里结识、合作和学习，以及获取更多营商机会。艾克商务中心是艾克集体（Arcc
      Holdings）的业务之一。艾克集团拥有房地产、酒店，以及服务式商务中心，传递创新商业概念，以达至“工作、生活及享受”（Work，Live，Play）的理念。
    </div>
  </div>
  <div id="intro">
    <div class="info-title">艾克商务中心简介</div>
    <div>
      艾克商务中心提供共享办公解决方案，与客户携手建立理想的办公环境，并透过足迹遍布亚洲多个地区的20多个服务式办公空间网络推动创新商业概念。
      总部设于新加坡，艾克商务中心拥有20多个办公空间，覆盖北京、上海、香港、新加坡、马来西亚、仰光共6个城市。艾克商务中心在全球主要城市的重点商业区为会员提供一系列高端精致的商务中心，让当下的领导者在这里结识、合作和学习，以及获取更多营商机会。艾克商务中心是艾克集体（Arcc
      Holdings）的业务之一。艾克集团拥有房地产、酒店，以及服务式商务中心，传递创新商业概念，以达至“工作、生活及享受”（Work，Live，Play）的理念。
    </div>
  </div>
</div>
```

```js
// 点击菜单跳转
$(".jump-links .a").click(function () {
  $(this).addClass("active").siblings().removeClass("active");
  let id = $(this).attr("target");
  let top = $(id)[0].offsetTop - 160;
  window.scroll(0, top);
});
// 滚动至内容处高亮菜单
let items = $(".jump-links .a");
$(window).scroll(function () {
  for (let i = 0; i < items.length; i++) {
    let id = items.eq(i).attr("target");
    if ($(window).scrollTop() + 300 > $(id).offset().top) {
      items.eq(i).addClass("active").siblings().removeClass("active");
    }
  }
});
```
