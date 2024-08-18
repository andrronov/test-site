<script setup>
import defButton from './defButton.vue'
</script>

<template>
   <div class="main_item">
      <div class="item_photo">
        <img src="/img/box.svg" alt="box icon" style="align-self: center; justify-self: center;">
        <div class="item_heatprice">
          <span class="heatprice_title">Хит продаж </span>
          <img src="/img/fire.svg" alt="fire icon">
        </div>
        <p class="item_sale">25%</p>
      </div>
      <div class="item_description">
        <p class="_gray_text">Бренд</p>
        <p class="item_text">Полное название товара в несколько строк для вида с обрывом в конце...</p>
      </div>
      <p class="item_price">5 990 ₽</p>
      <defButton>Купить</defButton>
    </div>
</template>