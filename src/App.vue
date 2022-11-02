<template>
  <div>
    <input type="text" v-model="name">
    <GreetComp :name="name" :position="position" />
    <ArticleComp id="title" :title="title"/>
    <h2>Logged: {{loggedUser}}</h2>
    <CompA />
    <button @click="showPopup = true" v-show="!showPopup">Open Popup</button>
    <PopupComp v-show="showPopup" @close="closePopup" />
    <InputComp v-model="name" />
    <CardComp>
      <template v-slot:header>
      Não adianta fugir...
    </template>
    <template v-slot:default><img class="chuck" src="https://upload.wikimedia.org/wikipedia/commons/b/b1/Chuck_Norris%2C_The_Delta_Force_1986.jpg"/></template>
    <template v-slot:footer>
        Ele vai te pegar
    </template>
  </CardComp>
  <NameList>
    <template v-slot:default="slotProps">
       {{slotProps.lastName}}, {{slotProps.firstName}}
    </template>
  </NameList>
  <button @click="activeTab='TabA'">Tab A</button>
  <button @click="activeTab='TabB'">Tab B</button>
  <button @click="activeTab='TabC'">Tab C</button>
  <keep-alive>
    <component :is="activeTab"/>
  </keep-alive>
  <teleport to="#portal-root">
    <PortalComp />
  </teleport>
  <PostList />
  </div>
  <PostComp />
</template>

<script>
import GreetComp from './components/GreetComp.vue';
import ArticleComp from './components/ArticleComp.vue';
import CompA from './components/CompA.vue';
import PopupComp from './components/PopupComp.vue';
import InputComp from './components/InputComp.vue'
import CardComp from './components/CardComp.vue';
import NameList from './components/NameList.vue';
import TabA from './components/TabA.vue'
import TabB from './components/TabB.vue'
import TabC from './components/TabC.vue'
import PortalComp from './components/PortalComp.vue';
import PostList from './components/PostList.vue';
import PostComp from './components/PostComp.vue';

export default {
  name: 'App',
  components:{
    GreetComp,
    ArticleComp,
    CompA,
    PopupComp,
    InputComp,
    CardComp,
    NameList,
    TabA,
    TabB,
    TabC,
    PortalComp,
    PostList,
    PostComp
  },
  data(){
    return {
      name: 'Filisberto',
      position: 'feliz',
      title: 'Title',
      loggedUser: 'Joe',
      showPopup: false,
      activeTab: 'TabA'
    }
},
  provide(){
    return {
    loggedUser: this.loggedUser
    }
  },
  methods:{
    closePopup(name){
      this.showPopup = false
      alert(name)
    }
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.chuck {
  width: 200px
}
</style>
