Vue.component('Box', {
    props:['user'],
    data:function(){
        return {}
    },
    methods :{
        a : function(){},
    } ,
    template:`<div>
        <div class="box mb-1 has-shadow">
            <video class="video" src="" height="" width="" preload="none" autoplay="autoplay"></video>
            <hr class="has-outline my-0" />
            <div v-on:keydown="console.log('down')" v-on:key="console.log('up')">
            <div>{{user}}</div><div>message</div>
            </div>
        </div>
    </div>`
})



Vue.component('Body', {
    props:[],
    data:function(){
        return {
           users :[1] 
        }
    },
    template:`<div>
        <Box user="you"/>
        <div v-for=" user in users">
            <Box v-bind:user="user"/>
        </div>
    </div>`
})