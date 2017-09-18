<template>
  <!-- <router-link to="/detail"> -->
  <div>
    <div v-for="project in this.projects" class="box" @click="displayDetails(project.id)">
      <article class="media">
        <div class="media-content">
          <div class="content">
            <p>
              <strong>{{ project.name }}</strong>
              <br>
              <small>{{ project.percent }}%</small>
              <br>
              <progress class="progress is-primary" :value="project.percent" max="100"></progress>
            </p>
          </div>
        </div>
      </article>
    </div>
  </div>
  <!-- </router-link> -->
</template>

<script>
  import data from '../data'
  export default {
    methods: {
      displayDetails (id) {
        this.$router.push({name: 'detail', params: { id: id }})
      }
    },
    data () {
      return {
        'projects': data.projects
      }
    }
  }
</script>

<style scoped>

  .progress {
    margin-top: 8px;
  }

  .box {
    cursor: pointer;
  }
/*  .add-picture-button {
    position: fixed;
    right: 24px;
    bottom: 24px;
    z-index: 998;
  }
  .image-card {
    position: relative;
    margin-bottom: 8px;
  }
  .image-card__picture > img {
    width:100%;
  }
  .image-card__comment {
    position: absolute;
    bottom: 0;
    height: 52px;
    padding: 16px;
    text-align: right;
    background: rgba(0, 0, 0, 0.5);
  }
  .image-card__comment > span {
    color: #fff;
    font-size: 14px;
    font-weight: bold;
  }*/
</style>
