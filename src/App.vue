<script setup>
import defButton from "./components/UI/defButton.vue";
import itemComponent from './components/UI/itemComponent.vue'
</script>

<template>
  <div class="wrapper">
    <header class="header">
      <div class="header__logo">
        <div class="header__logo_container">
          <img src="/img/logo.svg" alt="logo" />
          <p>Логотип</p>
        </div>
        <defButton>Каталог</defButton>
      </div>
      <img class="arrow_img" src="/img/arrow-back.svg" alt="arrow svg">
      <input type="text" placeholder="Поиск" class="header__input" />
      <defButton class="search_button">Найти</defButton>
      <div class="header__links">
        <a href="#" class="header__link">Информация о компании</a>
        <a href="#" class="header__link">Контакты</a>
        <a href="#" class="header__link">Полезные ссылки</a>
      </div>
    </header>
    <main class="main">
      <div class="main__container">
        <div class="search_container">
          <ul class="search_list">
            <li class="list_item" v-for="(item, index) in 4" :key="index"><a class="item_name _gray_title">Название категории</a><span class="item_value _gray_text">3</span></li>
          </ul>

          <div class="search_price">
            <p class="_black_title">Цена</p>
            <div class="price_container">
              <input type="text" class="search_input _default_input" placeholder="от 0₽" />
              <input type="text" class="search_input _default_input" placeholder="до 10000₽" />
            </div>
          </div>
          <div class="search_select">
            <div class="select_container">
              <p class="select_title">Бренд</p>
              <a class="_gray_text">Очистить</a>
            </div>
            <input type="text" class="select_input _default_input" placeholder="Поиск" />
            <ul class="select_list">
              <li class="list_item" v-for="item in 6" :key="item.index">
                <div class="item_spacer">
                  <input type="checkbox" />
                  <span class="item_name _gray_title">Атрибут</span>
                </div>
                <span class="item_value _gray_text">3</span>
              </li>
            </ul>
          </div>
          <div class="search_select">
            <p class="_black_title">Размер</p>
            <ul class="select_list">
              <li class="list_item" v-for="item in 6" :key="item.index">
                <div class="item_spacer">
                  <input type="checkbox" />
                  <span class="item_name _gray_title">Атрибут</span>
                </div>
                <span class="item_value _gray_text">3</span>
              </li>
            </ul>
          </div>
        </div>
        <div class="items__container">
          <itemComponent v-for="(item, index) in 12" :key="index" />
        </div>
      </div>
    </main>
  </div>
</template>

<style lang="scss">
header {
  @media (max-width: 769px) {
    font-size: 0.55rem;
    gap: 6px;
  }

  width: 100%;
  height: 72px;
  display: flex;
  flex-direction: row;
  align-items: center;
  background-color: #fff;
  padding: 12px 0px 12px 0px;
  gap: 24px;
  .header__logo {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    gap: 16px;
    width: 20%;
    @media (max-width: 769px) {
      display: none;
    }
  }
  .header__logo_container {
    display: flex;
    align-items: center;
    gap: 6px;
  }
  .header__input {
    padding: 14px 18px;
    border: 1px solid #73AFF4;
    background-color: white;
    border-radius: 8px;
    flex-grow: 1;
    max-width: 100%;
    @media (max-width: 769px) {
      padding: 10px 14px;
    }
  }
  .header__links {
    display: flex;
    flex-direction: row;
    align-items: center;
    font-size: 1rem;
    gap: 6px;
  }
  .header__link {
    @media (max-width: 769px) {
      display: none;
    }
    font-weight: 400;
    font-size: 14px;
    color: #393939;
  }
}

