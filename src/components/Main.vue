<template>
  <Page class="page">
    <ActionBar class="action-bar" title="Calculadora">
    </ActionBar>

    <StackLayout>
      <Label class="operations" :text="lcd"/>
      <Label class="partial" :text="partial"/>
      <FlexboxLayout class="buttons">
        <FlexboxLayout class="numbers" flexWrap="wrap">
          <Button v-for="i in 9" @tap="addNumber(i)" class="number" :key="i">{{i}}</Button>
          <Button class="number" @tap="addNumber('.')">.</Button>
          <Button class="number" @tap="addNumber(0)">0</Button>
          <Button class="number">=</Button>
        </FlexboxLayout>
        <FlexboxLayout flexDirection="column" class="actions">
          <Button>DEL</Button>
          <Button>-</Button>
          <Button>+</Button>
          <Button>x</Button>
          <Button>/</Button>
        </FlexboxLayout>
      </FlexboxLayout>
    </StackLayout>
  </Page>
</template>

<script>
  export default {
    data () {
      return {
        lcd: 0,
        surprise: false
      };
    },
    methods: {
      addNumber(n) {
        this.lcd = n;
        this.partial = n;
      }
    }
  };
</script>

<style scoped>
  Button {
    margin: 0;
    font-size: 26;
    border-radius: 1%;
    color: white;
    background-color: #0097e6;
  }
  Label {
    font-size: 32;
    text-align: right;
    background: #fff;
    color: #111;
    padding: 20;
  }
  .partial {
    font-size: 25;
    color: #aaa;
  }
  .number {
    width: 33.3333%
  }
  .actions Button {
    height: 21%;
    background: #192a56;
  }
  .numbers {
    width: 80%;
    height: 100%;
  }
</style>
