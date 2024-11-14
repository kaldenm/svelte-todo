<script>
    import TodoForm from "../../components/dashboard/TodoForm.svelte"
    import TodoList from "../../components/dashboard/TodoList.svelte"


    // State 

    let todoInput = ''


    let todoList = [ 
        {
            text: "Buy more milk",
            status: true

        },
        {
            text: "Buy ramen",
            status: false 
        }
    ]

    function addToList() {
        console.log()
        todoList = [
            { text: todoInput, status: true },
            ...todoList
        ]
        todoInput = '';
    }

    function removeFromList(i) {
        todoList.splice(i, 1)

        todoList = todoList

    }




</script>

   
<div class="flex min-h-full flex-col justify-center px-6 py-12 lg:px-8">
    <div class="sm:mx-auto sm:w-full sm:max-w-sm">
      <h2 class="mt-10 text-center text-2xl/9 font-bold tracking-tight text-gray-900">Welcome to Todo List</h2>
    </div>
  
    <div class="mt-10 sm:mx-auto sm:w-full sm:max-w-sm">
      <form class="mt-8 space-y-6" on:submit={(e) => {
        e.preventDefault();
        addToList();
      }}>
        <div>
          <label for="todo-input" class="block text-sm/6 font-medium text-gray-900"></label>
          <div class="mt-2">
            <input 
                bind:value={todoInput}
            id="todo-input" 
            name="email" 
            type="text" 
            required class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm/6"
            placeholder="Enter todo"
            />
          </div>
        </div>
    
        <div>
          <button type="submit" class="flex w-full justify-center rounded-md bg-indigo-600 px-3 py-1.5 text-sm/6 font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">Add Todo</button>
        </div>
      </form>
    </div>
</div>
  
    <TodoList todos={todoList} removeFromList={removeFromList}/>
   