<template>
    <div>
        <UserCard
        ref="userCard"
        id="userCard"
        :user-photo="userPhoto"
        @getUserName="getUserName"
        />


            <!-- <input v-model="newTodo" type="text" placeholder="Add new item" />
            <button @click="addToDo">Add +</button>
            <ul>
                <li class="todo_item" v-for="todo in todoItems">
                    <p>{{ todo.name }}</p>
                    <p v-if="todo.date"> {{ todo.date }} </p>
                    <p v-else> N/A</p>
                    <p> {{ todo.isdone }} </p>
                    <label>
                        Mark as done
                        <input v-model="todo.isdone" type="checkbox">
                    </label>
                </li>
            </ul>
            <h2>Total {{ totalTodo }} stuffs</h2>
            <h2>You have to finish {{ unfinishedTasks }} tasks</h2> -->
    </div>
</template>

<script>
import UserCard from './components/UserCard.vue'

export default {
    name: 'CreditCardForm',
    components: {
        UserCard
    },
    data() {
        return {
            userPhoto: 'https://images.goodsmile.info/cgm/images/product/20211122/12031/92321/large/4d186c72d553b4120e130374b40f4ae5.jpg',
            userage: '',
            todoItems: [
                {
                    name: 'Drink beer',
                    date: '03-02-2002',
                    isdone: false
                },
                {
                    name: 'Drink milk',
                    date: '03-02-2002',
                    isdone: false
                },
                {
                    name: 'Drink water',
                    date: '03-02-2002',
                    isdone: true
                },
                {
                    name: 'Drink gas',
                    date: '03-02-2002',
                    isdone: true
                }
            ],
            newTodo: ''
        }
    },
    mounted() {
        this.getElement();
    },
    methods: {
        addToDo() {
            const todoObj = {
                name: this.newTodo,
                isdone: false
            }

            this.todoItems.push(todoObj);
            this.newTodo = '';
        },
        getUserName(name) {
            // console.log(name);
        },
        getElement() {
            // const el = document.getElementById('userCard');
            console.log(this.$refs.userCard.showInfo());
        }
    },
    computed: {
        totalTodo() {
            return this.todoItems.length;
        },
        unfinishedTasks() {
            return this.todoItems.filter(el => !el.isdone).length;
        }
    }
}
</script>

<style lang="scss" src="./style.scss">

</style>