# 🌟 IA Boneca 3D — Sistema Paramétrico & Materialização por Visão Computacional

Uma aplicação web interativa 3D de alta performance construída com **Three.js** e **MediaPipe Pose (Google)**. O projeto implementa um modelo feminino procedural com **90 variações anatômicas por categoria**, física de animação em tempo real e um sistema de **materialização e reconhecimento de biotipo a partir de fotos** por visão computacional.

---

## ⚡ Destaques do Projeto

- **🔒 Estado Inicial Invisível (Holograma):** A personagem é renderizada inicialmente como um holograma futurista com anéis de energia e só é revelada ao carregar uma foto ou acionar a revelação manual.
- **📷 Materialização por Foto IA:** Integração com **MediaPipe Pose** para detecção precisa de pontos anatômicos (*landmarks*), calculando proporções reais de ombros, cintura, quadris e membros.
- **🎨 Extração Dinâmica de Cores:** Algoritmo em Canvas que extrai a paleta de cores dominante da imagem (tons de pele, cabelo e vestuário) e aplica instantaneamente aos materiais Three.js PBR.
- **🍑 90 Variações de Tudo:**
  - 90 Biotipos Corporais
  - 90 Formatos Faciais e Mandibulares
  - 90 Formatos de Bumbum Coração (com projeção, curvatura e lift independentes)
  - 90 Tipos de Quadril, Seios e Cintura
  - 90 Estilos de Cabelo e Franjas
  - 90 Tipos de Pernas com medidas em centímetros (coxa, panturrilha e tornozelo)
  - 90 Poses Sensuais Pré-configuradas
- **🔥 Física de Animação em Tempo Real:** Animação de rebolado isolado (*isolated twerk*) com oscilação harmônica senoidal nos eixos X/Y/Z e efeito de deformação elástica (*jiggle*), além do modo de respiração/vitrine (*idle breath*).
- **👗 Figurino Dinâmico:** Alternância imediata entre vestido de festa e lingerie/biquíni com ajuste anatômico.

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Descrição |
|---|---|
| **HTML5 & CSS3** | Layout responsivo em Neon Cyberpunk / Glassmorphism |
| **JavaScript (ES6+)** | Lógica procedural, manipulação de matrizes e eventos |
| **Three.js (r128)** | Renderizador WebGL, luzes direcionais/pontuais, materiais e malhas 3D |
| **Google MediaPipe Pose** | Visão computacional para detecção de pose corporal via IA |
| **Canvas API 2D** | Extração de paleta cromática por análise matricial de pixels |

---

## 🚀 Como Executar o Projeto

> **Atenção:** Devido às políticas de segurança do navegador (CORS) para carregar imagens e modelos WebAssembly do MediaPipe, a página **deve ser aberta através de um servidor HTTP local**.

### Método 1: VS Code com Live Server (Mais Rápido)
1. Abra a pasta do projeto no **Visual Studio Code**.
2. Instale a extensão **Live Server** (caso ainda não possua).
3. Clique com o botão direito no arquivo `index.html` e escolha **"Open with Live Server"**.

---

### Método 2: Via Terminal com Python

Se tiver o Python instalado:

