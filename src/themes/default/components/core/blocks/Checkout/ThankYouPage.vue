<template>
  <div>
    <header class="thank-you-title bg-cl-secondary py35 pl20">
      <div class="container">
        <breadcrumbs
          :routes="[{name: 'Homepage', route_link: '/'}]"
          :active-route="this.$t('Order confirmation')"
        />
        <h2 class="category-title">
          {{ $t('Order confirmation') }}
        </h2>
      </div>
    </header>
    <div class="thank-you-content py40 pl20">
      <div class="container">
        <div class="row">
          <div class="col-md-6">
            <h4>
              {{ $t('Your purchase') }}
            </h4>
            <p v-online v-html="this.$t('You have successfuly placed the order. You can check status of your order by using our <b>delivery status</b> feature. You will receive an order confirmation e-mail with details of your order and a link to track its progress.')" />
            <p v-online v-html="this.$t('E-mail us at <b>demo@vuestorefront.io</b> with any questions, seuggestions how we could improve products or shopping experience')"/>
            <p v-offline>
              {{ $t('Your order will be sent to the server as soon as you connect to the Internet and then confirmed regarding the stock quantities of selected items') }}
            </p>
            <div id="thank-you-extensions"/>
            <h4>
              {{ $t('Your Account') }}
            </h4>
            <p v-html="this.$t('You can log to your account using e-mail and password defined earlier. On your account you can <b>edit you\'r profile data,</b> check <b>history of transactions,</b> edit <b>subscription to newsletter.</b>')"/>
          </div>
          <div class="col-md-6 bg-cl-secondary thank-you-improvment">
            <h4>
              {{ $t('What we can improve?') }}
            </h4>
            <p class="mb25">
              {{ $t('Your feedback is important fo us. Let us know what we could improve.') }}
            </p>
            <form action="mailto:contributors@vuestorefront.io">
              <base-textarea
                class="mb25"
                type="text"
                name="body"
                value=""
                :placeholder="$t('Type your opinion')"
                :autofocus="true"
              />
              <button-outline color="dark">
                {{ $t('Give a feedback') }}
              </button-outline>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Composite from 'core/mixins/composite'
import Breadcrumbs from 'theme/components/core/Breadcrumbs'
import BaseTextarea from 'theme/components/core/blocks/Form/BaseTextarea'
import ButtonOutline from 'theme/components/theme/ButtonOutline'

export default {
  name: 'ThankYouPage',
  mixins: [Composite],
  components: {
    BaseTextarea,
    Breadcrumbs,
    ButtonOutline
  }
}
</script>

<style lang="scss">
  .thank-you-content {
    padding-left: 0;

    p {
      line-height: 25px
    }

    @media (min-width: 64em) {
      h4 {
        font-size: 24px;
      }
    }
  }
  .thank-you-improvment {
    padding: 20px 10px;

    @media (min-width: 64em) {
      padding: 20px 40px;
    }

    textarea {
      min-height: 100px;
    }
  }
</style>
