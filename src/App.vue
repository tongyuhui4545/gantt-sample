<template>
  <div id="app" class="container">
    <header class="header">
      <div class="tabs">
        <ul>
          <li><a>Gantt1</a></li>
          <li><a>Gantt2</a></li>
          <li><a>Gantt3</a></li>
          <li><a>Gantt4</a></li>
          <li><a>Gantt5</a></li>
        </ul>
      </div>
    </header>
    <div class="container">
      <GanttChart class="left-container" :tasks="tasks"></GanttChart>
    </div>
  </div>
</template>

<script>
import GanttChart from './components/GanttChart.vue'

export default {
  name: 'App',
  components: {
    GanttChart
  },
  data() {
    return {
      tasks: {
        data: [
          { id: 1, text: 'Task #1', start_date: '2020-01-17', duration: 3, progress: 0.6 },
          { id: 2, text: 'Task #2', start_date: '2020-01-20', duration: 3, progress: 0.4 }
        ],
        links: [
          { id: 1, source: 1, target: 2, type: '0' }
        ]
      },
    }
  }
}
</script>

<style>
html,
body {
  height: 100%;
  margin: 0;
  padding: 0;
}

.header {
  background-color: #f0f0f0;
  padding: 10px;
  display: flex;
  /* 使用flex布局使子元素水平排列 */
  justify-content: space-between;
  /* 水平分散对齐 */
  align-items: center;
  /* 垂直居中对齐 */
}

/* Tabs样式 */
.tabs ul {
  list-style: none;
  padding: 0;
  display: flex;
  /* 使用flex布局使选项卡水平排列 */
}

.tabs li {
  margin-right: 10px;
}

.container {
  height: 100vh;
  width: 100%;
}

.left-container {
  overflow: hidden;
  position: relative;
  height: 100%;
}</style>
