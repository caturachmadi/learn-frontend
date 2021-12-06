<template>
  <div id="app">
    <div class="main-wrapper">
      <!-- components sidebar/partials -->
      <partials-navbar />
      <!-- components sidebar/partials -->
      <partials-sidebar />

      <!-- Main Content -->
      <div class="main-content">
        <section class="section">
          <div class="section-header">
            <h1>JMIS ( Jig Manufacture Information System )</h1>
          </div>

          <div class="section-body"></div>
          <Nuxt />
        </section>
      </div>
      <!-- component footer/partials -->
      <partials-footer />
    </div>
  </div>
</template>
