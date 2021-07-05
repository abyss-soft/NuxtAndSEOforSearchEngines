<template>
  <div class="l-container">
    <h2 class="search__title">
      Обработка данных...
    </h2>
  </div>
</template>

<script>
export default {
  name: 'Search',
  mounted() {
    const ourURL = 'https://abyss-soft.ucoz.ru/'; // Place the url here on your website, for example https://abyss-soft.ucoz.ru/
    const url = new URL(window.location.href);
    const urlNormalize = url.search.replace(/%2F/g, '/').replace(/%3A/g, ':');
    if (url.pathname === '/yandbtm') {
      const indexStartURL = urlNormalize.indexOf('url=');
      const indexEndtURL = urlNormalize.indexOf('&', indexStartURL + 1);
      const patchToGo = urlNormalize.substring(indexStartURL + 4, indexEndtURL);
      if (patchToGo && patchToGo.length > 20) {
        document.location.href = patchToGo;
      } else {
        document.location.href = ourURL;
      }
    }
  },
};
</script>

<style lang="scss" scoped>
.search__title {
  font-family: 'ALS Schlange', sans-serif;
  font-style: normal;
  font-weight: bold;
  font-size: 36px;
  line-height: 36px;
  color: #1e1f1d;
  text-align: center;
  margin: 2rem 0;
}
</style>
