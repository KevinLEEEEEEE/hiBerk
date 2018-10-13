<template>
  <div class="main">
    <div class="content">
      <input type="radio" name="footer" id="left" checked>
      <label for="left">
        <p>more</p>
        <div class="info">

        </div>
      </label>
      <input type="radio" name="footer" id="middle">
      <label for="middle">
        <p>github</p>
        <div class="info">

        </div>
      </label>
      <input type="radio" name="footer" id="right">
      <label for="right">
        <p>join</p>
        <div class="info">

        </div>
      </label>
    </div>
    <div class="police">网站备案信息网站备案信息</div>
  </div>
</template>

<script>
export default {
  name: 'myNav',
  data() {
    return {
    };
  },
  methods: {
  },
};
</script>

<style scoped>
  .main {
    width: 100%;
    margin-top: 50px;
    background: rgba(20, 20, 20, 1.0)
  }
  @media screen and (min-width: 750px){
    .main {
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      height: 250px;
    }
    .content {
      display: flex;
      flex-direction: row;
      justify-content: center;
      height: 100%;
    }
  }
  input {
    display: none;
  }
  input:checked + label {
    height: 160px;
  }
  @media screen and (min-width: 750px){
    input:checked + label {
      height: 100%;
    }
  }
  label {
    display: block;
    width: 100%;
    height: 40px;
    border-bottom: 1px solid rgba(50, 50, 50, 1.0);
    color: white;
  }
  @media screen and (min-width: 750px){
    label {
      display: block;
      width: 20%;
      height: 100%;
      margin: 0 5px;
      color: white;
    }
  }
  label p {
    display: flex;
    align-items: center;
    height: 40px;
    margin: 0 0 0 20px;
  }
  .info {
    width: 100%;
    height: calc(100% - 40px);
    background: gray;
  }
  .police {
    width: 100%;
    height: 20px;
    color: rgba(100, 100, 100, 1.0);
    font-size: .5rem;
    line-height: 20px;
    text-align: center;
  }
  @media screen and (min-width: 750px){
    .police {
      padding: 5px;
    }
  }
</style>
