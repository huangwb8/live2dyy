# live2dyy
 live2dyy: Beta version

# Usage

+ 在主题`footer.php`文件的标签`</body>`之后添加：

```HTML
<!--博客宠物-->
<script src="https://cdn.jsdelivr.net/gh/huangwb8/live2dyy@latest/autoload.js"></script> 
<!--音乐播放器-->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/aplayer/dist/APlayer.min.css">
<script src="https://cdn.jsdelivr.net/npm/aplayer/dist/APlayer.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/meting@2.0.1/dist/Meting.min.js"></script>
<!--这里的ID要换成自己喜欢的音乐集-->
<meting-js id="6912478729" server="netease" type="playlist" theme="#339981" fixed="true"
preload="auto" autoplay="false" loop="all" order="random" volume="0.3"></meting-js>
<script>
function removelrc(){
	$(".aplayer.aplayer-fixed .aplayer-body").addClass("my-hide");
	//document.querySelector('meting-js').aplayer.lrc.hide();
	$(".aplayer.aplayer-fixed .aplayer-icon-lrc").addClass("aplayer-icon-lrc-inactivity");
	$(".aplayer.aplayer-fixed .aplayer-lrc").addClass("aplayer-lrc-hide");
	document.querySelector('meting-js').aplayer.on('play', function () {
    		document.querySelector('meting-js').aplayer.lrc.show();
    		$(".aplayer.aplayer-fixed .aplayer-icon-lrc").removeClass("aplayer-icon-lrc-inactivity");
	});
	document.querySelector('meting-js').aplayer.on('pause', function () {
    		document.querySelector('meting-js').aplayer.lrc.hide();
    		$(".aplayer.aplayer-fixed .aplayer-icon-lrc").addClass("aplayer-icon-lrc-inactivity");
	});
}
document.querySelector('meting-js').addEventListener("DOMNodeInserted",removelrc);
setTimeout(function() {
	document.querySelector('meting-js').removeEventListener("DOMNodeInserted",removelrc);
	//移除左侧栏切换时的监听事件防止页面刷新
	if($("#leftbar_tab_catalog_btn").length > 0){
		var el = document.getElementById('leftbar_tab_catalog_btn'),elClone = el.cloneNode(true);
		el.parentNode.replaceChild(elClone, el);
	}
	var el = document.getElementById('leftbar_tab_overview_btn'),elClone = el.cloneNode(true);
	el.parentNode.replaceChild(elClone, el);
	var el = document.getElementById('leftbar_tab_tools_btn'),elClone = el.cloneNode(true);
	el.parentNode.replaceChild(elClone, el);
}, 5000);
</script>
```

+ Wordpress-dashboard - 主题 - 自定义- 额外 CSS

```css
.my-hide{
	display:none !important;
}
.zero-margin-bottom{
	margin-bottom:0 !important;
}
```

# Test

> 个人专用，大佬们手下留情，不要点`https://purge*`类的网址。谢谢！

+ autoload.js
  + https://purge.jsdelivr.net/gh/huangwb8/live2dyy@latest/autoload.js
  + https://cdn.jsdelivr.net/gh/huangwb8/live2dyy@latest/autoload.js
+ waifu-tips.js
  + https://purge.jsdelivr.net/gh/huangwb8/live2dyy@latest/waifu-tips.js
  + https://cdn.jsdelivr.net/gh/huangwb8/live2dyy@latest/waifu-tips.js
+ waifu-tips.json
  + https://purge.jsdelivr.net/gh/huangwb8/live2dyy@latest/waifu-tips.json
  + https://cdn.jsdelivr.net/gh/huangwb8/live2dyy@latest/waifu-tips.json
+ waifu.css
  + https://purge.jsdelivr.net/gh/huangwb8/live2dyy@latest/waifu.css
  + https://cdn.jsdelivr.net/gh/huangwb8/live2dyy@latest/waifu.css

+ live2d.min.js
  + https://purge.jsdelivr.net/gh/huangwb8/live2dyy@latest/live2d.min.js
  + https://cdn.jsdelivr.net/gh/huangwb8/live2dyy@latest/live2d.min.js
+ model_list.json
  + https://purge.jsdelivr.net/gh/huangwb8/live2dyy@latest/live2d_api/model_list.json
  + https://cdn.jsdelivr.net/gh/huangwb8/live2dyy@latest/live2d_api/model_list.json
