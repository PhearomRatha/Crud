<script>
export default {
  data() {
    return {
      userName: "",
      txt: "watch",
      iterms: [],
      inputTask: "",
      taskId: 1,
      oldTask: null,
      newTask: null,
      firstName:"",
      lastName :""
    };
  },
  methods: {
    changeTxt() {
      this.txt = "watching...";
    },
    add() {
      if (this.inputTask.trim().length > 0) {
        this.oldTask = this.newTask;
        this.newTask = this.inputTask.trim();
        this.iterms.push({
          id: this.taskId++,
          name: this.inputTask.trim(),
        });
        console.log("New task added:", this.newTask);
        console.log("Old task:", this.oldTask);
        this.inputTask = "";
      }
    },
    del(task) {
      const index = this.iterms.findIndex((t) => t.id === task.id);
      if (index !== -1) {
        console.log("Removing task:", this.iterms[index]);
        this.iterms.splice(index, 1);
        if (this.iterms.length > 0) {
          this.newTask = this.iterms[this.iterms.length - 1].name;
          this.oldTask =
            this.iterms.length > 1 ? this.iterms[this.iterms.length - 2].name: null;
        } else {
          this.newTask = null;
          this.oldTask = null;
        }
        console.log("New task:", this.newTask);
        console.log("Old task:", this.oldTask);
      }
    },
  },
  watch: {
    userName(newVal, oldVal) {
      console.log("New:", newVal);
      console.log("Old:", oldVal);
    },
    iterms: {
      check(newValue, oldValue) {
        if (newValue.length > oldValue.length) {
          this.add();
        }
        if (newValue.length < oldValue.length) {
          const removedTask = oldValue.find(
            (task) => !newValue.some((newTask) => newTask.id === task.id)
          );
          if (removedTask) {
            this.del(removedTask);
          }
        }
      }
    },
    firstName(newName,oldName){
      console.log("newfirstName:",newName);
      console.log("oldfirstName:",oldName);
      

    },
    lastName(newName,oldName){
      console.log("newlastName:",newName);
      console.log("oldlastName:",oldName);
      

    }
  },
};
</script>


<template>
  <div>
    <p>{{ txt }}</p>
    <input type="text" v-model="userName" placeholder="Please input your name..." /><br><br>
    <input type="text" v-model="inputTask" placeholder="Add a new task..." />
    <button @click="add">Add Task</button>
    <ul>
      <li v-for="task in iterms" :key="task.id">
        {{ task.name }}
        <button @click="del(task)">Delete</button>
      </li>
    </ul>
  </div>
  <input type="text" v-model="firstName" placeholder="input first name"><br>
  <input type="text" v-model="lastName" placeholder="input last name">
</template>

<style scoped>


</style>
