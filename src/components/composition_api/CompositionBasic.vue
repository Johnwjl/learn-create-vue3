<template>
    <div class="case">
        <div class="case-title">
            CompositionBasic.vue
            | 本例参阅：
            <a href="https://cn.vuejs.org/guide/essentials/reactivity-fundamentals.html" target="_blank" rel="noopener noreferrer">响应式基础</a>
        </div>
        <div>
            涉及API:
            <a href="https://cn.vuejs.org/api/sfc-script-setup.html" target="_blank" rel="noopener noreferrer">script-setup</a>、
            <a href="https://cn.vuejs.org/api/reactivity-core.html#ref" target="_blank" rel="noopener noreferrer">ref()</a>、
            <a href="https://cn.vuejs.org/api/reactivity-core.html#reactive" target="_blank" rel="noopener noreferrer">reactive()</a>、
            <a href="https://cn.vuejs.org/api/general.html#nexttick" target="_blank" rel="noopener noreferrer">nextTick()</a>
            
        </div>
        <div>
            <div>Demo:</div>
            <button id="counter" @click="increment">
                ref | {{ count }}
            </button>
            <button @click="state.count++">
                reactive | {{ state.count }}
            </button>
        </div>
    </div>
</template>
  
<script setup>
    import { ref, reactive, onMounted, nextTick } from 'vue';

    // 使用 ref 创建一个响应式的引用
    const count = ref(0);

    // 定义一个方法来增加 count 的值
    const increment = async () => {
        count.value++;

        // DOM 还未更新
        console.log(document.getElementById('counter').textContent) // 0

        await nextTick()

        // DOM 此时已经更新
        console.log(document.getElementById('counter').textContent) // 1

    };

    //
    const state = reactive({count: 0});

    // 在组件挂载时执行的逻辑
    onMounted(() => {
        console.log('CompositionBasic.vue | Component is mounted!');
    });
</script>

<style scoped>
    #counter {
        margin-right:10px;
    }
</style>
  