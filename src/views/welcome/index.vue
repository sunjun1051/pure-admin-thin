<template>
  <div>
    <el-table :data="tableData" style="width: 100%">
      <el-table-column prop="date" label="Date" sortable width="180" />
      <el-table-column prop="name" label="Name" width="180" />
      <el-table-column prop="address" label="Address" :formatter="formatter" />
    </el-table>
    <el-button @click="add">加</el-button>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import type { TableColumnCtx } from 'element-plus/es/components/table/src/table-column/defaults'
interface User {
  date: string
  name: string
  address: string
}
defineOptions({
  name: 'Welcome'
})
const formatter = (row: User, _: TableColumnCtx<User>) => {
  return row.address
}

const userList: User[] = [
  {
    date: '2016-05-03',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles'
  },
  {
    date: '2016-05-02',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles'
  },
  {
    date: '2016-05-04',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles'
  },
  {
    date: '2016-05-01',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles'
  }
]
const tableData = ref(userList)
const add = () => {
  tableData.value.push({
    date: '2022-05-03',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles'
  })
  console.log(tableData)
}
</script>
