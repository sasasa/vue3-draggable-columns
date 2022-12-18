<template>
  <div class="container">
    <div id="box1" class="box">
      <draggable v-model="items1" item-key="no" tag="ul" group="ITEMS">
        <template v-slot:item="{ element, index }">
          <li>{{ element.name }}-(No.{{ element.no }})</li>
        </template>
      </draggable>
    </div>
    <div id="box2" class="box">
      <draggable v-model="items2" item-key="no" tag="ul" group="ITEMS">
        <template v-slot:item="{ element, index }">
          <li>{{ element.name }}-(No.{{ element.no }})</li>
        </template>
      </draggable>
    </div>
    <div id="box3" class="box">
      <draggable v-model="items3" item-key="no" tag="ul" group="ITEMS">
        <template v-slot:item="{ element, index }">
          <li>{{ element.name }}-(No.{{ element.no }})</li>
        </template>
      </draggable>
    </div>

    <div class="box">
      <code>
        <pre>{{ items1 }}</pre>
      </code>
    </div>
    <div class="box">
      <code>
        <pre>{{ items2 }}</pre>
      </code>
    </div>
    <div class="box">
      <code>
        <pre>{{ items3 }}</pre>
      </code>
    </div>
  </div>
</template>

<script setup>
import draggable from "vuedraggable";
import { ref } from "vue";

const items1 = ref([
  { no: 1, name: "キャベツ", categoryNo: "1" },
  { no: 2, name: "ステーキ", categoryNo: "2" },
]);
const items2 = ref([
  { no: 5, name: "きゅうり", categoryNo: "1" },
  { no: 6, name: "ハンバーグ", categoryNo: "2" },
]);
const items3 = ref([
  { no: 7, name: "ごはん", categoryNo: "1" },
  { no: 8, name: "ぱん", categoryNo: "2" },
]);
</script>

<style>
.container {
  display: flex;
  flex-wrap: wrap;
}
.box {
  width: 32%;
  padding: 20px 0;
}
#box1 {
  background-color: #fdd;
}
#box2 {
  background-color: #ddf;
}
#box3 {
  background-color: #dfd;
}
ul {
  list-style-type: none;
  padding-right: 2rem;
}
li {
  cursor: pointer;
  padding: 10px;
  border: solid #ddd 1px;
  background-color: #fff;
}
</style>
