.<template>
  <div class="container">
      <h2 class="text-center mt-5">Ma Todo App</h2>
  

<!-- Input -->

<div class="d-flex">
    <input v-model="task" type="text" class="form-control" placeholder="Nouvelle tâche">
<button @click="submitTask" class="btn btn-warning rounded-0">VALIDER</button>
</div>


<!-- task table -->

<table class="table table-bordered mt-5">
  <thead>
    <tr>
      <th scope="col">Name</th>
      <th scope="col">Status</th>
      <th scope="col" class="text-center">#</th>
      <th scope="col" class="text-center">#</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="(task, index) in tasks" :key="index">
      <th>{{task.name}}</th>
      <td>{{task.status}}</td>
      <td>
        <div class="text-center">
          <span class="fa fa-pen"></span>
        </div>
      </td>
      <td>
        <div class="text-center">
          <span class="fa fa-trash"></span>
        </div>
      </td>
    </tr>
    
  </tbody>
</table>

</div>

</template>

<script>
export default {
    name: 'TodoApp',
    props:{
      msg: String,
    },

data(){
  return{
    task: '',
    tasks: [
      {
        name: 'Steal bananas',
        status: 'to-do',
      },
      {
        name: 'Eat 1 kg chocolat',
        status: 'in-progress',
      }
    ]
    }
},

methods: {
  submitTask(){
    if(this.task.length === 0) return;
    this.tasks.push({name: this.task, status: 'to-do' })
}
}

}
</script>

<style>

</style>