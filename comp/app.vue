Vue.component('App',{
    props : [],
    data : function(){
        return {
            color: 'is-link',
        }
    },
    template : `<div>
        <Header v-bind:headercolor="color"/>
        <Body/>
    </div>`,
})
