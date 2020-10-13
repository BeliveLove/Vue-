<template>
  <div>
    <input v-model="message" />
  </div>
</template>
<script>
export default {
  data () {
    return {
      message: 123
    }
  },
  beforeCreate: function () {
    // 在 beforeCreate 生命周期函数执行的时候，data 和 methods 中的 数据都还没有没初始化
    console.group('------beforeCreate创建前状态------');
    console.log("%c%s", "color:red", "el     : " + this.$el); //undefined
    console.log("%c%s", "color:red", "data   : " + this.$data); //undefined 
    console.log("%c%s", "color:red", "message: " + this.message)
    console.log("alterFunction:   " + this.alter('beforeCreate'));//此处异常

  },
  created: function () {
    //此处初始化methods以及data
    console.group('------created创建完毕状态------');
    console.log("%c%s", "color:red", "el     : " + this.$el); //undefined
    console.log("%c%s", "color:red", "data   : " + this.$data); //已被初始化 
    console.log("%c%s", "color:red", "message: " + this.message); //已被初始化
    console.log("alterFunction:   " + this.alter('created'));
  },
  beforeMount: function () {
    console.group('------beforeMount挂载前状态------');
    console.log("%c%s", "color:red", "el     : " + (this.$el)); //已被初始化
    console.log(this.$el);
    console.log("%c%s", "color:red", "data   : " + this.$data); //已被初始化  
    console.log("%c%s", "color:red", "message: " + this.message); //已被初始化  
  },
  mounted: function () {
    console.group('------mounted 挂载结束状态------');
    console.log("%c%s", "color:red", "el     : " + this.$el); //已被初始化
    console.log(this.$el);
    console.log("%c%s", "color:red", "data   : " + this.$data); //已被初始化
    console.log("%c%s", "color:red", "message: " + this.message); //已被初始化 
  },
  beforeUpdate: function () {
    console.group('beforeUpdate 更新前状态===============》');
    console.log("%c%s", "color:red", "el     : " + this.$el);
    console.log(this.$el);
    console.log("%c%s", "color:red", "data   : " + this.$data);
    console.log("%c%s", "color:red", "message: " + this.message);
  },
  updated: function () {
    console.group('updated 更新完成状态===============》');
    console.log("%c%s", "color:red", "el     : " + this.$el);
    console.log(this.$el);
    console.log("%c%s", "color:red", "data   : " + this.$data);
    console.log("%c%s", "color:red", "message: " + this.message);
  },
  beforeDestroy: function () {
    console.group('beforeDestroy 销毁前状态===============》');
    console.log("%c%s", "color:red", "el     : " + this.$el);
    console.log(this.$el);
    console.log("%c%s", "color:red", "data   : " + this.$data);
    console.log("%c%s", "color:red", "message: " + this.message);
  },
  destroyed: function () {
    console.group('destroyed 销毁完成状态===============》');
    console.log("%c%s", "color:red", "el     : " + this.$el);
    console.log(this.$el);
    console.log("%c%s", "color:red", "data   : " + this.$data);
    console.log("%c%s", "color:red", "message: " + this.message)
  },
  methods: {
    alter (num) {
      alert(num);
    }
  },
}
</script>
