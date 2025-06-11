function responderQuiz(opcao) {
  const resposta = document.getElementById("respostaQuiz");
  if (opcao === 2) {
    resposta.innerText = "✅ Correto! A chance é de 50%.";
    resposta.style.color = "green";
  } else {
    resposta.innerText = "❌ Errado. Tente novamente.";
    resposta.style.color = "red";
  }
}

function mostrarDesafio() {
  document.getElementById("respostaDesafio").style.display = "block";
}

// Gráfico de probabilidades com Chart.js
const ctx = document.getElementById('graficoDado').getContext('2d');
new Chart(ctx, {
  type: 'pie',
  data: {
    labels: ['1', '2', '3', '4', '5', '6'],
    datasets: [{
      label: 'Probabilidade (%)',
      data: [16.67, 16.67, 16.67, 16.67, 16.67, 16.67],
      backgroundColor: [
        '#0066cc', '#3399ff', '#66ccff', '#99ccff', '#cce5ff', '#003366'
      ]
    }]
  },
  options: {
    responsive: true,
    plugins: {
      legend: { position: 'bottom' },
      title: { display: true, text: 'Probabilidade de cada número em um dado' }
    }
  }
});