```bash
# Execute no terminal dentro da pasta do projeto:
python -m http.server 8000
Depois abra seu navegador em: http://localhost:8000

Método 3: Via Node.js (npx)
Se tiver o Node.js:

code
Bash
npx serve .
# ou
npx http-server .
Método 4: Publicação no GitHub Pages ou Vercel
Crie um repositório no GitHub contendo o index.html e este README.md.

Acesse Settings > Pages > Selecione a branch main e clique em Save.

O link público será gerado automaticamente com suporte a HTTPS.

🎮 Controles e Interação
Girar Modelo: Clique/toque no viewport e arraste na horizontal.

Aproximar / Afastar (Zoom): Use a roda do mouse (scroll) ou o movimento de pinça no smartphone.

Menu Completo (☰): Localizado no canto superior direito para acessar todas as abas e sliders finos.

Modo Tela Cheia Imersivo: Toque rápido na tela (sem arrastar) para ocultar ou exibir todos os menus.

Modelos de Demonstração: Na aba IA Foto, clique em "Modelo 1", "Modelo 2" ou "Modelo 3" para simular a análise sem precisar enviar foto manualmente.

📂 Estrutura do Repositório
code
Text
├── index.html       # Aplicação completa (Three.js, MediaPipe, UI e Scripts)
└── README.md        # Documentação e instruções de execução
📄 Licença
Distribuído sob a licença MIT. Uso livre para estudos, modificações e projetos pessoais ou comerciais.

code
Code
3.8s
Aqui está o código do README.md completo, aprofundado, com todos os detalhes técnicos, arquitetura, mapeamento matemático de parâmetros e instruções de execução:

code
Markdown
# 🌟 IA Boneca 3D — Sistema Paramétrico & Materialização por Visão Computacional

Uma aplicação web interativa em 3D de alta fidelidade desenvolvida em **HTML5**, **JavaScript (ES6+)**, **Three.js (r128)** e **MediaPipe Pose (Google)**. O sistema conta com uma modelagem anatômica procedural feminina contendo **90 variações paramétricas exclusivas por atributo**, motor físico de oscilação harmônica para animações dinâmicas e algoritmo de **materialização e reconstituição corporal por foto via visão computacional**.

---

## 📋 Índice

- [Visão Geral](#-visão-geral)
- [Funcionalidades Principais](#-funcionalidades-principais)
- [Arquitetura e Matemática dos 90 Tipos](#-arquitetura-e-matemática-dos-90-tipos)
- [Sistema de Materialização por IA e Cores](#-sistema-de-materialização-por-ia-e-cores)
- [Motor de Animação e Física](#-motor-de-animação-e-física)
- [Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [Requisitos e Como Executar](#-requisitos-e-como-executar)
- [Guia de Controles e Atalhos](#-guia-de-controles-e-atalhos)
- [Estrutura do Projeto](#-estrutura-do-projeto)
- [Resolução de Problemas (Troubleshooting)](#-resolução-de-problemas-troubleshooting)
- [Licença e Créditos](#-licença-e-créditos)

---

## 👁️ Visão Geral

O projeto foi concebido para unir modelagem 3D procedural em tempo real e visão computacional no próprio navegador (sem necessidade de backend ou processamento em servidor). 

Inicialmente, a personagem encontra-se em **modo holográfico invisível**, aguardando uma foto de referência. Ao receber a imagem (ou ao selecionar um dos modelos demonstrativos embutidos), o pipeline analisa a estrutura física, extrai a silhueta, identifica as cores predominantes de cabelo, pele e roupa, e materializa a personagem aplicando as proporções e poses ideais.

---

## ⚡ Funcionalidades Principais

- **🔒 Estado Inicial Invisível (Holograma Sci-Fi):** Cilindro e anéis de contenção energética aramados em cor ciano. O corpo só ganha opacidade e texturas após a foto ou por liberação forçada do usuário.
- **📷 Materialização por Foto Real:** Análise de proporções anatômicas reais usando os 33 marcos da pose (*pose landmarks*) do MediaPipe Pose da Google.
- **🎨 Extração Dinâmica de Cores em Canvas:** Amostragem por blocos matriciais da imagem carregada para cálculo do valor RGB médio de:
  - Cabelo (região superior)
  - Pele (região facial/torácica)
  - Figurino/Roupa (região do tronco/quadril)
- **🍑 90 Tipos Paramétricos de Tudo:**
  - **90 Biotipos Corporais:** Variação de estatura, proporção ombro-cintura-quadril e densidade de membros.
  - **90 Formatos de Rosto:** Do perfil fino/oval ao quadrado/forte, além de controles finos para mandíbula, nariz, dentes e boca.
  - **90 Tipos de Bumbum Coração:** Geometria com lóbulos duplos modelados por deformação de vértices com fatores de elevação (*lift*), arqueamento e formato coração.
  - **90 Tipos de Quadril, Seios e Cintura:** Ajuste procedural de volume, projeção, espaçamento e curvatura.
  - **90 Cortes de Cabelo e Franja:** Cabelos lisos, ondulados, cacheados, afros, coques e franjas laterais/retas com até 6.000 fios gerados via `THREE.LineSegments`.
  - **90 Tipos de Pernas:** Personalização anatômica em centímetros (altura, coxa, panturrilha e tornozelo).
  - **90 Poses Sensuais:** De poses clássicas a ângulos dinâmicos de passarela e vitrine.
- **🔥 Física de Rebolado Isolado (*Isolated Twerk*):** Movimento pélvico harmônico nos eixos X, Y e Z com deformação elástica instantânea (*jiggle physics*) sem desestabilizar as pernas.
- **👗 Troca Rápida de Figurino:** Alternância instantânea entre vestido de festa estruturado e lingerie/biquíni coração.

---

## 📐 Arquitetura e Matemática dos 90 Tipos

Diferente de sistemas que utilizam modelos 3D pré-pesados (*blendshapes* estáticos que consomem centenas de megabytes), este projeto gera os 90 modelos de forma **paramétrica procedural** por meio de equações trigonométricas harmônicas:

```javascript
// Exemplo: Função de interpolação do quadril baseada no índice 1..90
function hipParams(i) {
  const t = (i - 1) / 89;
  const seed = i * 5.7;
  return {
    width: 0.95 + t * 0.6 + Math.sin(seed) * 0.12,
    depth: 0.85 + Math.cos(seed * 1.3) * 0.15 + t * 0.25,
    round: 0.90 + Math.abs(Math.sin(seed * 0.7)) * 0.35,
    tilt:  Math.sin(seed * 0.9) * 0.15
  };
}
Essa abordagem garante carregamento instantâneo, consumo mínimo de memória RAM e total compatibilidade com dispositivos móveis modestos.

