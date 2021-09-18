<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <a class="navbar-brand brand" href="/">
      <img
        src="../assets/logo.svg"
        width="60"
        class="d-inline-block align-top"
        alt=""
      />
      MovieInfo
    </a>
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarNav"
      aria-controls="navbarNav"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item">
          <a class="nav-link" href="/buscar">Buscar</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="/about">Sobre nosotros</a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>
img {
  margin: 0 40px;
}

.brand {
  display: flex;
  align-items: center;
}
</style>