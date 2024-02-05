<template>
  <div class="header">
    <div class="header-content">
        <div class="header-title">Overview</div>
        <i class="fa fa-fw fa-bell"></i>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {};
  },
};
</script>
<style scoped>
.header-title{
    font-weight: 900;
    font-size: 30px;
    color: black;
}
.header-content{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
</style>
