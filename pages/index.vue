<template>
  <main>
    <ContentDoc />
    <hr />

    <h2>ContentList does not (?) works with a path prop to articles</h2>
    <p>
      <em
        >It shows only the one content at /articles, shouldn't it show all the
        articles?</em
      >
    </p>
    <ContentList path="/articles" v-slot="{ list }">
      <div v-for="article in list" :key="article._path">
        <h3>{{ article.title }}</h3>
        <p>{{ article.description }}</p>
        <NuxtLink :to="article._path">Link</NuxtLink>
      </div>
    </ContentList>

    <hr />

    <h2>ContentList kind of work with an empty "" path prop</h2>
    <p>
      <em
        >It shows all the content but only if I put an path prop with an empty
        string</em
      >
    </p>
    <ContentList path="" v-slot="{ list }">
      <div v-for="article in list" :key="article._path">
        <h3>{{ article.title }}</h3>
        <p>{{ article.description }}</p>
        <NuxtLink :to="article._path">Link</NuxtLink>
      </div>
    </ContentList>
  </main>
</template>

<script setup></script>

<style lang="css" scoped>
h2 {
  color: blue;
}
</style>
