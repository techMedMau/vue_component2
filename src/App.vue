
<template>
  <div v-if="data.length" id="app" class="container mx-auto space">
    <div class="card">
      <Content
        :name="data[0].name"
        :desc="data[0].desc"
        :price="data[0].price"
      />
      <Img :src="data[0].src" :name="data[0].name" />
      <Input
        class="input"
        :num="num_pro"
        @decrease="num_pro--"
        @increase="num_pro++"
      />
    </div>
    <div class="card">
      <Content
        :name="data[1].name"
        :desc="data[1].desc"
        :price="data[1].price"
      />
      <Img :src="data[1].src" :name="data[1].name" />
      <Input
        class="input"
        :num="num_watch"
        @decrease="num_watch--"
        @increase="num_watch++"
      />
    </div>
    <div class="card">
      <Content
        :name="data[2].name"
        :desc="data[2].desc"
        :price="data[2].price"
      />
      <Img :src="data[2].src" :name="data[2].name" />
      <Input
        class="input"
        :num="num_mini"
        @decrease="num_mini--"
        @increase="num_mini++"
      />
    </div>
    <div class="card">
      <Content
        :name="data[3].name"
        :desc="data[3].desc"
        :price="data[3].price"
      />
      <Img :src="data[3].src" :name="data[3].name" />
      <Input
        class="input"
        :num="num_air"
        @decrease="num_air--"
        @increase="num_air++"
      />
    </div>
    <div class="total">
      <div class="total_title">商品數量</div>
      <p class="total_amount">
        {{ Overall(num_pro, num_watch, num_mini, num_air) }}
      </p>
    </div>
  </div>
</template>

<script>
import Input from "./components/Input";
import Img from "./components/Img";
import Content from "./components/Content";

export default {
  name: "App",
  components: {
    Input,
    Img,
    Content,
  },
  data() {
    return {
      data: [],
      // num: [0, 0, 0, 0],
      num_pro: 0,
      num_watch: 0,
      num_mini: 0,
      num_air: 0,
      total: 0,
    };
  },
  
  created() {
    this.$http.get("../static/data.json").then((res) => {
      this.data = res.data;
    });
  },
  methods: {
    Overall(num_pro, num_watch, num_mini, num_air) {
      return num_pro + num_watch + num_mini + num_air;
    }
  },
};
</script>

<style>
* {
  font-family: sans-serif;
  box-sizing: border-box;
}

.container {
  max-width: 1200px;
}

.mx-auto {
  margin-right: auto;
  margin-left: auto;
}

.space {
  display: flex;
  justify-content: space-between;
  margin-top: 1rem;
}
.card {
  width: 24%;
  border: 1px solid #ddd;
}

.input {
  text-align: center;
}

.total {
  position: absolute;
  right: 0;
  top: 0;
  text-align: center;
  color: #fff;
}

.total_amount {
  background-color: #ea337c;
  margin: 0;
  padding: 10px;
  font-size: 25px;
}

.total_title {
  font-size: 15px;
  background-color: #ec6fae;
  padding: 0.5rem;
}
</style>
