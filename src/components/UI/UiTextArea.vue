<template>
<div class="wrapper">
  <textarea
    class="ui-textarea"
    type="text"
    :value="value"
    :placeholder="placeholder"
    @input="$emit('update:value', $event.target.value)"
  ></textarea>
  <div class="error" v-for="error of errors" :key="error.$uid">
    <span class="error__msg">{{ error.$message }}</span>
  </div>
</div>
</template>

<script>
  export default {
    name: "ui-textarea",
    props: {
      value: String,
      placeholder: String,
      errors: Array,
    }
  }
</script>

<style lang="scss" scoped>
@import '@/styles/mixins.scss';

.wrapper {
  max-width: 450px;
  width: 100%;

  @include tablets {
    width: 90%;
  }

  @include phones {
    max-width: 380px;
  }
}

.ui-textarea {
  max-width: 450px;
  width: 100%;
  margin-bottom: 20px;
  padding: 15px 20px;
  font-size: 20px;
  border-radius: 5px;
  box-sizing: border-box;
  border: 1px solid gray;
  background: transparent;
  color: #fafafa;
  outline: none;

  @include tablets {
    font-size: 16px;
    margin-bottom: 15px;
    padding: 10px 15px;
  }

  @include phones {
    font-size: 14px;
    margin-bottom: 10px;
    padding: 10px 10px;
  }

  &:focus {
    box-shadow: 0 0 15px #2c3e50;
  }
}

.error {
  width: 100%;
  text-align: left;
  color: rgb(161, 0, 0);
  margin-top: -10px;
  padding: 0 0 10px 20px;

  @include tablets {
    padding-left: 15px;
  }

  @include phones {
    padding-left: 10px;
  }

  &__msg {
    font-size: 16px;
    font-weight: 400;
    line-height: 1.1;

    @include tablets {
      font-size: 14px;
    }

    @include phones {
      font-size: 12px;
    }
  }
}
</style>