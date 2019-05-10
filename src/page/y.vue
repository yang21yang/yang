<template>
    <div id="app">
        <ul :v-for="(item,index) in lidata">
            <li><span :class="{active:index==isActive}"  @click="changeClass(index)"> {{item.name}}
            </span></li> 
        </ul>
        
        <!--实现多选：

        <ul v-for="(item,index) in lidata">
        <li><span :class="{active:item.checked}"  @click="changeClass(item)"> {{item.name}}</span>
        </li> -->

        <div>Creating a new branch is quick.</div>
    </div>
</template>
<script>
    export default {
        data(){
            return{
                isActive:-1,
                lidata:[
                {index:0,name:'健康医疗'},
                {index:1,name:'生活服务'},
                {index:2,name:'旅游'},
                {index:3,name:'金融'},
                {index:4,name:'信息安全'},
                {index:5,name:'广告营销'},
                {index:6,name:'数据服务'},
                {index:7,name:'智能硬化'},
                {index:8,name:'文化娱乐'},
                {index:9,name:'网络招聘'},
                {index:10,name:'分类信息'},
                {index:11,name:'电子商务'},
                {index:12,name:'移动互联网'},
                {index:13,name:'企业服务'},
                {index:14,name:'社交网络'}
                ]
                }
        },
            
            changeClass(index){
            this.isActive=index;
        },
        changeClass(item){
            if(typeof item.checked=='undefined'){
                this.$set(item,"checked",true)
            }else{
            item.checked=!item.checked
            }
            },
            
        //限制三次：
            changeClass(item){
                let a=document.getElementsByClassName('active'); 
            if(typeof item.checked=='undefined'){
                if(a.length<=3){
                this.$set(item,"checked",true); 
            }else{
                alert(2222222222)
            }  
            }else{
            item.checked=!item.checked; 
            }
            },



            // methods:{
            //     beforeAvatarUpload(){
            //         console.log('上传前的对象')
            //         const isSize = new Promise(function(resolve, reject) {
            //         let width = 100;
            //         let height = 100;
            //         let _URL = window.URL || window.webkitURL;
            //         let img = new Image();
            //         img.onload = function() {
            //         let valid = img.width == width && img.height == height;
            //         valid ? resolve() : reject();
            //         } 
            //         }).then(() => {
            //         return file;
            //         }, () => {
            //         console.log('图片大小不能超过100成语100')
            //         return Promise.reject();
            //         });
            //         return isSize
            //         },
            //     }
            
    }
</script>
<style>

</style>
