<template>
  <b-navbar
    fixed-top
    spaced
    wrapper-class="container"
    :close-on-click="false"
    >
    <template #brand>
      <b-navbar-item tag="router-link" :to="{ path: '/' }" class="logo">
        <img
          src="/kodadot_lgbt_320px.png"
          alt="First NFT market explorer on Kusama and Polkadot"
          class="logo__img"
        >
      </b-navbar-item>
    </template>
    <template v-slot:start class="start">
      <b-navbar-dropdown
          arrowless
          collapsible
          >
          <template #label>
            <span>{{ $t('Create') }}</span>
          </template>
          <b-navbar-item
            tag="router-link"
            :to="{ name: 'rmrk'}">
            {{ $t('Classic') }}
          </b-navbar-item>
          <b-navbar-item
            tag="router-link"
            :to="{ name: 'simpleMint'}">
            {{ $t('Simple') }}
          </b-navbar-item>
      </b-navbar-dropdown>
      <b-navbar-item
        tag="router-link"
        :to="{ name: 'nft'}">
        {{ $t('Gallery') }}
      </b-navbar-item>
      <b-navbar-item
        tag="router-link"
        :to="{ name: 'spotlight'}">
        {{ $t('Spotlight') }}
      </b-navbar-item>
      <b-navbar-dropdown
          arrowless
          collapsible
          label="Extra">
          <b-navbar-item
            tag="router-link"
            :to="{ name: 'rmrkCredit' }">
            {{ $t('Credit') }}
          </b-navbar-item>
          <b-navbar-item
            tag="router-link"
            :to="{ name: 'rmrkFaq'}">
            {{ $t('FAQ') }}
          </b-navbar-item>
          <b-navbar-item
            tag="router-link"
            :to="{ name: 'settings'}">
            {{ $t('Settings') }}
          </b-navbar-item>
      </b-navbar-dropdown>
    </template>
    <template v-slot:end>
      <LocaleChanger />
      <NavbarProfileDropdown />
    </template>
  </b-navbar>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import LocaleChanger from '@/components/shared/SwitchLocale.vue';
import NavbarProfileDropdown from '@/components/rmrk/Profile/NavbarProfileDropdown.vue'
import { getCurrentColor } from '@/colors'
import i18n from '@/i18n.ts';

@Component({
  components: {
    LocaleChanger,
    NavbarProfileDropdown
  }
})
export default class NavbarMenu extends Vue {
  private color: string = getCurrentColor()
  public navbar: any = [
    {
      name: i18n.t('Gallery'),
      tag: 'router-link',
      to: { name: 'nft' },
      strong: true
    },
  ]
  public navbarExtra: any = [
    {
      name: i18n.t('Accounts'),
      icon: 'users',
      to: { name: 'accounts' },
      tag: 'router-link',
    },
    {
      name: i18n.t('Credit'),
      icon: 'users',
      to: { name: 'rmrkCredit' },
      tag: 'router-link',
      strong: true
    },
    {
      name: i18n.t('Transfer'),
      icon: 'paper-plane',
      to: { name: 'transfer' },
      tag: 'router-link',
    },
    {
      name: i18n.t('Settings'),
      icon: 'cogs',
      tag: 'router-link',
      to: { name: 'settings' },
    },
  ]
  private navbarExternal: any = [
    {
      name: 'Twitter',
      tag: 'a',
      href: 'https://twitter.com/Kodadot'
    }
  ]

  // get chainColor() {
  //   return {
  //     'border-bottom': `4px ${this.color} solid`
  //   }
  // }
}
</script>

<style lang="scss">
@import '@/styles/variables';

.navbar {
  &.is-spaced {
    & > .container {
      .navbar-menu {
        margin-right: 0;
      }
    }
  }

  .logo {
    padding: 0.5rem 0.75rem;

    @include desktop {
      padding-left: 0;
    }
  }

  .navbar-item {
    text-transform: uppercase;
    font-weight: 500;
  }

  .navbar-brand {
    align-items: center;
  }

  .burger {
    margin-right: 0.5rem;
  }
  .navbar-dropdown{
    box-shadow: 0px 0px 5px 0.5px #d32e79 !important;
  }
}
</style>
