<template>
  <div class="columns is-mobile is-multiline is-gapless nft-emotion__main">
    <div
      class="column is-one-fifth nft-emotion__column"
      v-for="emoji in emojis"
      :key="emoji.key"
    >
      <b-tag id="emoji-box" type="is-dark is-large">
        {{ String.fromCodePoint(parseInt(emoji.key, 16)) }}
        <span class="nft-emotion-tag__count">{{ emoji.count }}</span>
      </b-tag>
    </div>
  </div>
</template>

<script lang="ts" >
import { Component, Prop, Vue, Watch } from 'vue-property-decorator';
import { Emotion } from '../service/scheme';

const issuerId = (emotion: Emotion) => emotion.issuer;

interface GroupedEmotion {
  [x: string]: Emotion[];
}

interface Emoji {
  key: string;
  count: number;
  issuers: string[];
}

@Component
export default class extends Vue {
  private value2: any;
  @Prop() public emotions!: GroupedEmotion;

  get emojis(): Emoji[] {
    return Object.entries(this.emotions).map(([key, emotions]) => ({
      key,
      count: emotions.length,
      issuers: emotions.map(issuerId)
    }));
  }
}
</script>

<style lang="scss">
@import "@/styles/variables";

.nft-emotion__main {
  margin-top: 1em;
}

.nft-emotion-tag__count {
  margin-left: 0.2rem;
}

.nft-emotion__image {
  width: 25px;
}

#emoji-box {
  border: 2px solid $primary;
}
</style>
