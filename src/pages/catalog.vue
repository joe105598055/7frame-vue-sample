<template>
  <f7-page name="catalog">
    <f7-navbar title="Catalog"></f7-navbar>
    <f7-list>
      <f7-list-item
        v-for="(product) in products"
        :key="product.id"
        :title="product.title"
        :link="`/product/${product.id}/`"
      ></f7-list-item>
    </f7-list>
    <f7-list simple-list>
      <!-- <f7-list-item>
        <span>Batman</span>
        <f7-toggle :checked="isChecked" @change="isChecked=$event.target.checked"></f7-toggle>
      </f7-list-item> -->
      <f7-list-item v-for="(item,index) in toggleList" :key="index" :value="item">
        <span>{{item}}</span>
        <f7-toggle :value="item" @change="($event.target.checked?isChecked.push(item):isChecked.splice(isChecked.indexOf(item),1))"></f7-toggle>
      </f7-list-item>
    </f7-list>
    <f7-block>
    <f7-button fill @click="log">Log toggle button</f7-button>
    </f7-block>

  </f7-page>
</template>
<script>
export default {
  data: function() {
    return {
      products: this.$f7.data.products,
      isChecked: [],
      toggleList: ["one", "two", "three"]
    };
  },
  methods: {
    changeToggle(el) {
      console.log(el.target.checked);
    },
    log() {
      console.log(this.isChecked);
    }
  }
};
</script>
