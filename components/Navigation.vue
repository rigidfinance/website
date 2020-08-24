<template>
  <header id="header" ref="header">
    <div class="container">
      <div class="row">
        <nav>
          <div class="logo">
            <a href="/" id="logo"></a>
          </div>
          <div id="navbar" class="navbar">
            <div class="navbar-menu">
              <ul>
                <li><a href="#about">About</a></li>
                <li><a href="#tokensale">Token Sale</a></li>
                <li><a href="#roadmap">Roadmap</a></li>
                <li><a href="#faq">FAQ</a></li>
                <li><a href="#social">Social</a></li>
                <li class="exact_menu hamburger">
                  <button type="button" @click="showMenu">
                    <font-awesome-icon class="hamburger-icon" :icon="['fas', 'bars']"/>
                  </button>
                </li>
              </ul>
            </div>
          </div>
        </nav>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Navigation",
  components: {},
  data() {
    return {
      $$header: null,
      showMenuIn: null
    }
  },
  created() {
  },
  mounted() {
    this.$$header = this.$refs.header;
    window.addEventListener('scroll', this.throttle(this.onScroll, 25));

  },
  methods: {
    throttle(fn, delay) {
      var last = undefined;
      var timer = undefined;
      return function () {
        var now = +new Date();
        if (last && now < last + delay) {
          clearTimeout(timer);

          timer = setTimeout(function () {
            last = now;
            fn();
          }, delay);
        } else {
          last = now;
          fn();
        }
      };
    },
    onScroll() {
      if (window.pageYOffset) {
        this.$$header.classList.add('is-active');
      } else {
        this.$$header.classList.remove('is-active');
      }
    },
    showMenu() {
      this.showMenuIn = !this.showMenuIn;
    },

  }
}
</script>

<style scoped lang="scss">
header {
  background: #171055;
  position: relative;
  min-height: 50px;
  z-index: 99;

  nav {
    display: flex;
    justify-content: space-between;
    flex-direction: row;
    width: 100%;
    padding: 15px;


    .logo {
      display: flex;
      align-items: center;
      justify-content: center;
      max-width: 170px;
      width: 100%;

      #logo {
        display: block;
        max-width: 170px;
        width: 100%;
        height: 42px;
        background-image: url("~assets/img/logo.png");
        background-size: contain;
        background-repeat: no-repeat;
      }
    }

    ul {
      margin: 0;
      padding: 0;
      list-style-type: none;
      float: right;
      display: flex;
      justify-content: center;
      align-items: center;

      li {
        display: inline-block;

        &.hamburger {
          display: none;

          button {
            appearance: none;
            background: none;
            border: none;
            font-size: 28px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;

            .hamburger-icon {
              font-size: 28px;
              color: white;
            }
          }

        }

        a {
          color: #fff !important;
          text-decoration: none;
          display: block;
          font-size: 16px;
          font-weight: bold;
          line-height: 34px;
          padding: 29px 18px;
          transition: all 250ms ease-in-out 0s;
        }

        &:hover a {
          color: #6cd087 !important;
        }

        &#navbar_language {
          button {
            background: transparent;
            border: none;
            color: #fff !important;
            text-decoration: none;
            display: block;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
          }

          ul {
            margin: 0;
            padding: 0;
            list-style-type: none;
            display: none;

            li {
              margin: 0;
              padding: 0;
            }
          }
        }
      }


    }

    &.is-active {
      background: rgba(23, 16, 85, 0.9);
      position: sticky;
      will-change: transform;
      top: 0;
      box-shadow: 0 3px 15px rgba(0, 0, 0, 0.1);
    }
  }


}

@media (max-width: 991px) {
  header {
    ul {
      li {
        &:not(.exact_menu) {
          display: none;
        }

        &.hamburger {
          display: block !important;
        }

      }
    }
  }

}

</style>
