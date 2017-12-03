<template>
  <div class="hello">
   <div class="menumanage" style="border:1px solid #e4e4e4; border-bottom:none">
        <h1>菜单管理</h1>
        <div class="custommain">
            <div class="menutype">请选择服务类型：
                <select name="">
                    <option value="">固定菜单</option>
                    <option value="">自定义菜单</option>
                </select>
            </div>
            <dl class="explain">
                <dt>在这里您可以自定义菜单及菜单跳转链接</dt>
                <dd>适用机型：YUNOS、LETV、LENOVO、OPPO、Gionee、VIVO、ZUK</dd>
            </dl>
            <div class="phoneoperate">
                <div class="phone">
                    <div class="tingt"></div>
                    <div class="phonmain"></div>
                    <div class="phonmenu clearfix">
                        <div class="phonejp l">键</div>
                        <ul class="menu l">
                            <li class="addmainmu" @click="addmenu()">+添加菜单</li>
                            <!--                                 <li class="mu">嘉华服务
<div id="triangledown">1</div>
                                <ul class="submenu">
                                    <li>1</li>
                                    <li>2</li>
                                    <li class="addsubmenu">+</li>
                                </ul></li> -->
                            <!--      <li  class="mu">嘉华活动</li>
                                <li  class="mu">联系我们</li> -->
                                <MainLi name="AAAA"></MainLi>
                        </ul>
                    </div>
                    <div class="phonefoot">
                        <div class="circle"></div>
                    </div>
                </div>
 <div class="showmenudetial">
                    <div class="addedit" v-show="isShow"  ismenu="1" mainmenu="">
                        <h2><span class="cdmc">菜单名称</span><span class="deletxt">删除菜单</span></h2>
                        <ul>
                            <li class="subname"><span style="color:#ff0000">*</span>菜单名称：
                                <input type="text" name="" id="menuname" value="" placeholder="子菜单名称">
                                <p class="ts">字数不超 过4个汉字或8个字母</p>
                            </li>
                 
                            <li class="submain"><span></span>菜单内容：
                                <span id="h5" class="subcla"><input id="one" type="radio" name="nr" value="h5" checked  placeholder="H5链接"><label for="one">H5链接</label></span>
                                <span id="imgtxt" class="subcla"><input id="two" type="radio" name="nr" value="图文模板"  placeholder="图文模板"><label for="two">图文模板</label></span>
                                <span id="feast" class="subcla"><input id="three" type="radio" name="nr" value="活动" placeholder="活动"><label for="three">活动</label></span>
                                <span id="online" class="subcla"><input id="four" type="radio" name="nr" value="在线客服" placeholder="在线客服"><label for="four">在线客服</label></span>
                                <div class="submaincheck">
                                    <div class="subtype h5" style="display:block;">
                                        <p>用户点击该基金后会跳转到以下链接</p>
                                        <div class="">页面地址:
                                            <input type="text" name="" value="" placeholder="">
                                        </div>
                                    </div>
                                    <div class="subtype imgtxt" style="display:none;">
                                        <ul>
                                            <li>
                                                <img>
                                                <p>空的</p>
                                            </li>
                                            <li>
                                                <img>
                                                <p>上文下图</p>
                                            </li>
                                            <li>
                                                <img>
                                                <p>上下文中图</p>
                                            </li>
                                            <li>
                                                <img>
                                                <p>上文下图</p>
                                            </li>
                                        </ul>
                                    </div>
                                    <div class="subtype feast" style="display:none;">
                                        <p>可以绑定已发布的活动，用户点击此菜单可以跳转至相应活动页面</p>
                                        <div class="">　　活动:
                                            <select name="">
                                                <option value="中秋大礼包２０１７">中秋大礼包２０１７</option>
                                                <option value="中秋大礼包２０１８">中秋大礼包２０１８</option>
                                                <option value="中秋大礼包２０１９">中秋大礼包２０１９</option>
                                                <option value="中秋大礼包２０２０">中秋大礼包２０２０</option>
                                            </select>
                                        </div>
                                    </div>
                                    <div class="subtype online" style="display:none;">
                                        <ul>
                                            <li style="overflow:hidden">在线客服:
                                                <input type="
                                        " name="" value="" class="zxkfname" placeholder="">
                                            </li>
                                            <li style="overflow:hidden; line-height:80px">
                                                <p class="headset">头像设置:</p>
                                                <div>
                                                    <p class="imghead"></p>
                                                    <p class="imgadd">+</p>
                                                </div>
                                            </li>
                                            <li>自动回复:
                                                <input class="inpureply" type="
                                        " name="" value="" placeholder="你好，请问有什么可以帮助您？">
                                            </li>
                                        </ul>
                                    </div>
                                </div>
                            </li>
                        </ul>
                    </div>
                    <div class="edittxt" v-show="isHide" style="text-align:center; line-height:460px">点击左边进行编辑</div>
                </div>
                <div class="btnContent">
                    <button type="" class="" id="save">预览</button>
                    <button type="">保存并提交审核</button>
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
import MainLi from './MainLi'
export default {
  name: 'HelloWorld',
  components:{MainLi},
 data() {

 return{
         tabs: ["标题一", "标题二","标题三"],
         tabContents: ["内容一", "内容二","内容三"],
         num: 1,
         isShow:false,
         isHide:true
         }
    },
    methods: {
        tab(index) {
            this.num = index;
        },
        addmenu(){
        console.log(this.isShow)
          this.isShow=true;
          this.isHide=false;
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 li{list-style:none;}
  .menumanage h1 {
        background-color: #f2f2f2;
        font-size: 16px;
        color: #000;
        padding: 0 12px;
        border-bottom: 1p solid #e4e4e4;
    }
    
    .custommain {
        padding: 12px;
    }
    
    .custommain .menutype select {
        width: 200px;
    }
    
    .custommain .explain {
        margin-bottom: 16px;
    }
    
    .custommain .explain dt {
        color: #ff0000;
        font-weight: bold;
        padding: 8px 0;
    }
    
    .phoneoperate {
        overflow: hidden;
    }
    
    .phoneoperate .phone {
        width: 26%;
        float: left;
        background-color: #474e5e;
        border-radius: 16px;
        padding: 0 0.8%;
    }
    
    .phoneoperate .phone .tingt {
        background-color: #7d7d7d;
        width: 30%;
        margin: 12px auto;
        border-radius: 12px;
        padding: 4px;
    }
    
    .phonmain {
        background-color: #fff;
        min-height: 415px;
    }
    
    .phonefoot {
        padding: 24px 0px;
    }
    
    .phonefoot .circle {
        width: 25px;
        height: 25px;
        border-radius: 20px;
        background-color: #7d7d7d;
        margin: 0 auto;
    }
    
    .phonmenu {
        background-color: #fff;
        border-top: 1px solid #e4e4e4;
    }
    
    .phonmenu .menu .mu {
        position: relative;
        background-color: #fff;
        cursor: pointer;
    }
    
    .phonmenu .menu .addmainmu {
        position: relative;
        text-align: center;
        color: #44b548;
        background-color: #fff;
        padding: 0.8% 0;
        cursor: pointer;
        float: right;
        width: 100%;
    }
    
    .phonmenu .menu .addmainmu-l {
        border-left: 1px solid #e4e4e4;
    }
    
    .phonmenu .menu .mu .submenu {
        border: 1px solid #e4e4e4;
        border-top: none;
        position: absolute;
        text-align: center;
        width: 100%;
        bottom: 31px;
        left: 0px;
        border-radius: 8px 8px 0 0;
        overflow: hidden
    }
    
    .phonmenu .menu .mu .submenu li {
        border-top: 1px solid #e4e4e4;
         background-color:#fff;
    }
       .phonmenu .menu .mu .submenu li.check1 {
        background-color:#44b548;
        border-top: 1px solid #44b548;
        color:#fff;
    }
    
    .l {
        float: left
    }
    
    .phonejp {
        width: 10%;
        text-align: center;
        padding: 0.8% 0;
        border-right: 1px solid #e4e4e4;
    }
    
    .phonmenu .menu {
        width: 89.5%;
    }
    
    .phonmenu .menu .mu {
        width: 33%;
        display: inline-block;
        text-align: center;
        padding: 1% 0;
        border-right: 1px solid #e4e4e4;
    }

       .phonmenu .menu .current {
            background-color:#44b548;

       }

       .phonmenu .menu .sl{
            background-color:#fff;
       }
       .phonmenu .menu .current span{
        color:#fff;
       }
       .phonmenu .menu .sl span{
        color:#000;
       }

       .phonmenu .menu .current .submenu .sublimenu span{
            color:#000;
       }

       .phonmenu .menu .current .submenu .check1 span{
            color:#fff;
       }
    
    .phonmenu .menu .mu:last-child {
        border: none;
    }
    
    .phonmenu .menu .mu ul,
    .phonmenu .menu .mu #triangledown {
        display: none
    }
    
    .phonmenu .menu li.current ul,
    .phonmenu .menu li.current #triangledown {
        display: block
    }
    
    .showmenudetial {
        margin-left: 28%;
        border: 1px solid #e4e4e4;
        padding: 0.5%;
        min-height: 553px
    }
    
    .showmenudetial h2 {
        font-size: 14px;
        border-bottom: 1px solid #e4e4e4;
        margin-bottom: 12px
    }
    
    .showmenudetial .deletxt {
        float: right;
        cursor: pointer
    }
    
    .showmenudetial ul li {
        margin-bottom: 24px;
    }
    
    .showmenudetial .subname input {
        width: 80%;
    }
    
    .showmenudetial .subname .ts {
        padding-left: 80px;
    }
    
    .showmenudetial .submain span {
        margin-right: 8px;
    }
    
    .showmenudetial .submain .submaincheck {
        margin-left: 80px;
        border: 1px dashed #e4e4e4;
        padding: 8px;
    }
    
    .showmenudetial .submain .submaincheck .h5 {
        font-family: "微软雅黑"
    }
    
    .showmenudetial .submain .submaincheck .subtype p {
        margin-bottom: 25px;
        font-size: 14px;
    }
    
    .showmenudetial .submain .submaincheck .subtype {
        font-size: 14px;
    }
    
    .showmenudetial .submain .submaincheck .subtype input {
        width: 80%;
    }
    
    .headset {
        float: left
    }
    
    .imghead,
    .imgadd {
        width: 80px;
        height: 80px;
        border: 1px solid #e4e4e4;
        float: left;
        margin-right: 1.2%;
        text-align: center;
        margin-bottom: 0px;
    }
    
    .imgtxt ul {
        overflow: hidden
    }
    
    .showmenudetial .submain .submaincheck .imgtxt img {
        height: 100px;
        width: 80px;
    }
    
    .showmenudetial .submain .submaincheck .imgtxt li {
        margin-right: 16px;
        width: 80px;
        float: left;
        border: 1px solid #e4e4e4;
    }
    
    .showmenudetial .submain .submaincheck .imgtxt li.check {
        border: 1px solid #ff0000;
    }
    
    .showmenudetial .submain .submaincheck .imgtxt li p {
        text-align: center;
        margin-bottom: 0px!important
    }
    
    .btnContent {
        text-align: center;
        padding-top: 24px;
    }
    
    .btnContent button {
        background-color: #3f88eb;
        color: #fff;
        font-size: 14px;
        border: none;
        border-radius: 5px;
        padding: 8px 16px;
    }
    
    .clearfix:after {
        content: " ";
        display: block;
        clear: both;
        height: 0;
    }
    
    .clearfix {
        zoom: 1;
    }
    
    #triangledown {
        width: 0;
        height: 0;
        position: absolute;
        top: -33%;
        left: 48%;
        border-left: 3px solid transparent;
        border-right: 3px solid transparent;
        border-top: 6px solid #e4e4e4;
    }
</style>
