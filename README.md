# 🎸 Posi-Cifra-Flex

**Posi-Cifra-Flex** é uma ferramenta web interativa projetada para músicos, arranjadores e estudantes de violão. Ela permite visualizar, criar e personalizar posições (diagramas/voicings) alternativas de acordes no braço do violão a partir de partituras e cifras importadas ou criadas do zero.

<img width="1215" height="791" alt="image" src="https://github.com/user-attachments/assets/ce199b5d-0a4e-4a8a-80f6-201949fab0a8" />


O projeto é executado inteiramente no navegador de forma independente, combinando bibliotecas de teoria musical e processamento de áudio em tempo real.

---

## 🌟 Principais Recursos

- **Visualização Dinâmica de Diagramas (SVG):**
  - Geração automática e precisa de diagramas com afinação padrão de violão.
  - Exibição opcional das notas constituintes do acorde (Dó, Ré, Mi, etc.).
  - Pestanas (barre) desenhadas com alinhamento perfeito e extrapolação visual proporcional.
  
- **Controle Avançado de Filtros de Posições:**
  - **Limitar Inversões:** Escolha limitar a busca ao *Estado Fundamental* ou permita inversões (1ª, 2ª ou 3ª inversão livre).
  - **Omitir Cordas Soltas:** Evita posições que utilizem cordas soltas para favorecer shapes móveis/transportáveis.
  - **Abertura Máxima (3 ou 4 casas):** Enfraquece/enrijece o limite físico de abertura da mão, aplicando uma tolerância dinâmica de $+1$ casa a partir da casa 8 e regras de segurança para evitar shapes desconfortáveis (proíbe casa 4 na nota mais grave, exceto em escadas contíguas).
  - **Limpar Som:** Filtra e remove notas agudas na região sub-grave (abaixo de Dó#3) para garantir clareza sonora.
  - **Juntar Bloco:** Filtra os diagramas para exibir apenas posições onde as três notas mais agudas estejam dispostas em cordas contíguas.
  - **Modo de Exceção Inteligente:** Se nenhum acorde atender aos filtros rigorosos, o app busca um shape genérico de contingência sem desconfigurar as prioridades de fundamental e inversão do usuário.

- **Prévia e Acompanhamento de Áudio em Tempo Real:**
  - Sintetizador integrado de violão de nylon e contrabaixo elétrico.
  - **Bateria de Bossa Nova:** Acompanhamento automático em compasso binário/quaternário ($2/4$, $4/4$).
  - **Bateria de Valsa:** Acompanhamento rítmico dedicado para compassos ternários e compostos ($3/4$, $6/8$, $9/8$, $12/8$) utilizando o arquivo `100-valsa-bat.mp3`.
  - Mixer inline para controle de volumes individuais (**Bat.**, **Viol.**, **Bx.**) e seletor de estilos de execução (*Bossa*, *Canção*, *Ataque*, *Com Arpejo*, *Em Colcheia*).
  - Metrônomo inteligente com contagem rítmica (8 batidas) ativo apenas quando a música inicia a partir do compasso 1.

- **Gerenciamento de Compassos e Edição de Cifras:**
  - Ferramentas de edição avançada: copiar, colar, inserir e excluir compassos em lote (seleção múltipla usando `Shift`).
  - Histórico de ações com suporte completo para **Desfazer / Refazer** (`Ctrl+Z` / `Ctrl+Y`).
  - Correção e validação musical automática (exemplos: `3` vira `#`, minúsculas são normalizadas, etc.).

- **Exportação Multiformato:**
  - **Exp. Posições (Imagem PNG):** Exporta os diagramas de acordes de todo o arranjo.
  - **Exp. Cifra (MusicXML):** Exporta a estrutura rítmica e de cifras para edição no MuseScore, Finale ou Sibelius.
  - **Exp. MP3 (Áudio):** Exporta o áudio em tempo real diretamente para arquivo MP3 de alta fidelidade com decaimento natural de 2 segundos ao final e fadeout ultra-curto (50ms) para evitar estalos de áudio.

---

## 🛠️ Tecnologias Utilizadas

O projeto utiliza bibliotecas consagradas carregadas via CDN:
- [Tonal.js](https://github.com/tonaljs/tonal) - Manipulação de teoria musical, acordes e escalas.
- [Soundfont-Player](https://github.com/danigb/soundfont-player) - Carregamento e reprodução de instrumentos MIDI sintetizados.
- [lamejs](https://github.com/zhuker/lamejs) - Codificação de áudio em formato MP3 diretamente no navegador.
- [JSZip](https://github.com/Stuk/jszip) - Empacotamento de arquivos.
- [html2canvas](https://github.com/niklasvh/html2canvas) & [html2pdf](https://github.com/eKoopmans/html2pdf.js) - Captura e renderização gráfica de páginas da web.

---

## ⌨️ Atalhos de Teclado (QWERTY)

- `Espaço`: Iniciar / Pausar a reprodução (prévia).
- `Seta Esquerda` / `Seta Direita`: Selecionar compasso anterior / seguinte.
- `Shift + Seta Esquerda/Direita`: Selecionar múltiplos compassos contíguos.
- `Ctrl + Z`: Desfazer última alteração.
- `Ctrl + Y`: Refazer última alteração desfeita.
- `Ctrl + S`: Salvar o projeto atual em arquivo de texto próprio.
- `Ctrl + O`: Carregar/abrir um projeto de texto salvo.
- `Delete` / `Backspace` (no modo de edição): Excluir cifras selecionadas.
- `Tab` / `Shift + Tab` (no modal de edição): Ir para a cifra seguinte / anterior.
- `Enter` (no modal de edição): Salvar a cifra atual.

---

## 🚀 Como Executar Localmente

Como o **Posi-Cifra-Flex** é uma aplicação estática (Serverless / Front-end puro), basta baixar o código fonte e abrir o arquivo `index.html` em seu navegador de preferência.

1. Clone o repositório:
   ```bash
   git clone https://github.com/GlauberLASantiago/posi-cifra-flex.git
   ```
2. Abra o arquivo `index.html` diretamente (clique duplo) ou utilize um servidor local de desenvolvimento (ex: *Live Server* no VS Code ou `npx serve .`).

*Nota: Para utilizar as baterias e backing tracks de bossa e valsa localmente sem restrições de CORS, recomenda-se abrir a página a partir de um servidor local.*
