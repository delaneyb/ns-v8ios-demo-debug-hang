<template>
    <Page>
        <ActionBar>
            <Label text="Home"/>
        </ActionBar>

        <StackLayout>
            <Label class="info" @tap="tapped">
                <FormattedString>
                    <Span class="fas" text.decode="&#xf135; "/>
                    <Span :text="message"/>
                </FormattedString>
            </Label>
            <StackLayout height="40" width="40" :background="color" />
        </StackLayout>
    </Page>
</template>

<script>
  export default {
      data() {
          return {
              color: 'black'
          }
      },
    computed: {
      message() {
        return "Blank {N}-Vue app";
      }
    },
    methods: {
        tapped() {
            console.log(`Label was tapped`);
            debugger
            this.color = this.color === 'black' ? 'white' : 'black'
        }
    }
  };
</script>

<style scoped lang="scss">
    @import '~@nativescript/theme/scss/variables/blue';

    // Custom styles
    .fas {
        @include colorize($color: accent);
    }

    .info {
        font-size: 20;
        horizontal-align: center;
        vertical-align: center;
    }
</style>
