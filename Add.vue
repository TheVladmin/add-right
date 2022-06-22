<template>
    <div :class="{ display: showAdd }" class="add-block">
      <span @click="setHide" class="add-block__close-btn">
        <span class="add-block__close-chest">
        </span>
      </span>
    </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return{
      showAdd: false,
    };
  },
  methods: {
     setShow() {
      setTimeout(() => {
        this.showAdd = true;
      }, 3000);
    },
    setHide() {
        this.showAdd = false;
    },
  },
  mounted() {
    this.setShow()
  }
}
</script>

<style scoped>

.add-block {
  bottom: 24px;
  right: -500px;
  position: fixed;
  z-index: 99;
  transition: right 1.5s ease;
  width: 400px;
  height: 300px;
  background: url("img/banner.png");
  padding: 15px;
  border-radius: 10px;
  box-shadow: 0 0 20px 0 rgb(0 0 0 / 40%);
  box-sizing: border-box;
  cursor: pointer;
  display: block;
  overflow: hidden;
}
.display{
  right: 24px;
}

.add-block__close-chest{
  position: absolute;
  right: 0px;
  top: 0px;
  width: 40px;
  height: 40px;
  cursor: pointer;
}

.add-block__close-btn{
  background: rgba(255, 255, 255, 0.8);
  border-radius: 50%;
  overflow: hidden;
  position: absolute;
  bottom: 92%;
  left: 94%;
  transform: translate(-50%, 50%);
  width: 28px;
  height: 28px;
  border: 6px solid transparent;
}
.add-block__close-btn:before,.add-block__close-btn:after{
  background: #221F1F;
  content: '';
  height: 2px;
  left: 0;
  margin-top: -1px;
  position: absolute;
  top: 50%;
  width: 100%;
  transition: background-color .1s ease;
}
.add-block__close-btn:after{
  transform: rotate(-45deg);
}
.add-block__close-btn:before{
  transform: rotate(45deg);
}
.add-block__close-btn:hover:before,.add-block__close-btn:hover:after{
  background: #f84147;
}
</style>
