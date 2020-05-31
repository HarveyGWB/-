<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对Vue的评论</h1>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <!-- <Add :addcomment="addcomment"></Add> -->
      <Add @addcomment="addcomment"></Add>
      <List :comments="comments" :deletecomment="deletecomment"></List>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
import Add from '@/components/Add'
import List from '@/components/List'
export default {
    components:{
        Add,
        List
    },
    data(){
        return {
            comments:[
                {id:1,usename:'欧阳锋',content:'Vue真棒'},
                {id:2,usename:'郭靖',content:'Vue666'},
                {id:3,usename:'黄蓉',content:'Vue真好'},


            ]
        }
    },
    methods: {
      addcomment(obj){
        this.comments.unshift(obj)
      },
      deletecomment(index){
        this.comments.splice(index,1)
      }
    },
}
</script>

<style scoped></style>
