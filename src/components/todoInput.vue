<template>
<div class="todo-input mt-4">
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-6">
                <div class="input-group mb-3">
                    <input v-model="newTodo" type="text" 
                    class="form-control" 
                    placeholder="Enter a new Task" 
                    @keyup.enter="addTodo" />
                    <button @click="addTodo" class="btn btn-primary">Add</button>
                </div>
            </div>
        </div>
    </div>

</div>
</template>

<script>
export default {
    name: 'TodoInput',
    data() {
        return {
            newTodo: ''
        };
    },
    methods:{
        addTodo(){
            //console.log(this.newTodo);
            
            if(this.newTodo.trim() !==''){
                this.$emit('add-todo', this.newTodo);
                this.newTodo='';
            }else{
                alert('please enter a task')
            }
        }
    }
}
</script>
