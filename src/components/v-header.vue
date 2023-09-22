<template>
  <header>
    <div class="header__wrapper">
      <div class="header__logo">
        <img src="@/assets/img/logo.svg" alt="" />
      </div>
      <nav class="header__navigation">
        <ul class="header__navigation-list">
          <li class="header__navigation-item"><a href="">О нас</a></li>
          <li class="header__navigation-item">
            <a href="javasctipt(void)" class="submenu">Услуги</a>
            <ul class="navigation-sublist hidden">
              <li class="header__navigation-sub-item">
                <a href="">страница</a>
              </li>
              <li class="header__navigation-sub-item">
                <a href="">страница</a>
              </li>
            </ul>
          </li>
          <li class="header__navigation-item"><a href="">Вакансии</a></li>
          <li class="header__navigation-item"><a href="">Новости</a></li>
          <li class="header__navigation-item">
            <a href="" class="submenu" ref="submenu">Соглашения</a>
            <ul class="navigation-sublist hidden">
              <li class="header__navigation-sub-item">
                <a href="">страница</a>
              </li>
              <li class="header__navigation-sub-item">
                <a href="">страница</a>
              </li>
            </ul>
          </li>
          <li class="header__navigation-item">
            <a href="#"><button class="header_signIn">Войти</button></a>
          </li>
          <li class="header__navigation-item">
            <a href="#"
              ><button class="header__signUp">Зарегистрироваться</button></a
            >
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      isHighlighted: false,
    }
  },
  methods: {
    addClass() {
      this.isHighlighted = true
      const element = document.querySelector(
        '.header__navigation-item:nth-child(2) .navigation-sublist',
      )
      const element2 = document.querySelector(
        '.header__navigation-item:nth-child(5):hover .navigation-sublist',
      )
      console.log(element)
      if (element || element2) {
        element.classList.remove('hidden')
        element2.classList.remove('hidden')
      }
    },
    removeClass() {
      this.isHighlighted = false
    },
  },
}
</script>

<style lang="scss" rel="stylesheet/scss" scoped>
@import '@/assets/styles/variables.scss';

header {
  background-color: #fff;
}
.header__wrapper {
  margin: 26px 140px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

.header__navigation-list {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  position: relative;
}
.header__navigation-item {
  margin-right: 18px;
  position: relative;
}
.header__navigation-list li:last-child {
  margin-right: 0px;
}
.header__navigation-item a {
  font-family: $baseFont;
  color: rgba($baseColor, 0.5);
  position: relative;
  font-size: 14px;
}
.header__navigation-item:nth-child(5) {
  margin-right: 35px;
}
.submenu {
  position: relative;
  display: block;
  font-family: 'Poppins', sans-serif;
  text-transform: uppercase;
  color: #222;
  text-decoration: none;
  font-size: 14px;
  margin: 0 15px;
  font-weight: 600;
  -webkit-transition: all 0.3s ease-in-out;
  -moz-transition: all 0.3s ease-in-out;
  -ms-transition: all 0.3s ease-in-out;
  -o-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;
}

.submenu::after {
  font-family: $baseFont;
  color: rgba($baseColor, 0.5);
  position: absolute;
  content: '';
  background-image: url(@/assets/icons/openSubmenu.svg);
  background-repeat: no-repeat;
  top: 7px;
  right: -16px;
  width: 14px;
  height: 8px;
}
ul .hidden {
  opacity: 0;
  width: 180px;
  position: absolute;
  top: 25px;
  left: 0;
  background: linear-gradient(to top, #bc9cff, #8ba4f9) border-box;
  z-index: 1;
}
ul .navigation-sublist {
  position: absolute;
  left: 0;
  top: 150%;
  width: 172px;
  text-align: left;
  background-color: #222222;
  z-index: 9999;
  -ms-filter: 'progid:DXImageTransform.Microsoft.Alpha(Opacity=0)';
  filter: alpha(opacity=0);
  opacity: 0;
  visibility: hidden;
  -webkit-transition: all 0.3s ease-in-out;
  -moz-transition: all 0.3s ease-in-out;
  -ms-transition: all 0.3s ease-in-out;
  -o-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;
}
.header__navigation-item:hover > ul.navigation-sublist {
  top: 100%;
  -ms-filter: 'progid:DXImageTransform.Microsoft.Alpha(Opacity=100)';
  filter: alpha(opacity=100);
  opacity: 1;
  visibility: visible;
}
.header__navigation-sub-item a {
  color: #fff;
}
.header_signIn,
.header__signUp {
  font-family: $baseFont;
  font-weight: 700;
  text-transform: uppercase;
}
.header_signIn:hover,
.header__signUp:hover {
  cursor: pointer;
  transition: 0.2s ease-out;
}
.header_signIn {
  background:
    linear-gradient(white, white) padding-box,
    linear-gradient(to right, #bc9cff, #8ba4f9) border-box;
  border-radius: 11em;
  padding: 5px 18px;
  border: 4px solid transparent;
  color: #bc9cff;
}
.header_signIn:hover {
  background: linear-gradient(to bottom, #bc9cff, #8ba4f9) border-box;
  color: #fff;
}
.header__signUp {
  background: linear-gradient(to bottom, #bc9cff, #8ba4f9) border-box;
  border-radius: 11em;
  padding: 5px 18px;
  color: #fff;
  border: 4px solid transparent;
}
.header__signUp:hover {
  background:
    linear-gradient(white, white) padding-box,
    linear-gradient(to right, #bc9cff, #8ba4f9) border-box;
  border: 4px solid transparent;
  color: #bc9cff;
}
</style>
