<template>
  <f7-page name="steps">
    <f7-navbar title="Steps"></f7-navbar>
    <f7-block-title>Step Example</f7-block-title>
    <f7-block strong>
      <f7-link href="/step1/">Go Step1</f7-link>
    </f7-block>
  </f7-page>
</template>
<script>
export default {
  data() {
    return {
      name: "",
      email: "",
      gender: "",
      toggle: "",
      range: 50
    };
  },
  mounted() {
    console.log(`[setting]`);
  },
  methods: {
    submit() {
      this.$f7.dialog.alert(
        "Uesrname: " +
          this.name +
          "<br>email: " +
          this.email +
          "<br>Gender: " +
          this.gender +
          "<br>Toggle: " +
          this.toggle +
          "<br>Range: " +
          this.range
      );
    },
    changeRang(value) {
      this.range = value;
    }
  }
};
</script>
