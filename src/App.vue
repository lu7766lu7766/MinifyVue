<template>
  <section>
    <h1>hello {{ moment().getDateTime() }}{{ _(this).getVal("a") }}</h1>
    <button
      @click="
        $open('http://www.google.com', 'google', {
          height: 600,
          width: 800
        })
      "
    >
      open
    </button>
  </section>
</template>

<script>
export default {
  data: () => ({
    a: 'aa'
  }),
  methods: {
    counter() {
      return new Promise(resolve => {
        setTimeout(() => {
          resolve(99)
        }, 2000)
      })
    }
  },
  async mounted() {
    const res = await this.counter()
    console.log(res)
  }
}
</script>