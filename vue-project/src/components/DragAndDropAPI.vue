<script setup>
import { ref, onMounted } from 'vue'
const dragSource = ref(null)
// onMounted(() => {
//     console.log('DOM Box1：', dragSource.value);
// })
const clickEven = () => {
    console.log('click')
}
const dragstartEven = () => {
    console.log('dragstart')
}

const dragEven = () => {
    console.log('drag')
}

const dragenterEven = () => {
    console.log('dragenter')
}

const dragoverEven = () => {
    console.log('dragover')
}

const dragleaveEven = () => {
    console.log('dragleave')
}
const dropEven = () => {
    console.log('drop')
}
const dragendEven = () => {
    console.log('dragend')
}
</script>

<template>
    <div id="drag-drop-basic">
        <div id="source-container" data-role="drag-drop-container">
            <div id="drag-source" draggable='true' ref="dragSource" @click="clickEven" @dragstart="dragstartEven"
                @drag.once="dragEven" @dragenter="dragenterEven" @dragleave="dragleaveEven" @dragend="dragendEven"
                @dragover="dragoverEven" @drop="dropEven">
            </div>
            <!-- 針對能夠被拖曳的元素，在其 HTML 標籤上添加屬性 draggable="true"： -->

        </div>
        <div id="target-container" data-role="drag-drop-container"></div>

    </div>
</template>

<style lang="scss" scoped>
[draggable="true"] {
    /*
   To prevent user selecting inside the drag source
  */
    user-select: none;
    -moz-user-select: none;
    -webkit-user-select: none;
    -ms-user-select: none;
}

#drag-drop-basic {
    display: flex;

    #source-container {
        width: 400px;
        height: 400px;
        border: 2px solid #CCC;
        flex: 1;
        margin: 1rem;
    }

    #target-container {
        width: 400px;
        height: 400px;
        border: 2px solid #CCC;
        flex: 1;
        margin: 1rem;
    }

    #drag-source {
        width: 100px;
        height: 100px;
        border-radius: 50%;
        background-color: steelblue;
    }
}

// End of Drag and Drop Basic
</style>


 <!-- [筆記] 製作可拖曳的元素（HTML5 Drag and Drop API）
https://pjchender.blogspot.com/2017/08/html5-drag-and-drop-api.html -->


<!-- HTML 屬性
data-role="drag-drop-container"
draggable='true' -->

<!-- 
拖曳對象事件 
dragstart	
drag	
dragend


拖曳對象事件 & 拖曳目標事件 
dragenter
dragleave
dragover


拖曳目標事件 
drop
針對要被置放的容器 dropTarget 監聽 drop 事件，來處理當使用者放掉的時候要執行的行為，並透過 getData 來取得傳遞的資料；監聽 dragenter 和 dragover 事件來避免預設行為 -->


<!-- =============================================== -->
<!-- DataTransfer -->
<!-- https://developer.mozilla.org/zh-TW/docs/Web/API/DataTransfer -->

<!-- 就是要一起拖拖拉拉！(二) - 利用 DataTransfer API 實作拖拉元素間的資料傳遞 -->
<!-- https://www.muji.dev/2020/03/07/web-dnd-2/ -->
