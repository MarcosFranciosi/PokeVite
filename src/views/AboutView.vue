<template>
  <div class="container mt-4">
    <div class="card card-about shadow-lg">
      <div class="card-body text-center">
        <h1 class="display-4 mb-4">PokeVite Project</h1>
        
        <div class="row justify-content-center">
          <div class="col-md-8">
            <p class="lead">
              Este projeto foi desenvolvido para demonstrar o uso do <strong>Vue 3</strong> com a 
              <strong>PokeAPI</strong>, explorando conceitos modernos de desenvolvimento web.
            </p>
            <hr class="my-4">
          </div>
        </div>

        <div class="row mt-3">
          <div class="col-md-6 offset-md-3">
            <h3 class="h5 mb-3 text-secondary">Objetivos do Projeto:</h3>
            <ul class="list-group list-group-flush text-start mb-4">
              <li class="list-group-item bg-transparent border-0">✅ Consumo de API REST (PokeAPI)</li>
              <li class="list-group-item bg-transparent border-0">✅ Gerenciamento de estado com Composition API</li>
              <li class="list-group-item bg-transparent border-0">✅ Componentização e Props</li>
              <li class="list-group-item bg-transparent border-0">✅ Filtragem reativa com Computed Properties</li>
            </ul>
          </div>
        </div>

        <div class="tech-stack mt-4">
          <span class="badge rounded-pill bg-primary mx-1 p-2 px-3">Vue 3</span>
          <span class="badge rounded-pill bg-info mx-1 p-2 px-3">Vite</span>
          <span class="badge rounded-pill bg-success mx-1 p-2 px-3">Bootstrap 5</span>
          <span class="badge rounded-pill bg-warning text-dark mx-1 p-2 px-3">JavaScript</span>
        </div>
      </div>
      
      <div class="card-footer text-muted text-center py-3">
        Desenvolvido por <strong>Marcos Franciosi</strong> - 2026
      </div>
    </div>
  </div>
</template>

<style scoped>
.card-about {
  background: rgba(255, 255, 255, 0.9);
  border-radius: 15px;
  border: none;
  transition: transform 0.3s ease;
}

.card-about:hover {
  transform: translateY(-5px);
}

h1 {
  color: #002996;
  font-weight: bold;
}

.tech-stack .badge {
  font-size: 0.9rem;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

@media (max-width: 768px) {
  .container {
    padding-bottom: 2rem;
  }
}
</style>