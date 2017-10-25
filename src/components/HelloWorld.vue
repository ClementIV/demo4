<template>
<div id="app2">
  <el-table
    :data="tableData2"
    height="600"
    border
    style="width: 100%"
    >
    <el-table-column
      prop="CID"
      label="编号"
     >
    </el-table-column>
    <el-table-column
      prop="CourseName"
      label="课程名称"
     >
    </el-table-column>
    <el-table-column
      prop="Type"
      label="类型">
    </el-table-column>
  </el-table>
  <!-- <span>{{msg}}</span> -->
  <!-- <span>{{tableData}}</span> -->
  <router-view/>
</div>
</template>

 <script>
 // var msg;
 // var tableData;
 import Vue from 'vue'
 import axios from 'axios'

export default {

 data () {
   return {
      tableData2: this.getMsg(),
    //    msg:this.msg,
    //  tableData:this.tableData,
   }

  },
  methods:{
     getMsg(){
             axios.get('http://localhost:80/ccdemo/backend/web/index.php/api/course/index').then(res=>{

             console.log([res.data]);
             this.tableData2 =res.data;
              console.log( this.tableData2);
          })
    },
    create(){
        alert('hsa');
    }
}
 }
// new Vue({
//     el:"#app",
//     data:{
//         msg:'dad',
//
//     },
//
//     methods:{
//         tableData3:function(){ return [{
//                  date: '2016-05-03',
//                  name: '王小虎',
//                  address: '上海市普陀区金沙江路 1518 弄'
//                }, {
//                  date: '2016-05-02',
//                  name: '王小虎',
//                  address: '上海市普陀区金沙江路 1518 弄'
//                }, {
//                  date: '2016-05-04',
//                  name: '王小虎',
//                  address: '上海市普陀区金沙江路 1518 弄'
//                }, {
//                  date: '2016-05-01',
//                  name: '王小虎',
//                  address: '上海市普陀区金沙江路 1518 弄'
//                }, {
//                  date: '2016-05-08',
//                  name: '王小虎',
//                  address: '上海市普陀区金沙江路 1518 弄'
//                }, {
//                  date: '2016-05-06',
//                  name: '王小虎',
//                  address: '上海市普陀区金沙江路 1518 弄'
//                }, {
//                  date: '2016-05-07',
//                  name: '王小虎',
//                  address: '上海市普陀区金沙江路 1518 弄'
//              }];
//          }
//     }
// })

// export {
//  data (){
//     return {
//         msg: 'Welcome to Your Vue.js App'
//       }
//     }
// }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
