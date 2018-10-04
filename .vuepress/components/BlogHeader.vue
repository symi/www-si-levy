<template>
  <header>
    <h1>{{ title }}</h1>
    <sub>
      {{ date }}
      ·
      Tags:
      <template v-for="(tag, index) in tags">
        {{ tag }}<template v-if="index + 1 < tags.length">, </template>
      </template>
    </sub>
  </header>
</template>

<script>
import { format } from 'date-fns';

export default {
  computed: {
    title() {
      return this.$page.frontmatter.title;
    },
    date() {
      return format(this.$page.frontmatter.date, 'Do MMMM YYYY');
    },
    tags() {
      return this.$page.frontmatter.tags;
    }
  },
}
</script>
