<template>
  <div class="columns mb-1">
    <div class="column is-8 is-offset-2">
      <section>
        <br />
        <SpotlightTable />
      </section>
    </div>
  </div>
</template>
<script lang="ts" >
import { Component, Vue } from 'vue-property-decorator';

@Component<Leaderboard>({
  components: {
    Identity: () => import('@/components/shared/format/Identity.vue'),
    SpotlightTable: () => import('@/components/spotlight/SpotlightTable.vue')
  }
})
export default class Leaderboard extends Vue {
  public creators: any = [
    'Dx6nVUy6f2znn4ZwNZ3TGbEyUz3FLbCRGQGKAut4LxjCVRs',
    'J6mwrrDE5ZywDe8T4mWgsdgHCcrDcrVtoGh37i7PSaZARRs',
    'FqCJeGcPidYSsvvmT17fHVaYdE2nXMYgPsBn3CP9gugvZR5',
    'DmUVjSi8id22vcH26btyVsVq39p8EVPiepdBEYhzoLL8Qby',
    'CxQJNQeowRUJBgUHQpspudWy4BU6Rk2u93yDZEKe6GzcLDe',
    'GHuTwhh9txr69tHBM2f1mPE6tWn9XCYKMi3nRNFrYvGv9Yy',
    'CuHWHNcBt3ASMVSJmcJyiBWGxxiWLyjYoYbGjfhL4ovoeSd',
    'ESRGCgBvTnuWkjeQs9G5W5hhXa4XuquXHJMtkDVQFvNUAb5',
    'H1bSKJxoxzxYRCdGQutVqFGeW7xU3AcN6vyEdZBU7Qb1rsZ',
    'Ea34UVcfamiLCFSRXD1bc4HRbZzsoo8RsTfKj2cDtf8GUdZ',
    'H4XB5xxo1YhDmBf3fVnobqDJPnEuF1m2GTctdkiXSPNchy5',
    'HnccMvwD4zsrG2mdyyiZvNCvDgMPZKrMA4BGHkT17c3KfkP',
    'EB1oqZ5MEnEwxhJ5DySCH3pyY55a2CUDfAbYKmLz2QcqWgx',
    'ERyyXEbUDa5AEMqY8dM7Nrtt6WY4BEAb65y1nbCmgE3rtQi',
    'FLPSoZhUwJwZvGwihQbrnF7aNYP62GaNKmDKDoiVZFe3TaQ',
    'HRL2QctmfjgFPLCSaiDJThYShQy7V4KvJqLWCY6pga6AEnE',
    'Gskn3eRyr3tDiKxhzU1MPG4ha8RFTBG9ft3C6Rrn3kGJMXn',
    'EB1oqZ5MEnEwxhJ5DySCH3pyY55a2CUDfAbYKmLz2QcqWgx',
    'Eki6rrJtqfF5RA7gshbe9twhL3umQRebqdWxRkUoLRtofHv',
    'DFxLeonhy3wNSDPVh5uqyai31vsMp2rY7SSJiM7dK6WQSgn'
    // 'HtRTwHSP6fYC5PtCsJ7pG4H1hwyPhzXbtVTTVRJ6kvfPFe1', did not set identity
    // 'Cu7QaEnRGPE91WvLduzUii2ZNa3jhMWtmB8SYwumycNRmoN' did not set identity
  ];
}
</script>
