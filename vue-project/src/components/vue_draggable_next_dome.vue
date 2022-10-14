<script setup>
import { ref, computed } from 'vue'
import draggable from 'vuedraggable'
let id = 1

const name = "simple"
const display = "Simple"
const order = 0
const components = {
    draggable: true
}
const enabled=ref(false)
const list = ref([
    { name: "John", id: 0 },
    { name: "Joao", id: 1 },
    { name: "Jean", id: 2 }
])
const dragging = ref(false)

const add = () => {
    list.value.push({ name: "Juan " + id, id: id++ })
}

const replace = () => {
    list.value = [{ name: "Edgard", id: id++ }];
}
const checkMove = (e) => {
    window.console.log("Future index: " + e.draggedContext.futureIndex);
}

const draggingInfo = computed(() => {
    return dragging.value ? "under drag" : "";
})
</script>

<template>
    <div class="row">
        <div class="col-2">
            <div class="form-group">
                <div class="btn-group-vertical buttons" role="group" aria-label="Basic example">
                    <button class="btn btn-secondary" @click="add">Add</button>
                    <button class="btn btn-secondary" @click="replace">Replace</button>
                </div>

                <div class="form-check">
                    <input id="disabled" type="checkbox" v-model="enabled" class="form-check-input" />
                    <label class="form-check-label" for="disabled">DnD enabled</label>
                </div>
            </div>
        </div>

        <div class="col-6">
            <h3>Draggable {{ draggingInfo }}</h3>

            <draggable :list="list" :disabled="!enabled" item-key="name" class="list-group" ghost-class="ghost"
                :move="checkMove" @start="dragging = true" @end="dragging = false">
                <template #item="{ element }">
                    <div class="list-group-item" :class="{ 'not-draggable': !enabled }">
                        {{ element.name }}
                    </div>
                </template>
            </draggable>
        </div>

        <rawDisplayer class="col-3" :value="list" title="List" />
    </div>
</template>


<style scoped>
.buttons {
    margin-top: 35px;
}

.ghost {
    opacity: 0.5;
    background: #c8ebfb;
}

.not-draggable {
    cursor: no-drop;
}
</style>
