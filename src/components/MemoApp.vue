// 메모들의 상태를 관리하는 컴포넌트(parent)
<template>
    <div class="memo-app">
        <memo-form />
       <memo />
    </div>

</template>
<script>
import Memo from './Memo.vue'
import MemoForm from './MemoForm.vue'
export default {
  components: { MemoForm, Memo },
  name:"MemoApp",
  data()    {
      return{
          memos:[],
      };
  },
  created(){
      // 만약 기존의 추가된 localStorage에 데이터가 있다면, created 훅에서
     //  localStorage의 데이터를 컴포넌트 내의 memos 데이터에 넣어주고,
     //  그렇지 않다면 그대로 빈 배열로 초기화 한다.
     this.memos = localStorage.memos ? json.parse(localStorage.memos) : [];
  }
    
}
</script>