.main {
  width: 100%;
  min-height: 100%;
  flex: 1 1 auto;
  margin-top: 5px;

  .main__container {
    min-height: 100%;
    display: flex;
    width: 100%;
    flex-direction: row;
    justify-content: space-between;
    @media (min-width: 769px) {
      gap: 36px;
    }
  }
  .search_container {
    text-align: center;
    width: 20%;
    display: flex;
    flex-direction: column;
    gap: 28px;
    @media (max-width: 769px) {
      display: none;
    }
  }
  .search_list {
    .list_item {
      display: inline-flex;
      flex-direction: row;
      justify-content: space-between;
      margin: 4px 0px;
      width: 90%;
    }
    :first-child {
      .item_name {
        margin-left: -15px;
      }
    }
  }
  .search_price {
    display: flex;
    flex-direction: column;
    p {
      margin-bottom: 16px;
    }
  }
  .price_container {
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }
  .search_input {
    width: 45%;
  }
  .select_container {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    width: 100%;
  }
  .select_title {
    color: #333333;
    font-weight: 700;
  }
  .search_select {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 16px;
  }
  .select_input {
    width: 100%;
  }
  .select_list {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 12px;
  }
  .items__container {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
    @media (min-width: 769px) {
      width: 80%;
    }
    @media (max-width: 768px) {
      width: 100%;
    }
  }

  @media (max-width: 1200px) {
    .items__container {
      grid-template-columns: repeat(3, 1fr);
    }
  }

  @media (max-width: 900px) {
    .items__container {
      grid-template-columns: repeat(2, 1fr);
    }
  }
  @media (max-width: 769px) {
    .main {
      margin-top: 0px;
    }
    .header__logo {
      justify-content: flex-start;
      width: 20%;
    }
    .arrow_img {
      display: block;
    }
    .header__input {
      padding: 7px 9px;
    }
  }
  @media (max-width: 426px) {
    .main_item {
      font-size: 0.75rem;
    }
    .item_sale {
      padding: 7.5px;
    }
    .items__container {
      gap: 6px;
    }
  }

  .list_item input[type="checkbox"] {
    appearance: none;
    width: 20px;
    height: 20px;
    border: 2px solid #ddd;
    border-radius: 4px;
    margin-right: 12px;
    outline: none;
    cursor: pointer;
    transition: background 0.3s, border-color 0.3s;
  }

  .list_item input[type="checkbox"]:checked {
    background-color: #5b84f1;
    border-color: #5b84f1;
    background-image: url('data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="white"%3E%3Cpath d="M20.29 5.71l-11 11a1 1 0 01-1.41 0l-5-5a1 1 0 111.42-1.42L9 14.59l9.29-9.3a1 1 0 011.42 1.42z"/%3E%3C/svg%3E');
    background-repeat: no-repeat;
    background-position: center;
  }

  .list_item input[type="checkbox"]:hover {
    border-color: #aaa;
  }
  .list_item {
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    .item_spacer {
      display: flex;
      flex-direction: row;
      align-items: center;
    }
  }
}

.main_item {
  width: 100%;
  min-height: 400px;
  display: flex;
  flex-direction: column;
  gap: 16px;
}
.main_item:hover {
  cursor: pointer;
}
.main_item:hover .item_photo {
  transform: scale(1.05);
}
.item_photo {
  width: 100%;
  min-height: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #F8F8FA;
  position: relative;
  transition: transform 0.3s;
}
.item_heatprice {
  position: absolute;
  background-color: white;
  padding: 10px;
  top: 12px;
  left: 12px;
}
.item_sale {
  position: absolute;
  padding: 10px;
  background-color: #7397F5;
  color: white;
  border-radius: 4px;
  bottom: 12px;
  left: 12px;
  font-weight: 700;
}
.item_description {
  display: flex;
  flex-direction: column;
  gap: 8px;
}
.search_button {
  padding: 14px 18px; 
  background-color: #73AFF4; 
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  @media (min-width: 769px) {
    display: none;
  }
  @media (max-width: 769px) {
    padding: 10px 14px;
  }
}
.arrow_img {
  @media (min-width: 769px) {
    display: none;
  }
}

* {
  -webkit-overflow-scrolling: touch;
}

.wrapper {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.header {
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}
</style>