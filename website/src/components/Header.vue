<template>
  <header>
    <div class="inner-header">
      <div><img alt="Vue logo" width="40px" height="40px" src="../assets/logo.png"></div>
      <p>{{ formattedDate }}</p>
    </div>
  </header>
</template>

<script>
import { ref, onMounted } from 'vue';
import { format } from 'date-fns';

export default {
  name: 'Header',
  setup() {
    const formattedDate = ref('');

    const getNowWithFormat = () => {
      const now = new Date();
      formattedDate.value = format(now, 'yyyy年 MM月 dd日');
    };

    onMounted(() => {
      getNowWithFormat();
    });

    return {
      formattedDate
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
header {
  /* background: repeating-linear-gradient(
    45deg,
    yellow,
    yellow 20px,
    black 20px,
    black 40px
  ); */
  background: linear-gradient(45deg, #a8e6cf, #dcedc1, #b3e5fc, #81d4fa, #4fc3f7, #29b6f6, #03a9f4);

}
div, p {
  color: #ffffff;
}
.inner-header {
  display: flex;
}
</style>
