<template>
    <button id="counter" @click="increment">
        ref | {{ count }}
    </button>
    <button @click="state.count++">
        reactive | {{ state.count }}
    </button>
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
  