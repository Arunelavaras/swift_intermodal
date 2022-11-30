
<template>
    <footer role="contentinfo">
    <div class="content">
        <div class="site-info">
            Copyright ©2022 Swift Transportation Inc. <span><br></span>Contact Us: <a
            href="mailto:support@swiftintermodal.com">support@swiftintermodal.com</a>.
        </div>      
    </div>
</footer>
</template>

<script  lang="ts">
import { defineComponent } from 'vue';
export default defineComponent ({
  name:'FooterPage'
})
</script>
<style scoped>
footer[role="contentinfo"] {
    position: fixed;
    width: 100%;
    height:60px;
    /* padding: 0.9375rem 0 2.125rem;  */
    background: black;
    color: #666;
    font-size: 0.875rem;
    text-align: center;
    bottom:0;
}
.site-info{
    margin: 20px;
}
</style>