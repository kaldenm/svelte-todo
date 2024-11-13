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
        console.log(todoInput)
        todoList = [
            { text: todoInput, status: true },
            ...todoList
        ]
    }

</script>


<div class="flex min-h-full flex-col justify-center px-6 py-12 lg:px-8">
    <div class="sm:mx-auto sm:w-full sm:max-w-sm">
        <TodoForm todoInput={todoInput} add={addToList}/>
        <TodoList todos={todoList}/>
    </div>
</div>