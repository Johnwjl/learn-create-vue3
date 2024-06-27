<template>
    <div class="case">
        <div class="case-title">
            ComputedDemo.vue
            | 本例参阅：
            <a href="https://cn.vuejs.org/guide/essentials/computed.html" target="_blank" rel="noopener noreferrer">计算属性</a>
        </div>
        <div>
            涉及API:
            <a href="https://cn.vuejs.org/api/sfc-script-setup.html" target="_blank" rel="noopener noreferrer">script-setup</a>、
            <a href="https://cn.vuejs.org/api/reactivity-core.html#ref" target="_blank" rel="noopener noreferrer">ref()</a>、
            <a href="https://cn.vuejs.org/api/reactivity-core.html#reactive" target="_blank" rel="noopener noreferrer">reactive()</a>、
            <a href="https://cn.vuejs.org/api/general.html#nexttick" target="_blank" rel="noopener noreferrer">nextTick()</a>
            
        </div>
        <div>
            <div>
                <div>Demo 01:</div>
                <div>是否还有书籍: {{ publishedBooksMessage }} ，库存：{{ author.books.length }} 本 </div>
                <button @click="operate"> {{ publishedBooksOperate }} </button>
            </div>
            <div>
                <div>Demo 02: 修改computed的值，从而更新依赖项</div>
                <div>
                    <input v-model="fullName" />
                    <div>
                        <div>First-Name: {{firstName}}</div>
                        <div>Last-Name: {{lastName}}</div>
                    </div>
                </div>
            </div>
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
  