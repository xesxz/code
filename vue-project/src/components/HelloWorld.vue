<template>
  <div>
    <el-button type="text"
               @click="dialogVisible = true">点击打开 Dialog</el-button>

    <el-dialog title="提示"
               :visible.sync="dialogVisible"
               width="30%"
               :before-close="handleClose">
      <span>这是一段信息</span>
      <span slot="footer"
            class="dialog-footer">
        <el-button @click="dialogVisible = false">取 消</el-button>
        <el-button type="primary"
                   @click="dialogStatus==='create'?createData():updateData()">确 定</el-button>
      </span>
    </el-dialog>
  </div>
</template>

<script>
export default {
  data () {
    return {
      dialogVisible: false,
    };
  },
  methods: {
    handleClose (done) {
      this.$confirm('确认关闭？')
        .then((_) => {
          done();
        })
        .catch((_) => { });
    },
    

  },
};
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
