<template>
  <div>
    <h1>用户列表</h1>
    <table border="1">
      <tr>
        <td>编号</td>
        <td>姓名</td>
        <td>年龄</td>
        <td>生日</td>
        <td>操作</td>
      </tr>
      <tr v-for="user in users">
        <td>{{ user.id }}</td>
        <td>{{ user.name }}</td>
        <td>{{ user.age }}</td>
        <td>{{ user.bir }}</td>
        <td><a href="">删除</a><a href="">修改</a></td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "User",
  data(){
    return{
      users:[]
    }
  },
  methods:{},
  components:{},
  created() {
    this.$http.get("http://rap2api.taobao.org/app/mock/295165/user/findAll?page=1&rows=4").then((res)=>{
    this.users = res.data.results;
    });

  }

}
</script>

<style scoped>

</style>
