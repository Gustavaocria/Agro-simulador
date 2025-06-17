# Agro-simulador
/* Estilos globais para o corpo da página */
body {
    font-family: 'Inter', sans-serif;
    /* Fundo bonito com um gradiente suave de verde e azul, simulando céu e campo */
    background: linear-gradient(to bottom right, #a7f3d0, #6ee7b7, #34d399); /* Cores vibrantes e suaves */
    display: flex;
    justify-content: center;
    align-items: flex-start; /* Alinha no topo para permitir rolagem se necessário */
    min-height: 100vh;
    padding: 20px;
    box-sizing: border-box;
    color: #334155; /* Cor de texto padrão */
}

/* Estilos para o contêiner principal do simulador */
.simulator-container {
    background-color: rgba(255, 255, 255, 0.95); /* Fundo branco semi-transparente */
    border-radius: 1.5rem; /* Bordas arredondadas */
    box-shadow: 0 15px 30px -5px rgba(0, 0, 0, 0.2), 0 6px 12px -3px rgba(0, 0, 0, 0.1); /* Sombra mais pronunciada */
    padding: 2.5rem;
    max-width: 900px; /* Largura máxima para desktops */
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 2rem;
    animation: fadeIn 1s ease-out; /* Animação de entrada */
    backdrop-filter: blur(5px); /* Efeito de desfoque no fundo */
}

@keyframes fadeIn {
    from { opacity: 0; transform: translateY(-20px); }
    to { opacity: 1; transform: translateY(0); }
}

/* Estilos para botões primários (Comprar/Iniciar) - MAIS TECNOLÓGICOS */
.btn-primary {
    background: linear-gradient(145deg, #22c55e, #10b981); /* Gradiente de verde */
    color: white;
    padding: 0.75rem 1.75rem;
    border-radius: 0.75rem;
    font-weight: 700; /* Mais negrito */
    transition: all 0.3s ease-in-out; /* Transição mais suave para todas as propriedades */
    cursor: pointer;
    border: none;
    box-shadow: 0 5px 15px rgba(34, 197, 94, 0.4); /* Sombra colorida */
    text-transform: uppercase; /* Texto em maiúsculas */
    letter-spacing: 0.05em; /* Espaçamento entre letras */
}

.btn-primary:hover {
    background: linear-gradient(145deg, #10b981, #22c55e); /* Inverte o gradiente no hover */
    transform: translateY(-3px) scale(1.02); /* Leve levantamento e aumento */
    box-shadow: 0 8px 20px rgba(34, 197, 94, 0.6); /* Sombra mais intensa */
}

.btn-primary:active {
    transform: translateY(0); /* Volta ao normal no clique */
    box-shadow: 0 2px 5px rgba(34, 197, 94, 0.2); /* Sombra menor */
}

/* Estilos para botões secundários (Reiniciar) - MAIS TECNOLÓGICOS */
.btn-secondary {
    background: linear-gradient(145deg, #60a5fa, #3b82f6); /* Gradiente de azul */
    color: white; /* Texto branco para contraste */
    padding: 0.75rem 1.75rem;
    border-radius: 0.75rem;
    font-weight: 700;
    transition: all 0.3s ease-in-out;
    cursor: pointer;
    border: none;
    box-shadow: 0 5px 15px rgba(59, 130, 246, 0.4); /* Sombra colorida */
    text-transform: uppercase;
    letter-spacing: 0.05em;
}

.btn-secondary:hover {
    background: linear-gradient(145deg, #3b82f6, #60a5fa); /* Inverte o gradiente no hover */
    transform: translateY(-3px) scale(1.02);
    box-shadow: 0 8px 20px rgba(59, 130, 246, 0.6);
}

.btn-secondary:active {
    transform: translateY(0);
    box-shadow: 0 2px 5px rgba(59, 130, 246, 0.2);
}

/* Estilos para inputs e selects */
input[type="number"],
select {
    border: 1px solid #9ca3af; /* Borda cinza um pouco mais escura */
    border-radius: 0.5rem;
    padding: 0.6rem 1rem;
    width: 100%;
    box-sizing: border-box;
    transition: border-color 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
    background-color: #f9fafb; /* Fundo levemente acinzentado */
}

input[type="number"]:focus,
select:focus {
    outline: none;
    border-color: #22c55e; /* Verde no foco */
    box-shadow: 0 0 0 4px rgba(34, 197, 94, 0.3); /* Sombra mais destacada no foco */
}

/* Classes para mensagens */
.message-box {
    padding: 1rem;
    border-radius: 0.75rem;
    font-weight: 600; /* Mais negrito */
    margin-top: 1rem;
    display: none; /* Escondido por padrão */
    opacity: 0;
    transition: opacity 0.3s ease-out, transform 0.3s ease-out; /* Adiciona transição para transform */
    transform: translateY(10px); /* Começa um pouco abaixo */
}

.message-box.show {
    display: block;
    opacity: 1;
    transform: translateY(0); /* Desliza para cima */
}

.message-success {
    background-color: #dcfce7; /* Verde claro */
    color: #16a34a; /* Verde escuro */
    border: 1px solid #86efac;
}

.message-error {
    background-color: #fee2e2; /* Vermelho claro */
    color: #ef4444; /* Vermelho escuro */
    border: 1px solid #fca5a5;
}

/* Layout responsivo com Flexbox para seções */
.section-grid {
    display: flex;
    flex-wrap: wrap; /* Permite que os itens quebrem para a próxima linha */
    gap: 1.5rem; /* Espaçamento entre as colunas */
}

.section-grid > div {
    flex: 1 1 calc(50% - 0.75rem); /* Cada item ocupa cerca de metade da largura */
    min-width: 300px; /* Largura mínima para evitar que fiquem muito estreitos */
    background-color: #f0fdf4; /* Fundo para as seções de compra/venda */
    border-radius: 1rem;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.08);
}

/* Responsividade para telas menores */
@media (max-width: 768px) {
    .simulator-container {
        padding: 1.5rem;
    }
    .section-grid > div {
        flex: 1 1 100%; /* Em telas pequenas, cada item ocupa a largura total */
    }
}
