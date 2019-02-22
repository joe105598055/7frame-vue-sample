<template>
  <f7-page
    name="step2"
    title="step2"
    @page:reinit="reinit"
    @page:beforeremove="beforeremove"
    @page:afterout="afterout"
  >
    <f7-navbar title="Step 2" back-link="Back"></f7-navbar>
    <f7-block-title>Step 2</f7-block-title>
    <f7-block strong>
      <f7-link reload-all href="/steps/">Go Home</f7-link>
    </f7-block>
      <label>Clicked: {{ $store.state.count }} times</label>

  </f7-page>
</template>

<script>
export default {
  data: function() {
    return {};
  },
  mounted() {
    // console.log(`[About Mounted]`);
  },
  destroyed() {
    // console.log("[About Destroyed]");
  },
  methods: {
    sendData() {
      console.log("sendData");
      this.$root.$emit("eventing", "hello");
    },
    reinit(el) {
      // console.log(`[About] reinit`);
    },
    beforeremove() {
      // console.log(`[About] beforeremove`);
    },
    afterout() {
      // console.log(`[About] afterout`);
    }
  }
};
</script>

