<template>
  <div class="col-md-4">
    <form class="form-horizontal">
      <div class="form-group">
        <label>用户名</label>
        <input
          type="text"
          class="form-control"
          placeholder="用户名"
          v-model="usename"
        />
      </div>
      <div class="form-group">
        <label>评论内容</label>
        <textarea
          class="form-control"
          rows="6"
          placeholder="评论内容"
          v-model="content"
        ></textarea>
      </div>
      <div class="form-group">
        <div class="col-sm-offset-2 col-sm-10">
          <button
            type="button"
            class="btn btn-default pull-right"
            @click="addC"
          >
            提交
          </button>
        </div>
      </div>
    </form>
  </div>
</template>

<script type="text/ecmascript-6">
export default {
  data() {
    return {
      usename:'',
      content:''

    }
  },
    //  props:['addcomment'],
    comments:{

    },
    methods: {
       addC(){
      let usename = this.usename
      let content = this.content
      let id = Date.now()
      if(usename.trim() && content.trim()){
        let obj={
          usename,
          content,
          id
        }
        // this.addcomment(obj)
        this.$emit('addcomment',obj)
      }
      this.usename=''
      this.content=''
    }
    },

};
</script>

<style scoped></style>
