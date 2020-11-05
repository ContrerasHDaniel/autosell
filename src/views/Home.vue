<template>
  <section class="home">
    <div class="flex application-content home-content">
      <div class="animate__animated animate__backInRight">
        <img src="@/assets/car_1.png" class="running-car">
      </div>
      <h1 class="home-title">Lorem ipsum dolor sit, amet consectetur.</h1>
      <h2 class="home-subtitle">Lorem ipsum dolor sit amet consectetur adipisicing elit.
        Vel quis deleniti asperiores amet.</h2>
      <div class="button-group">
        <div class="btn-left">
          <Button @click="lBtnClick()"> Compra un auto </Button>
        </div>
        <div class="btn-right">
          <Button @click="rBtnClick()"> Vende tu auto </Button>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Button from '../components/Button.vue';

export default {
  name: 'Home',
  components: {
    Button,
  },
  methods: {
    lBtnClick() {
      this.$router.push({ name: 'catalogue' });
    },
    rBtnClick() {
      console.log('Right click');
    },
  },
};
</script>

<style lang="scss" scoped>
.home {
  background: url('http://cdn.backgroundhost.com/backgrounds/subtlepatterns/polonez_car.png');
  //background: url('http://cdn.backgroundhost.com/backgrounds/subtlepatterns/furley_bg.png');
  background-size: inherit;
  //background-color: var(--application-primary-color);
}

.home-content {
  //background: url('/home/daniel/development/AutoSell/prototype/src/assets/home_bkg.jpg');
  display: flex;
  flex-direction: column;
  justify-content: center;
  color: var(--application-text-color);
}

.home-title {
  margin-bottom: 1.5rem;
  font-size: 2rem;
  letter-spacing: 1px;
}

.home-subtitle {
  margin-bottom: 1.5rem;
  font-size: 1.2rem;
  letter-spacing: 1px;
}

.button-group {
  display: flex;
  flex-wrap: wrap;
  align-content: center;
  justify-content: center;
  font-size: 1.5rem;
}

.btn-left {
  margin-left: 1rem;
  margin-bottom: 2rem;
  margin-right: 1rem;
}

.btn-right {
  margin-left: 1rem;
  margin-bottom: 2rem;
  margin-right: 1rem;
}

.running-car {
  filter: sepia(45%);
  margin-bottom: 1.2rem;
  width: 14rem;
  height: 9rem;
}
</style>
