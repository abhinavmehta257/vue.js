<template >
  <div id="app">
    <h1 align='center'>{{title}}</h1>
    <div class="container">
      <button class="btn btn-outline-success col-md-12" name="button" @click='addNewMember'>Add New Member</button>
      <div class="row">
        <character v-for='id in initial_ids' :id='id'/>
      </div>
    </div>

  </div>
</template>

<script type="text/javascript">
  import character from './components/charecter.vue'
  export default{
    name: 'app',
    data(){
      return{
        title: 'Generate Your Team',
        initial_ids: [1, 13, 14]
      }
    },
    methods:{
      addNewMember(){
        var new_id = Math.floor(Math.random()*81)+1
        this.initial_ids.push(new_id)
      }
    },
    components:{
      character
    }
  }
</script>
