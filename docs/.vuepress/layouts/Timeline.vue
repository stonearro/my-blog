<script setup>
import { useBlogType } from '@vuepress/plugin-blog/client'
import { usePageFrontmatter } from 'vuepress/client'
import ParentLayout from '@vuepress/theme-default/layouts/Layout.vue'

import ArticleList from '../components/ArticleList.vue'

const timelines = useBlogType('timeline')
const frontmatter = usePageFrontmatter()
</script>

<template>
  <ParentLayout>
    <template #page>
      <main class="page">
        <h1 class="timeline-title">{{ frontmatter.title }}</h1>

        <ArticleList :items="timelines.items" is-timeline />
      </main>
    </template>
  </ParentLayout>
</template>

<style lang="scss">
.timeline-title {
  padding-top: calc(var(--navbar-height) + 1rem) !important;
  text-align: center;
}
</style>
