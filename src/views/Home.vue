<template>
 <div id="app">
   <div class="container">
     <div class="card">
       <p class=title>Todo List</p>
       <div class=todo>
         <form class="flex" action="送信先" method="post">
           <input class="input-add" type="text" name="名前" value="送信されるデータ" v-model="todo">
           <button class="button-add" type="submit" @click="add">追加</button>
         </form>
         <form class="flex"  action="受取先" method="put">
           <input class="input-update" type="text"> 
           <button class="button-update" @click="updateTodo(todo)">更新</button>
           <button class="button-delete" @click="deleteTodo(todo)">削除</button>
         </form>
       </div>
     </div>
   </div>
 </div>
</template>  

<script>
export default {
 data(){
   return {
     todo: "",

     editIndex: -1, 

    items: [       
        "タスク１",
        "タスク２",
        "タスク３"
    ]
   };
 },
 methods:{
   button-add: function() {
     this.items.push({
       text: this.addText,
       check: false,
       dueDate: this.addDate,
     });
     this.addText = "";
     this.addDate = null;
   },
   updateTodo(todo) {
        this.updateIndex = index;
        this.text = this.items[index];
        this.$refs.editor.focus();
   },
   deleteTodo: function (todo) {
     this.todos.splice(this.todos.indexOf(todo), 1)
    }
 }
}
</script>

<style scoped>
.container{
  background-color:#2d197c ;
  height: 100vh;
  width: 100vw;
  position: relative;
}

.card{
  background-color: #fff;
  width: 50vw;
  padding: 30px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  border-radius: 10px;
}
.title {
  font-weight: bold;
  font-size: 24px;
}
.input-add{
  width: 80%;
  padding: 5px;
  border-radius: 5px;
  border: 1px solid #ccc;
  -webkit-appearance: none;
     -moz-appearance: none;
          appearance: none;
  font-size: 14px;
  outline: none;
}
.input-update{
  width: 30%;
  padding: 5px;
  border-radius: 5px;
  border: 1px solid #ccc;
  -webkit-appearance: none;
     -moz-appearance: none;
          appearance: none;
  font-size: 14px;
  outline: none;
}
.button-add{
  text-align: left;
  border: 2px solid #dc70fa;
  font-size: 12px;
  color: #dc70fa;
  background-color: #fff;
  font-weight: bold;
  padding: 8px 16px;
  border-radius: 5px;
  cursor: pointer;
  transition: 0.4s;
  outline: none;
}
.button-add:hover {
  background-color: #dc70fa;
  border-color: #dc70fa;
  color: #fff;
}
.button-update{
  text-align: left;
  border: 2px solid #fa9770;
  font-size: 12px;
  color: #fa9770;
  background-color: #fff;
  font-weight: bold;
  padding: 8px 16px;
  border-radius: 5px;
  cursor: pointer;
  transition: 0.4s;
  outline: none;
}
.button-update:hover {
  background-color: #fa9770;
  border-color: #fa9770;
  color: #fff;
}
.button-delete{
  text-align: left;
  border: 2px solid #71fadc;
  font-size: 12px;
  color: #71fadc;
  background-color: #fff;
  font-weight: bold;
  padding: 8px 16px;
  border-radius: 5px;
  cursor: pointer;
  transition: 0.4s;
  outline: none;
}
.button-delete:hover {
  background-color: #71fadc;
  border-color: #71fadc;
  color: #fff;
} 
.flex{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin: 10px; 
}
.button-update{
  margin-right: 5px;
}
</style>

