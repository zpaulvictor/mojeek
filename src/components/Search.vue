<template>
<div class="px-10 hover:bg-primary">
  <div class="flex items-center justify-center py-10 px-20 hover:bg-light">
    <!--box shadow-->
    <!--delete focus-->
  <div style="width:45%;min-width:300px;" class="dropdown">
    <div tabindex="0" class="flex relative hover:bg-purple">
      <input v-model=searchKey style="outline: none; width:100%;" type="search" placeholder="No Tracking. Just Search…" class="w-full input input-bordered text-lg" />
      <button class="flex absolute right-2 top-3 hover:bg-green">
        <span @click="searchKey!=''?jump():1" class="material-icons text-2xl text-muted">search</span>
      </button>
    </div>
    <ul tabindex="0" class="dropdown-content menu p-2 shadow bg-base-100 w-52">
      <a @click="jump" class="text-sm">indigenous people bushfire</a>
      <a class="text-sm">Maxpool 2D</a>
      <a class="text-sm">jevons paradox</a>
      <a class="text-sm">news aggregator</a>
      <a class="text-sm">search with nlp and machine learning</a>
      <a class="text-sm">Serena Williams</a>
    </ul>
  </div>
  </div>
</div>
</template>

<script>
import { computed } from "@vue/reactivity";
import axios from "axios"

export default {
  methods: {
    jump(){
    this.$router.push({path: '/search'}),
    this.$router.push({name:'Search', params: { searchKey: this.searchKey }	})
    },
  },
  data() {
    return {
      searchKey: "",
    }
  },
}
</script>

<style>
  input[type=search]::-webkit-search-cancel-button {
    -webkit-appearance: searchfield-cancel-button;
    margin-right: 8mm;
    cursor: pointer;
    height: 10px;
    width: 10px;
    content: url(data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iaXNvLTg4NTktMSI/Pg0KPCEtLSBHZW5lcmF0b3I6IEFkb2JlIElsbHVzdHJhdG9yIDE2LjAuMCwgU1ZHIEV4cG9ydCBQbHVnLUluIC4gU1ZHIFZlcnNpb246IDYuMDAgQnVpbGQgMCkgIC0tPg0KPCFET0NUWVBFIHN2ZyBQVUJMSUMgIi0vL1czQy8vRFREIFNWRyAxLjEvL0VOIiAiaHR0cDovL3d3dy53My5vcmcvR3JhcGhpY3MvU1ZHLzEuMS9EVEQvc3ZnMTEuZHRkIj4NCjxzdmcgdmVyc2lvbj0iMS4xIiBpZD0iQ2FwYV8xIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB4PSIwcHgiIHk9IjBweCINCgkgd2lkdGg9IjEyMy4wNXB4IiBoZWlnaHQ9IjEyMy4wNXB4IiB2aWV3Qm94PSIwIDAgMTIzLjA1IDEyMy4wNSIgc3R5bGU9ImVuYWJsZS1iYWNrZ3JvdW5kOm5ldyAwIDAgMTIzLjA1IDEyMy4wNTsiDQoJIHhtbDpzcGFjZT0icHJlc2VydmUiPg0KPGc+DQoJPHBhdGggZD0iTTEyMS4zMjUsMTAuOTI1bC04LjUtOC4zOTljLTIuMy0yLjMtNi4xLTIuMy04LjUsMGwtNDIuNCw0Mi4zOTlMMTguNzI2LDEuNzI2Yy0yLjMwMS0yLjMwMS02LjEwMS0yLjMwMS04LjUsMGwtOC41LDguNQ0KCQljLTIuMzAxLDIuMy0yLjMwMSw2LjEsMCw4LjVsNDMuMSw0My4xbC00Mi4zLDQyLjVjLTIuMywyLjMtMi4zLDYuMSwwLDguNWw4LjUsOC41YzIuMywyLjMsNi4xLDIuMyw4LjUsMGw0Mi4zOTktNDIuNGw0Mi40LDQyLjQNCgkJYzIuMywyLjMsNi4xLDIuMyw4LjUsMGw4LjUtOC41YzIuMy0yLjMsMi4zLTYuMSwwLTguNWwtNDIuNS00Mi40bDQyLjQtNDIuMzk5QzEyMy42MjUsMTcuMTI1LDEyMy42MjUsMTMuMzI1LDEyMS4zMjUsMTAuOTI1eiIvPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPC9zdmc+DQo=);
    background-size: 10px 10px;
  }

  input[type=search] {
      -webkit-appearance: none;

  }
</style> 