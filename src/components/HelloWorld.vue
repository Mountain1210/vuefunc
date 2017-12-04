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
                            <li class="addmainmu" v-show="addshow" ref="addmu" @click="addmenu()">+添加菜单</li>
                            <!--                                 <li class="mu">嘉华服务
<div id="triangledown">1</div>
                                <ul class="submenu">
                                    <li>1</li>
                                    <li>2</li>
                                    <li class="addsubmenu">+</li>
                                </ul></li> -->
                            <!--      <li  class="mu">嘉华活动</li>
                                <li  class="mu">联系我们</li> -->
                              
                                <MainLi v-for="(item,index) in tabs" :class="{current:index==num}" :name="item.name"  @select="tab(index)" @addsub="addsubck($ev)"></MainLi>
                               <!--<li>{{muname}}</li>-->
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
                                <input type="text" name="" id="menuname" value="" v-model="muname" placeholder="子菜单名称" ref="inputname">
                                <p class="ts">字数不超 过4个汉字或8个字母</p>
                            </li>
                 
                            <li class="submain" ref="spanmenu"><span></span>菜单内容：
                            <template v-for='(item,index) in subtab'>
                                <span :id="item.spainid" class="subcla" @click="subtabs(index)"><input :id="item.inputid" type="radio" name="nr" :checked="index==addrSelected"/><label :for="item.inputid">{{item.labelval}}</label></span>
                            </template>
                                <div class="submaincheck"  ref="allsubtype">
                                    <div class="subtype h5" v-show="subishow">
                                        <p>用户点击该基金后会跳转到以下链接</p>
                                        <div class="">页面地址:
                                            <input type="text" name="" value="" placeholder="" v-model="inputh5" ref="h5">
                                        </div>
                                    </div>
                                    <div class="subtype imgtxt" v-show="subishow">
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
                                    <div class="subtype feast" v-show="subishow">
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
                                    <div class="subtype online" v-show="subishow">
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
                    <button type="" class="" id="save" @click="preview()">预览</button>
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
         tabs: [{id:'1','name':'标题1','maintype':{"type":"h5",
                                        "h5":"www.163.com",
                                        "imgtxt":"",
                                        "feast":"",
                                        "online":{
                                            "name":"",
                                            "imghead":"",
                                            "autoreply":""
                                        }},'sublist':[]},{id:'2','name':'标题2','maintype':{"type":"imgtxt",
                                        "h5":"",
                                        "imgtxt":"0",
                                        "feast":"",
                                        "online":{
                                            "name":"",
                                            "imghead":"",
                                            "autoreply":""
                                        }},'sublist':[]}],
         subtab: [{'spainid':'h5','inputid':'one','labelval':'H5链接'}, {'spainid':'imgtxt','inputid':'two','labelval':'图文模板'},{'spainid':'feast','inputid':'three','labelval':'活动'},{'spainid':'online','inputid':'four','labelval':'在线客服'}],
         num: 0,
         subnum:0,
         inputh5:'',
         isShow:false,
         isHide:true,
         addshow:true,
         muname:'',
         subishow:false,
         addrSelected:0,
         type:"",

         }
    },
    mounted:function(){
       if(this.tabs.length>=3){
        this.addshow=!this.addshow;
        this.$refs.addmu.style.display="none"
       }else if(this.tabs.length>=2){
        this.$refs.addmu.style.width="33.3%";
        this.$refs.addmu.style.borderLeft="1px solid #e4e4e4";
       }else if(this.tabs.length==1){
        this.$refs.addmu.style.width="66%";
        this.$refs.addmu.style.borderLeft="1px solid #e4e4e4";
       }

    },
    methods: {
        tab(index) {
            this.num = index;
            this.addrSelected=0;
            this.isShow=true;
            this.isHide=false;
            this.muname=this.$refs.inputname.value=this.tabs[this.num].name;
            this.inputh5=this.$refs.h5.value=this.tabs[this.num].maintype.h5;
            this.type=this.tabs[this.num].maintype.type;



            var alsubtype=this.$refs.allsubtype.querySelectorAll('.subtype');
             for (let i=0;i<alsubtype.length;i++){
                var fortype=alsubtype[i].getAttribute("class")
                if(fortype.indexOf(this.type)>=0){
                    alsubtype[i].style.display="block";
                    this.addrSelected=i;
                }else{
                     alsubtype[i].style.display="none";
                }
            }
        }
        ,subtabs(inx){       
         var alsubtype=this.$refs.allsubtype.querySelectorAll('.subtype');
            for (let i=0;i<alsubtype.length;i++){
                if(i==inx){
                    alsubtype[i].style.display="block";
                }else{
                     alsubtype[i].style.display="none";
                }
            }
        }
        ,addsubck(){
            alert(1234)
        }
        ,addmenu(){
         var alsubtype=this.$refs.allsubtype.querySelectorAll('.subtype')
          this.isShow=true;
          this.isHide=false;
          this.muname="";
          alsubtype[0].style.display="block";
        }
        ,preview(){
          let itemjson={};
          itemjson.name=this.$refs.inputname.value;
          this.tabs.push(itemjson);
          this.addshow=!this.addshow;
          this.num=this.tabs.length-1;
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
