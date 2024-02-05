<template>
  <div class="container">
    <div class="sidebar-left">
      <SideNav></SideNav>
    </div>
    <div class="main-section">
      <Header></Header>
      <MainSection></MainSection>
    </div>
    <div class="sidebar-right">
      <button class="header-dropdown-btn">
        Administrator <i class="fa fa-fw fa-caret-down"></i>
      </button>
      <div class="sidebar-right-container">
        <h4>Popular Product</h4>
        <div
          class="sidebar-right-content"
          v-for="product in productData"
          :key="product.id"
        >
          <div class="avatar"></div>
          <div class="product">
            <div class="product-name">{{ product.name }}</div>
            <div class="product-price">{{ product.price }}</div>
          </div>
        </div>
        <h4>Chat</h4>
        <div
          class="sidebar-right-content"
          v-for="user in userData"
          :key="user.id"
        >
          <div class="avatar"></div>
          <div class="user">
            <div class="user-name">{{ user.name }}</div>
            <div class="user-msg">{{ user.msg }}</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import SideNav from "@/components/SideNav.vue";
import Header from "@/components/Header.vue";
import MainSection from "@/components/MainSection.vue";
export default {
  components: {
    SideNav,
    Header,
    MainSection,
  },
  data() {
    return {
      productData: [
        {
          id: 1,
          name: "Gadget Converter",
          price: "$250",
        },
        {
          id: 2,
          name: "Lens Camera",
          price: "$50",
        },
        {
          id: 3,
          name: "Airpods",
          price: "$100",
        },
        {
          id: 4,
          name: "Macbook",
          price: "$999",
        },
      ],
      userData: [
        {
          id: 1,
          name: "Debra Young",
          msg: "How's my product",
        },
        {
          id: 2,
          name: "Dorothy Collins",
          msg: "How was the meeting",
        },
        {
          id: 3,
          name: "Chris Jordan",
          msg: "How employee performance",
        },
        {
          id: 4,
          name: "Denise Murphy",
          msg: "How was the meeting",
        },
      ],
    };
  },
};
</script>
<style scoped>
.container {
  height: 100vh;
  display: grid;
  grid-template-columns: 250px auto 250px;
  grid-template-rows: auto;
  grid-template-areas: "left main right";
}
.sidebar-left {
  background-color: #0b0b4c;
  grid-area: left;
  padding: 20px;
}

.main-section {
  grid-area: main;
  background-color: #f4f4f4;
  padding: 20px;
}

.sidebar-right {
  grid-area: right;
  background-color: #f4f4f4;
  /* color: #fff; */
  padding: 20px 0 20px 10px;
  display: flex;
  flex-direction: column;
}

.content-box {
  border: 1px solid white;
  border-radius: 8px;
  width: 200px;
}
.content {
  display: block;
  margin: 0 auto;
}
.header-dropdown-btn {
  background-color: #f4f4f4;
  border: none;
  padding: 10px;
  font-size: 18px;
  margin-bottom: 20px;
}
.sidebar-right-container {
  background-color: white;
  border-radius: 25px;
  padding: 10px;
}
.sidebar-right-content {
  display: flex;
  align-items: center;
  margin: 10px;
}
.avatar {
  border: 1px solid #0b0b4c;
  border-radius: 50%;
  width: 35px;
  height: 35px;
  background-color: #0b0b4c;
  margin: 0 5px;
}
.product {
  display: flex;
  flex-direction: column;
}
.product-name {
  font-weight: bold;
  font-size: 14px;
}
.product-price {
  font-weight: 500;
  color: grey;
  font-size: 9px;
}
.user-name {
  font-weight: bold;
  font-size: 14px;
}
.user-msg {
  font-weight: 500;
  color: grey;
  font-size: 9px;
}
</style>
