index.html<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kerusso TV</title>
<style>
body {
    margin: 0;
    font-family: 'Segoe UI', sans-serif;
    background-color: #0e1a2b;
    color: white;
}
header {
    background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)),
    url('https://images.unsplash.com/photo-1504052434569-70ad5836ab65');
    background-size: cover;
    background-position: center;
    padding: 120px 20px;
    text-align: center;
}
header h1 {
    font-size: 3.5em;
    margin-bottom: 10px;
}
header p {
    font-size: 1.3em;
    max-width: 700px;
    margin: auto;
}
.btn {
    display: inline-block;
    margin: 15px;
    padding: 15px 35px;
    background-color: #f4c430;
    color: black;
    text-decoration: none;
    font-weight: bold;
    border-radius: 8px;
    transition: 0.3s;
}
.btn:hover {
    background-color: #ffd700;
}
.section {
    padding: 60px 20px;
    text-align: center;
}
.cards {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
}
.card {
    background-color: #1c2c44;
    padding: 20px;
    width: 280px;
    border-radius: 10px;
}
footer {
    background-color: #08101a;
    text-align: center;
    padding: 20px;
}
@media (max-width: 768px) {
    header h1 {
        font-size: 2.2em;
    }
    .cards {
        flex-direction: column;
        align-items: center;
    }
}
</style>
</head>
<body>

<header>
    <h1>Kerusso TV</h1>
    <p>Llevando el mensaje de Jesucristo con poder, revelación y verdad.</p>
    <a href="#" class="btn">🔴 Ver En Vivo</a>
    <a href="#" class="btn">🙏 Donar</a>
</header>

<section class="section">
    <h2>Últimas Prédicas</h2>
    <div class="cards">
        <div class="card">
            <h3>El Espíritu de Sabiduría</h3>
            <p>Basado en Isaías 11 – Revelación para estos tiempos.</p>
        </div>
        <div class="card">
            <h3>La Pesca Milagrosa</h3>
            <p>De escasez a abundancia – Lucas 5.</p>
        </div>
        <div class="card">
            <h3>Rompiendo Cisternas Rotas</h3>
            <p>Jeremías 2:13 – Restauración espiritual.</p>
        </div>
    </div>
</section>

<footer>
    © 2026 Kerusso TV | Todos los derechos reservados
</footer>

</body>
</html>
