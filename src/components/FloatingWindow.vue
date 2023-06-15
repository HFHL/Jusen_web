<template>
    <div class="customer-service">
      <div class="logo">
        <img  >
      </div>
      <div class="contact">
        <div class="wechat" @mouseover="showQRCode" @mouseleave="hideQRCode">
          微信联系
          <div v-show="showQR" class="qr-code">
            <img  alt="微信二维码">
          </div>
        </div>
        <div class="phone" @mouseover="showPhoneInfo" @mouseleave="hidePhoneInfo">
          电话联系
          <div v-show="showPhone" class="phone-info">
            客服电话：1234567890
          </div>
        </div>
        <div class="register" @click="goToRegister">立即注册</div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        showQR: false,
        showPhone: false,
      };
    },
    methods: {
      showQRCode() {
        this.showQR = true;
      },
      hideQRCode() {
        this.showQR = false;
      },
      showPhoneInfo() {
        this.showPhone = true;
      },
      hidePhoneInfo() {
        this.showPhone = false;
      },
      goToRegister() {
        // 跳转到注册页面的逻辑
        this.$router.push('/register');
      },
    },
  };
  </script>
  
  <style scoped>
  .customer-service {
    padding: 15px;
    background-color: aliceblue;
    position: fixed;
    right: 10px;
    bottom: 10%;
    border-radius: 25px;
    display: flex;
    flex-direction: column;
    font-size: 16px;
    font-weight: 300;
  }
  
  .logo {
    text-align: center;
    margin-bottom: 10px;
  }
  
  .contact {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .wechat,
  .phone,
  .register {
    margin-bottom: 10px;
    cursor: pointer;
  }
  
  .qr-code,
  .phone-info {
    display: none;
    position: absolute;
    top: 100%;
    left: 0;
    background-color: white;
    padding: 5px;
    border-radius: 5px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
  }
  
  .wechat:hover .qr-code {
    display: block;
  }
  
  .phone:hover .phone-info {
    display: block;
  }
  </style>
  