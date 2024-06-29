<template>
    <div>01:</div>
    <div>是否还有书籍: {{ publishedBooksMessage }} ，库存：{{ author.books.length }} 本 </div>
    <button @click="operate"> {{ publishedBooksOperate }} </button>
    <div>02: 修改computed的值，从而更新依赖项</div>
    <div>
        <input v-model="fullName" />
        <div>
            <div>First-Name: {{firstName}}</div>
            <div>Last-Name: {{lastName}}</div>
        </div>
    </div>
</template>
  
<script setup>
    import { ref, reactive, computed } from 'vue';

    // demo 01

    const books = [
            'Vue 2 - Advanced Guide',
            'Vue 3 - Basic Guide',
            'Vue 4 - The Mystery'
        ]

    const author = reactive({
        name: 'John Doe',
        books
    })

    // 一个计算属性 ref
    const publishedBooksMessage = computed(() => {
        return author.books.length > 0 ? 'Yes' : 'No'
    })

    const publishedBooksOperate = computed(() => {
        return author.books.length > 0 ? '清空' : '恢复'
    })

    const operate = () => {
        author.books = author.books.length > 0 ? [] : books
    }

    // demo 02

    const firstName = ref("John");
    const lastName = ref("Doe");

    const fullName = computed({
        // getter
        get() {
            return firstName.value + ' '+ lastName.value;
        },
        // setter
        set(newValue) {
            console.log("newValue", newValue)
            // 注意：我们这里使用的是解构赋值语法
            if (typeof newValue === 'string' && newValue.includes(' ')) {
                [firstName.value = "", lastName.value = ""] = newValue.split(' ');
            }
        }
    })

</script>

<style scoped>
    
</style>
  