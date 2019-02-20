<template>
  <f7-page name="home">
    <!-- Top Navbar -->
    <f7-navbar :sliding="true" large>
      <f7-nav-left>
        <f7-link icon-ios="f7:menu" icon-md="material:menu" panel-open="left"></f7-link>
      </f7-nav-left>
      <f7-nav-title sliding>My App</f7-nav-title>
      <f7-nav-right>
        <f7-link icon-ios="f7:menu" icon-md="material:menu" panel-open="right"></f7-link>
      </f7-nav-right>
      <f7-nav-title-large sliding>My App</f7-nav-title-large>
    </f7-navbar>

    <!-- Page content-->
    <f7-block strong>
      <p>This is an example of tabs-layout application. The main point of such tabbed layout is that each tab contains independent view with its own routing and navigation.</p>

      <p>Each tab/view may have different layout, different navbar type (dynamic, fixed or static) or without navbar like this tab.</p>
    </f7-block>

    <f7-block-title>Navigation</f7-block-title>
    <f7-list>
      <f7-list-item link="/about/" title="About"></f7-list-item>
      <f7-list-item link="/form/" title="Form"></f7-list-item>
    </f7-list>

    <f7-block-title>Modals</f7-block-title>
    <f7-block strong>
      <f7-row>
        <f7-col width="50">
          <f7-button fill raised popup-open="#my-popup">Popup</f7-button>
        </f7-col>
        <f7-col width="50">
          <f7-button fill raised login-screen-open="#my-login-screen">Login Screen</f7-button>
        </f7-col>
      </f7-row>
    </f7-block>

    <f7-block-title>Panels</f7-block-title>
    <f7-block strong>
      <f7-row>
        <f7-col width="50">
          <f7-button fill raised panel-open="left">Left Panel</f7-button>
        </f7-col>
        <f7-col width="50">
          <f7-button fill raised panel-open="right">Right Panel</f7-button>
        </f7-col>
      </f7-row>
    </f7-block>
    <f7-list>
      <f7-list-item
        title="Dynamic (Component) Route"
        link="/dynamic-route/blog/45/post/125/?foo=bar#about"
      ></f7-list-item>
      <f7-list-item title="Default Route (404)" link="/load-something-that-doesnt-exist/"></f7-list-item>
      <f7-list-item
        title="Request Data & Load"
        media-item
        badge="3"
        item-input
        link="/request-and-load/user/123456/"
      ></f7-list-item>
    </f7-list>
    <f7-block-title>Something more simple</f7-block-title>
    <f7-list media-list>
      <f7-list-item title="Yellow Submarine" subtitle="Beatles">
        <img
          slot="media"
          src="https://cdn.framework7.io/placeholder/fashion-88x88-1.jpg"
          width="44"
        >
      </f7-list-item>
      <f7-list-item title="Don't Stop Me Now" subtitle="Queen">
        <img
          slot="media"
          src="https://cdn.framework7.io/placeholder/fashion-88x88-2.jpg"
          width="44"
        >
      </f7-list-item>
      <f7-list-item title="Billie Jean" subtitle="Michael Jackson">
        <img
          slot="media"
          src="https://cdn.framework7.io/placeholder/fashion-88x88-3.jpg"
          width="44"
        >
      </f7-list-item>
    </f7-list>
    <div class="block-title">Picker with single value</div>
    <div class="list no-hairlines-md">
      <ul>
        <li>
          <div class="item-content item-input">
            <div class="item-inner">
              <div class="item-input-wrap">
                <input
                  type="text"
                  placeholder="Your iOS device"
                  readonly="readonly"
                  id="demo-picker-device"
                >
              </div>
            </div>
          </div>
        </li>
      </ul>
    </div>
    <button @click="log">Log</button>
    <f7-list>
      <f7-list-item title="Fruit" smart-select :smart-select-params="{openIn: 'sheet'}">
        <select name="fruits" v-model="chooseFruit">
          <option
            v-for="(fruit,index) in fruitList"
            :value="fruit"
            :key="index"
          >{{fruit.toUpperCase()[0]+fruit.slice(1)}}</option>
          <!-- <option value="apple" selected>Apple</option>
          <option value="pineapple">Pineapple</option>
          <option value="pear">Pear</option>
          <option value="orange">Orange</option>
          <option value="melon">Melon</option>
          <option value="peach">Peach</option>
          <option value="banana">Banana</option>-->
        </select>
      </f7-list-item>
    </f7-list>
    <test :fruitList="fruitList"></test>

    <f7-list media-list>
      <f7-list-item
        v-for="(item,index) in itemList"
        :key="index"
        :title="item.title"
        subtitle="Beatles"
      >
        <!-- <img slot="media" :src="item.img_src" width="44"> -->
        <img slot="media" :src="item.img_src" width="44">
      </f7-list-item>
    </f7-list>
  </f7-page>
</template>

<script>
import test from "./test";
var pickerDevice;
export default {
  props: ["hello"],
  components: {
    test
  },
  data() {
    return {
      itemList: [
        {
          title: "Yellow Submarine",
          img_src: "https://cdn.framework7.io/placeholder/fashion-88x88-1.jpg"
        },
        {
          title: "Don't Stop Me Now",
          img_src: "https://cdn.framework7.io/placeholder/fashion-88x88-2.jpg"
        },
        {
          title: "Billie Jean",
          img_src: "https://cdn.framework7.io/placeholder/fashion-88x88-3.jpg"
        }
      ],
      fruitList: [
        "apple",
        "pineapple",
        "pear",
        "orange",
        "melon",
        "peach",
        "Banana"
      ],
      chooseFruit: ""
    };
  },
  methods: {
    log() {
      console.log(pickerDevice.getValue());
      console.log(this.chooseFruit);
    },
    reinit() {
      console.log("reinit");
    }
  },
  beforeRouteUpdate(to, from, next) {
    console.log("beforeRouteUpdate");
    next();
  },
  mounted() {
    this.$nextTick(() => {
      console.log(`nextTick`);
      console.log(this.hello);
    });
    this.$f7ready(f7 => {
      // Call F7 APIs here
      pickerDevice = f7.picker.create({
        inputEl: "#demo-picker-device",
        cols: [
          {
            textAlign: "center",
            values: [
              "iPhone 4",
              "iPhone 4S",
              "iPhone 5",
              "iPhone 5S",
              "iPhone 6",
              "iPhone 6 Plus",
              "iPad 2",
              "iPad Retina",
              "iPad Air",
              "iPad mini",
              "iPad mini 2",
              "iPad mini 3"
            ]
          }
        ]
      });
    });
  }
};
</script>
