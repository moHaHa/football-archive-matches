<script setup lang="ts" generic="T extends any, O extends any">
const route = useRoute()
const router = useRouter()
const one = route.query.one
const two = route.query.two
const isPartOne = computed(() => route.query['current-part'] === 'one')
const isPartTwo = computed(() => route.query['current-part'] === 'two')
const next = computed(() => {
  const part = route.query['current-part'] === 'two' ? { text: 'Back', path: `/match?one=${one}&two=${two}&current-part=one` } : { text: 'Next', path: `/match?one=${one}&two=${two}&current-part=two` }
  return part
})
function go(path: string) {
  router.push(path)
}
</script>

<template>
  <div>
    <div mx-auto w-full lg:w-700px>
      <div mblg text-start text-lg>
        {{ isPartOne ? 'الشوط الاول' : isPartTwo ? 'الشوط الثاني' : 'part not found' }}
      </div>
      <div mb-lg>
        <MatchPlayer :url="route.query['current-part'] === 'two' ? one : two" />
      </div>
      <div flex justify-between>
        <button flex items-center btn @click="router.push('/')">
          <div i-carbon-home me-2px inline-block />
        </button>
        <button btn @click="go(next.path)">
          {{ next.text }}
        </button>
      </div>
    </div>
  </div>
</template>
