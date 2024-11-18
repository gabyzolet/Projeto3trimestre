@import url('https://fonts.googleapis.com/css2?family=SUSE:wght@100..800&display=swap');

:root {
    --bg-color: #f8c8d8;  /* Cor de fundo suave */
    --primary-color: #f5a3c7;  /* Cor principal (um rosa suave) */
    --secondary-color: #db6cba; /* Cor secundária (um tom mais forte de rosa) */
    --font: "SUSE", sans-serif;
}

body {
    background-color: var(--bg-color);
    color: var(--primary-color);
    font-family: var(--font);
    height: 100vh;
    margin: 0;
}

header {
    background-color: var(--primary-color);
    text-align: center;
    padding: 1rem;
}

h1 {
    font-size: 2rem;
    color: white;
    font-weight: 700;
}

nav {
    display: flex;
    justify-content: center;
    font-weight: 400;
}

nav a {
    text-decoration: none;
    color: white;
    margin: 0 2rem;
    font-size: 1.2rem;
}

nav a:hover {
    text-decoration: underline;
    transform: scale(0.90);
    transition: transform 0.1s;
}

.graficos-container {
    margin: 5rem;
}

.graficos-container__texto {
    font-size: 1.3rem;
    text-align: center;
    padding: 2rem;
    border: var(--secondary-color) solid 2px;
}

span {
    font-weight: bold;
    color: var(--secondary-color);
}

footer {
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: var(--primary-color);
    color: white;
    width: 100%;
    height: 3rem;
    margin-top: 2rem;
}




html


<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Inserção de aplicativos nos colégios</title>
    <link rel="stylesheet" href="style.css">
    <script src="https://cdn.plot.ly/plotly-2.27.0.min.js" charset="utf-8"></script>
</head>
<body>
    <header>
        <h1>Relatório de Inserção de Aplicativos nos Colégios</h1>
        <nav>
            <a href="index.html">Mundo</a>
            <a href="#">Minha Escola</a>
        </nav>
    </header>
    <main class="graficos-section">
        <section id="graficos-container" class="graficos-container">
            <div class="graficos-container__texto">
                <p>
                    O uso de aplicativos educacionais tem crescido <span>exponencialmente</span> nas escolas. 
                    Veja abaixo os gráficos que ilustram essa evolução:
                </p>
            </div>
            <!-- Gráfico de barras -->
            <div id="grafico-1"></div>
        </section>
    </main>
    <footer>
        <p>Desenvolvido por Gab Zolet, Nay Gross, Sophi Melo, Lu Debona</p>
    </footer>
    <script type="module" src="graficos/common.js"></script>
    <script type="module" src="informacoesGlobais.js"></script>
    <script type="module" src="graficos/quantidadeUsuarios.js"></script>

    <script>
        // Dados do gráfico de barras
        var trace1 = {
            x: ['Dentro da escola', 'Mundo'],
            y: [31, 34],
            name: 'Apoiam',
            type: 'bar',
            marker: {color: '#db6cba'}  // Cor rosa forte para as barras de apoio
        };

        var trace2 = {
            x: ['Dentro da escola', 'Mundo'],
            y: [69, 66],
            name: 'Não Apoiam',
            type: 'bar',
            marker: {color: '#f5a3c7'}  // Cor rosa mais suave para as barras de não apoio
        };

        var data = [trace1, trace2];

        var layout = {
            barmode: 'stack',
            title: 'Opinião sobre a inserção de aplicativos nos colégios',
            xaxis: {
                title: 'Contexto'
            },
            yaxis: {
                title: 'Porcentagem (%)'
            },
            paper_bgcolor: '#f8c8d8',  // Fundo da área do gráfico
            plot_bgcolor: '#f8c8d8'  // Fundo da área do gráfico
        };

        // Renderizando o gráfico
        Plotly.newPlot('grafico-1', data, layout);
    </script>
</body>
</html>
