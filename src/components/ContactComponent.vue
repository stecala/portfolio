<template>
  <div class="row justify-content-between">
    <div class="col-12 col-md-6">
      <div class="col-12">
        <h1 class="pt-4">Let's get in touch!</h1>
      </div>
      <div class="col-9 mt-5 mt-md-4">
        <p>Now that I have your attention, feel free to follow me on my social media or directly contact me by e-mail.</p>
      </div>
    </div>
    <div class="col-6 col-md-4 d-flex align-items-center mt-3">
        <a class="button-53" role="button" href="mailto:calarotastefano@gmail.com">TEXT ME!</a>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
h1{
  font-weight: 700;
}
.button-53 {
  background-color: var(--title-color);
  border: 0 solid #E5E7EB;
  box-sizing: border-box;
  color: white;
  display: flex;
  font-family: ui-sans-serif,system-ui,-apple-system,system-ui,"Segoe UI",Roboto,"Helvetica Neue",Arial,"Noto Sans",sans-serif,"Apple Color Emoji","Segoe UI Emoji","Segoe UI Symbol","Noto Color Emoji";
  font-size: 1rem;
  font-weight: 700;
  justify-content: center;
  line-height: 1.75rem;
  padding: .75rem 1.65rem;
  position: relative;
  text-align: center;
  text-decoration: none white solid;
  text-decoration-thickness: auto;
  width: 100%;
  max-width: 460px;
  position: relative;
  cursor: pointer;
  transform: rotate(-2deg);
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
}

.button-53:focus {
  outline: 0;
}

.button-53:after {
  content: '';
  position: absolute;
  border: 1px solid white;
  bottom: 4px;
  left: 4px;
  width: calc(100% - 1px);
  height: calc(100% - 1px);
}

.button-53:hover:after {
  bottom: 2px;
  left: 2px;
}

@media (min-width: 768px) {
  .button-53 {
    padding: .75rem 3rem;
    font-size: 1.25rem;
  }
}
</style>