# Livia IA - Assistente & Simulador Corporal 3D com Chat em Tempo Real

Este é um aplicativo web interativo que combina um cenário tridimensional avançado com uma interface de inteligência artificial em tempo real. O projeto renderiza uma personagem com proporções esculturais baseadas em curvas de violão (estilo Lívia Andrade), contando com um sistema dinâmico de fios de cabelo procedurais e um motor de chat ativo para comunicação imediata.

## 🚀 Recursos Principais

- **Chat em Tempo Real Integrado:** Caixa de diálogo ativa na barra lateral que processa as entradas do usuário instantaneamente e gera respostas dinâmicas da assistente Livia IA.
- **Visualização 3D Fluida:** Renderização nativa de alta performance utilizando a biblioteca **Three.js** com iluminação de estúdio (luz ambiente, direcional e contra-luz azulada).
- **Customização Corporal Dinâmica (Live Slider Engine):** Sliders interativos que alteram em tempo real a escala anatômica da personagem (Busto volumétrico, Cintura fina e Quadril em formato ampulheta).
- **Sistema de Cabelo Fio a Fio:** Geração procedural de 60 mechas independentes usando Curvas de Bézier em 3D. O algoritmo calcula automaticamente as coordenadas para que o cabelo contorne o rosto perfeitamente, **respeitando estritamente o espaço facial** e limpando a área dos olhos e boca.
- **Estados de Movimento:** Animações coordenadas disparadas pela interface para alternar entre os modos **Andar** (passarela) e **Agachar** (rebaixamento suave do centro de gravidade).

## 🛠️ Tecnologias Utilizadas

- **HTML5 & CSS3:** Design futurista cibernético com efeitos de desfoque de fundo (`backdrop-filter`).
- **JavaScript (ES6+):** Motor assíncrono para captura, envio e exibição de mensagens do chat em tempo real.
- **Three.js (r128):** Criação do ambiente tridimensional, matrizes de luz e materiais realistas (`MeshStandardMaterial`).
- **GSAP (GreenSock Animation Platform):** Suavização de movimentos e transições físicas na interface.

## 💬 Como Funciona o Chat em Tempo Real

O sistema de mensagens foi unificado diretamente ao ciclo de eventos da página:
1. **Captura do Input:** O aplicativo monitora o campo `.chat-input` esperando o clique no botão de envio (`.chat-send`) ou o pressionamento da tecla *Enter*.
2. **Processamento e Resposta:** O texto é integrado instantaneamente ao painel. O motor interno responde de volta simulando o comportamento da inteligência artificial em tempo real.

## 🔧 Como Executar o Projeto

1. Salve o arquivo principal da aplicação como `index.html`.
2. Certifique-se de estar conectado à internet para que as dependências oficiais carregadas via CDN (Three.js, GSAP, FontAwesome) funcionem.
3. Abra o arquivo `index.html` em qualquer navegador web moderno.
4. Clique no menu flutuante (☰) no canto superior direito para abrir o painel da **Livia IA**, ajustar as medidas e iniciar o chat.
