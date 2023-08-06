<script setup lang="ts" generic="T extends any, O extends any">
import { matchs } from '~/data/matchs'

const data = ref(matchs)
</script>

<template>
  <div>
    <div mx-auto w-full lg:w-700px>
      <div flex flex-wrap>
        <router-link v-for="(match, index) in data" :key="index" w="50% lg:33%" :to="`/match?one=${match.one}&two=${match.tow}&current-part=one`" px-5px pb-20px lg:px-10px>
          <div h-full rounded-lg>
            <img :src="match.thumbnail" w="100%" rounded-lg>
          </div>
        </router-link>
      </div>
    </div>
  </div>
</template>
