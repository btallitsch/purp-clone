<template>
  <div>
    <div class="field is-grouped">
      <p class="control">
        <a v-on:click="back" class="button is-primary">
          Back
        </a>
      </p>
      <p class="control">
        <a v-on:click="addTask" class="button">
          Add Task
        </a>
      </p>
<!--       <p class="control">
        <a class="button is-danger">
          Delete post
        </a>
      </p> -->
    </div>
<!--     <router-link to="/">Back</router-link>
    <button class="button is-primary is-medium">Add Task</button> -->
<!--     <br>
    <br> -->
    <div class="box">
      <article class="media">
        <div class="media-content">
          <div class="content">
            <p>
              <strong>{{ this.projects[$route.params.id].name }}</strong>
              <br>
              <small>{{ this.projects[$route.params.id].percent }}%</small>
              <br>
              <progress class="progress is-primary" :value="this.projects[$route.params.id].percent" max="100"></progress>
            </p>

            <b-checkbox-group v-model="checkboxGroup">
              <div class="field" v-for="task in this.projects[$route.params.id].tasks">
                  <b-checkbox :custom-value="task.id" v-on:change="updatePercent(task)">{{ task.name }}</b-checkbox>
              </div>
            </b-checkbox-group>
            <br>
            <p>{{ this.projects[$route.params.id].tasks.length }}</p>
            <p class="content"><b>Selection:</b> {{ checkboxGroup }}</p>

          </div>
        </div>
      </article>
    </div>
  </div>
</template>

<script>
  import data from '../data'
  // import { find } from 'lodash'
  export default {
    data () {
      return {
        // project: null
        // 'tasks': data.projects.tasks,
        newTask: "",
        'projects': data.projects,
        checkboxGroup: []
      }
    },
    props: ['myMessage'],
    methods: {
      back() {
        this.$router.push({name: 'home'}); 
      },
      addTask() {
        //create new task here
        console.log('add task - this is buggy')
        // var task = this.newTask.trim();
        // if (task) {
          //Push an object containing the task to the taskList array
          data.projects[0].tasks.push({
            id: 2,
            name: 'task',
            description: ''
          });
          //Reset newTask to an empty string so the input field is cleared
          // this.newTask = '';
        // }
        // this.projects[0].tasks.push({id: 2, name: 'asdasd', description: 'asdASdASdASd' });
      },
      updatePercent: function (task) {
        var tasksNum = data.projects[0].tasks.length
        var pcent = data.projects[0].percent
        //get total number of tasks for this project
        console.log(tasksNum, pcent, task.name)
        // total = checked/total tasks

        data.projects[0].percent = (1/2)*100;
      }
    },
    mounted () {
      // if (navigator.onLine) {
        // this.project = find(this.$root.project, (project) => project['.key'] === this.$route.params.id)
      // } else {
        // this.project = JSON.parse(localStorage.getItem('project'))[this.$route.params.id]
      // }
    }
  }
</script>

<style scoped>

  .progress {
    margin-top: 8px;
  }

</style>
