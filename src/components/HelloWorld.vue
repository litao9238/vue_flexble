<template>
    <div class="hello">
    	<x-header>This is the page title.</x-header>
        <div class="selector">
            		这是一个标题
        </div>
        <div>dpr: {{dpr}}</div>
        <div>html font-size: {{size}}</div>
        <br /><br /><br />
        
        <p class="msg">
        	下面两段是以750的设计稿,font-size: 36px<br />
        	在1倍屏下会有不同的展示<br />
        	在2倍屏(例如iphone)下会有不同的展示<br />
        	↓
        </p>
        
        <div class="a1">这是一个处理过的</div>
        
        <div class="a2">这是一个未处理的</div>
        
        
        
        <h1>- -!</h1>
        <h1>当使用第三方ui库,例如vux,出现无法解决的问题</h1>
        <h1>因css源码使用px单位而被处理掉,导致实际显示变小</h1>
        
        
    </div>
</template>

<script>
    export default {
        name: 'HelloWorld',
        data() {
            return {
                msg: 'Welcome to Your Vue.js App',
                dpr: '',
                size: ''
            }
        },
        mounted(){
        	var html = document.getElementsByTagName('html')[0]
        	
        	this.dpr = html.getAttribute('data-dpr')
        	this.size = html.style.fontSize
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" scoped>
	.msg{
		font-size: 36px;
		line-height: 1.5;
	}
    .selector {
        width: 100%;
        height: 100px;
        line-height: 100px;
        font-size: 36px;
        border: 1px solid #ddd;
    }
    .a1{
    	font-size: 36px;
    }
    .a2{
    	font-size: 36px;/*no*/
    }
</style>