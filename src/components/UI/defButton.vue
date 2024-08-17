<template>
  <button class="default_button">
   <slot />
  </button>
</template>

<script>
</script>

<style>
.default_button{
   @media (max-width: 769px) {
      padding: 7px 9px;
   }
   padding: 14px 18px;
   border: 1px solid #73AFF4;
   background-color: white;
   border-radius: 8px;
   transition: transform 0.3s;
}
.default_button:hover{
   transform: scale(1.05);
   background-color: #73AFF4;
   color: white;
   cursor: pointer;
}
</style>