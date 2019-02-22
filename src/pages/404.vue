<template>
  <f7-page>
    <f7-navbar title="Not found" back-link="Back"></f7-navbar>

    <f7-block strong>
      <p>Sorry</p>
      <p>Requested content not found.</p>
      <f7-list no-hairlines-md>
        <f7-list-input
          label="Name"
          type="text"
          placeholder="Your name"
          :value="name"
          @input="name=$event.target.value"
        ></f7-list-input>
        <f7-list-item
          title="Dynamic (Component) Route"
          link="/dynamic-route/blog/45/post/125/?foo=bar#about"
        ></f7-list-item>
    <f7-link href="/">Left Link</f7-link>

      </f7-list>
    </f7-block>
  </f7-page>
</template>
<script>
export default {
  data() {
    return {
      name: ""
    };
  },
  mounted() {
    console.log(`[404]`);
  },
  destroyed(){
    console.log('[404] Des')
  }
};
</script>