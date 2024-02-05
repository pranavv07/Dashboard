<template>
  <div class="sidenav">
    <h2 class="project-name">CRM.io</h2>
    <button class="dashboard-btn">
      <span><i class="fa-solid fa-bars"></i> Dashboard</span>
    </button>
  </div>
  <div v-for="menu in menuItems" :key="menu.key" class="menu">
    <h3 class="menu-name">{{ menu.name }}</h3>
    <a v-for="subMenu in menu.subMenu" :key="subMenu.key">
      <i :class="subMenu.icon"></i> {{ subMenu.name }}</a
    >
    <hr v-if="menu.showLine" />
  </div>
</template>
<script>
export default {
  data() {
    return {
      menuItems: [
        {
          key: "management",
          name: "Management",
          showLine: true,
          subMenu: [
            {
              key: "document",
              name: "Document",
              icon: "fa-solid fa-print",
            },
            {
              key: "contact",
              name: "Contact",
              icon: "fa-solid fa-book",
            },
            {
              key: "prospect",
              name: "Prospect",
              icon: "fa-solid fa-bitbucket",
            },
            {
              key: "workflow",
              name: "Workflow",
              icon: "fa-solid fa-rotate",
            },
          ],
        },
        {
          key: "connection",
          name: "Connection",
          showLine: true,
          subMenu: [
            {
              key: "chat_integration",
              name: "Chat Integration",
              icon: "fa-solid fa-search",
            },
            {
              key: "marketing_automation",
              name: "Marketing Automation",
              icon: "fa-solid fa-file",
            },
            {
              key: "email_integration",
              name: "Email Integration",
              icon: "fa-solid fa-envelope",
            },
          ],
        },
        {
          key: "customer",
          name: "Customer",
          showLine: false,
          subMenu: [
            {
              key: "transaction",
              name: "Transaction",
              icon: "fa-solid fa-arrow-right-arrow-left",
            },
            {
              key: "maintenance",
              name: "Maintenance",
              icon: "fa-solid fa-gear",
            },
          ],
        },
      ],
    };
  },
};
</script>
<style scoped>
.sidenav {
  display: flex;
  flex-direction: column;
}
.menu a {
  margin: 10px;
  color: white;
  font-size: 12px;
}
.dashboard-btn {
  background-color: #3a64dae0;
  color: white;
  border-radius: 8px;
  padding: 10px;
  border: 1px solid #3a64dae0;
  margin: 10px;
}
.project-name {
  color: orange;
  font-style: italic;
  font-weight: bold;
  margin: 10px;
}
hr {
  color: white;
  width: 100%;
}
.menu {
  display: flex;
  flex-direction: column;
}
.menu-name {
  margin: 10px;
  font-size: 14px;
  color: #3a64dae0;
}
</style>
