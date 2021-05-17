Vue.component('Header',{
    props : ['headercolor'],
    data : function(){
        return {
            color : {
                header : this.headercolor +'button is-rounded is-inverted',
            },
            notSearching:true,
            menuBar : false,
            editing : false,
            selecting : false,
        }
    },
    template:`<div>
<nav class="navbar has-shadow">
<div v-if="!editing" class="navbar-brand mx-2">
    
    <!-- menu tag-->
    <div v-on:click="menuBar = !menuBar " v-if="notSearching" v-bind:class="color.header+' has-dropdown' " class="nav-r navbar-item is-hoverable">
        <img  class="icon" src="../res/svg/list-ul-solid.svg" alt="menu" />
        <div v-bind:class="{'is-hidden': !menuBar}">menuBar</div>
    </div>
    
    <!--  this is the back button -->
     <div v-on:click="notSearching = true" v-else v-bind:class="color.header" class="nav-back navbar-item">
        <img  class="icon" src="" alt="back" />
     </div>
     
    <!--   home/user clicking on it takes you to user profile  -->
    <div v-bind:class="{'$notSearching  ' :notSearching, 'is-hidden':!notSearching}" class="nav-r navbar-item">
         <img  class="" src="" alt="user" />
    </div>

    <!--  search -->  
    <div v-on:click="notSearching = false" v-bind:class="color.header" v-if="notSearching" class="nav-l navbar-item">
          <img class="icon"  src="../res/svg/search-solid.svg" alt="search" />
    </div>
  
    <div v-else class="nav-search navbar-item">
            <input  class=" input is-rounded" alt="input" type="search" name="search" id="search" placeholder="search"/>
    </div>

    <!-- camera use the navigator module  -->
    <div  v-bind:class="{'button is-link is-rounded is-inverted nav-l':notSearching, 'is-hidden':!notSearching }" class="navbar-item">
        <img class="icon" src="../res/svg/camera-retro-solid.svg" alt="camera" />
    </div>

</div>
<div v-else>
    <!-- while i long click it enters editing mode
    there are two editing mode 
    
    1. when i get editing uption like selecting
    2. when i am selecting i get options like select all select interval etc-->
    <div v-if="selecting" class="navbar-brand mx-2">
        selecting
    </div>
    <div v-else class="navbar-brand mx-2">
        editing
    </div>
</div>

<div v-bind:class="{'is-hidden': !menuBar}">
    <hr class="has-outline my-0" />
    <Menu class="navbar pt-0 mt-0"/>
</div>

</nav>
</div>`
})





/*     <div class="nav-a"><div class="navbar-item button" v-bind:class ="color.header" >
            <img class="icon" src="../res/svg/list-ul-solid.svg" alt="menu" />
        </div>
    </div> 
    <div class="nav-a">
        <div class="navbar-item nav-m" >
            <div class="button" v-bind:class ="color.header">b</div>
        </div>
    </div>
    
    <div class="nav-a navbar-item">
        <div class="nav-r button" v-bind:class ="color.header" >
                <img src="../res/svg/search-solid.svg" class="icon" ></img>
        </div>
        <div class="nav-r button" v-bind:class="color.header">
            <img src="../res/svg/camera-retro-solid.svg" class="icon"></img>
        </div>
    </div>
</div>
*/

