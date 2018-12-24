<template>
  <div class="container">
    <div id="translateForm">
      <div class="col-md-6">
        <form id="transForm" v-on:submit="formSubmit" class="well form-inline">
          <input class="form-control" type="text" placeholder="请输入需要翻译的内容" v-model="textToTranslate">
          <select v-model="language" class="form-control">
            <option value="en">English</option>
            <option value="ru">Russian</option>
            <option value="ko">Korean</option>
            <option value="ja">Janpenese</option>
          </select>
          <input type="submit" value="翻译" class="btn btn-primary">
        </form>
      </div>
    </div>
  </div>
</template>

<script>


export default {
  name: 'translateForm',
  data:function(){
    return {
      textToTranslate:"",
      language:""
    }
  },
  methods:{
    formSubmit:function(e){
      // alert(this.textToTranslate);
      this.$emit("formSubmit", this.textToTranslate, this.language);
      e.preventDefault();
    }
  },
  created:function(){
    this.language = "en";
  }
}
</script>

<style>
  #transForm{
    border-radius: 10px;
    border: 1px solid #ccc;
  }

</style>