🔬 Sistema de Materialização por IA e Cores
O pipeline de materialização executa as seguintes etapas:

code
Code
[ Upload da Foto ]
       │
       ├─► [ Canvas 2D ] ────► Amostragem de Pixel (RGB) ────► Cores PBR Three.js
       │
       └─► [ MediaPipe Pose ] ─► Landmarks Anatômicos
                                      │
                                      ▼
                        Cálculo de Proporções:
                        - Razão Ombro/Quadril (Shoulder-to-Hip Ratio)
                        - Comprimento dos Membros Inferiores
                        - Mapeamento nos Índices (1 a 90)
                                      │
                                      ▼
                        [ Ativação de Opacidade: 0.0 -> 1.0 ]
Se o MediaPipe não encontrar uma pessoa completa na imagem, o sistema ativa um algoritmo de fallback por silhueta de aspecto, garantindo que a aplicação nunca falhe ou trave.

💃 Motor de Animação e Física
O loop de renderização utiliza o THREE.Clock e funções harmônicas com frequências independentes para cada grupo de malhas:

Rebolado Isolado (animateIsolatedTwerk):

Frequência base calculada a 13.6 rad/s.

Posição da pelve varia harmonicamente em X, Y e Z.

Aplica deformação de escala assimétrica em cada lóbulo do bumbum com inverso da raiz quadrada no eixo Y para preservação de volume de massa:
escala
y
=
altura
fator de jiggle
escala 
y
​	
 = 
fator de jiggle
​	
 
altura
​	
 

Modo Vitrine / Idle (animateIdle):

Ciclo respiratório suave na caixa torácica.

Inclinação leve de cabeça e olhar.

Rotação de Câmera e Órbita:

Suporte a rotação manual em 360° com inércia.

🛠️ Tecnologias Utilizadas
Tecnologia	Versão	Função Principal
HTML5 & CSS3	Padrão W3C	Estruturação de DOM, animações CSS e interface glassmorphism
JavaScript	ES6+	Lógica da aplicação, gerenciamento de estado e controladores
Three.js	r128	Renderizador WebGL, luzes direcionais/pontuais, câmeras e malhas
MediaPipe Pose	0.5.x	Detecção de pontos-chave do corpo humano via WebAssembly e WebGL
HTML5 Canvas 2D	Nativo	Processamento e amostragem de dados matriciais de imagens
🚀 Requisitos e Como Executar

Pré-requisito Fundamental: Servidor Local (HTTP/HTTPS)
Atenção: Devido às diretivas de segurança dos navegadores modernos (política de CORS para carregar arquivos do MediaPipe via CDN e WebAssembly), o arquivo index.html não deve ser aberto dando duplo clique direto pelo explorador de arquivos (file:///). Ele precisa de um servidor local.
Opção 1: VS Code com Live Server (Mais Simples)
Instale o Visual Studio Code.

Abra a pasta do projeto no VS Code.

Vá na aba de extensões (Ctrl+Shift+X ou Cmd+Shift+X) e procure por Live Server (de Ritwick Dey).

Clique com o botão direito sobre o arquivo index.html e selecione "Open with Live Server".

O navegador abrirá automaticamente em http://127.0.0.1:5500.

Opção 2: Via Terminal com Python
Se você já possui o Python 3 instalado:

code
Bash
# Abra o terminal dentro da pasta onde está o index.html e rode:
python3 -m http.server 8000
(No Windows, você pode usar python -m http.server 8000).
Acesse: http://localhost:8000

Opção 3: Via Node.js (npx)
Sem precisar instalar dependências no projeto:

code
Bash
# Executa um servidor HTTP leve temporário:
npx serve .
ou:

code
Bash
npx http-server . -c-1
Opção 4: Publicação no GitHub Pages (Sem Servidor Local)
Crie um repositório no GitHub.

Adicione o index.html e o README.md na raiz do repositório.

Acesse Settings > Pages > Na seção Branch, selecione main e a pasta / (root).

Clique em Save. O GitHub fornecerá um link online com certificado HTTPS funcional.

🎮 Guia de Controles e Atalhos

Navegação 3D no Viewport:
Rotacionar o Modelo: Clique/toque com o botão esquerdo e arraste horizontalmente.

Aproximar / Afastar (Zoom): Role a roda do mouse (scroll) ou use o gesto de pinça na tela do celular.

Modo Limpo / Ocultar Telas: Dê um clique rápido sobre o fundo da tela (sem arrastar) para sumir com todos os botões e menus. Toque novamente para reexibi-los.

Painel Lateral (☰):
💋 Poses: Seleção entre as 90 poses e sliders de arqueamento e projeção pélvica.

💇 Rosto: 90 tipos de formato facial, boca, dentes, queixo e olhos.

💈 Cabelo: 90 cortes, 90 franjas e ajuste da densidade de fios (até 6.000).

🍑 Bumbum: 90 variações de bumbum coração, volume, elevação e botão de zoom tático.

📐 Medidas: Tipos e volumes de quadril, seios e cintura.

🩷 Corpo: 90 biotipos gerais e botão de randomização total (Aleatório Total).

📏 Pernas: Sliders numéricos em centímetros para altura, comprimento e circunferências.

🎨 Cores: Seletores de cor hexadecimal para pele, cabelo, maquiagem e roupas.

📷 IA Foto: Envio de fotos locais e 3 botões de modelos pré-fabricados para demonstração imediata.

💃 Ação: Alternância entre rebolado, vitrine sensual, pausa e figurinos.

📂 Estrutura do Projeto
code
Text
ia-boneca-3d/
├── index.html        # Arquivo unificado contendo HTML5, CSS3, Three.js, MediaPipe e UI
└── README.md         # Documentação completa do projeto
O projeto foi intencionalmente concentrado em um arquivo unificado para facilitar a distribuição portátil, eliminando etapas de compilação (build step), Webpack ou Vite.

🔍 Resolução de Problemas (Troubleshooting)

1. O corpo não aparece ou continua transparente:
Motivo: O projeto inicia intencionalmente com opacidade zero (modo holográfico).

Solução: Envie uma foto na aba 📷 IA Foto, clique em um dos modelos demonstrativos ("Modelo 1", "Modelo 2", "Modelo 3"), ou clique no botão "👁️ Forçar Visibilidade Manual".

2. Erro de CORS no console (Access to XMLHttpRequest... has been blocked by CORS policy):
Motivo: Você abriu o arquivo clicando duas vezes direto da pasta (file:///).

Solução: Inicie o projeto através de um servidor local como ensinado na seção Requisitos e Como Executar.

3. Animação travando em celulares antigos:
Solução: Abra a aba 💈 Cabelo e diminua o slider "Nº de fios" para 1000 ou 500. Isso reduz o número de vértices processados pelo WebGL a cada frame.

📄 Licença e Créditos
Este projeto é disponibilizado sob a licença MIT — sinta-se à vontade para utilizar, modificar, aprimorar e redistribuir em seus próprios projetos comerciais ou pessoais.

Three.js: mrdoob/three.js (Licença MIT)

MediaPipe Pose: Google MediaPipe (Licença Apache 2.0)
