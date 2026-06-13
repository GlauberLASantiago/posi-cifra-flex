# Posi-Cifra-Flex

Aplicação web para gerar, editar e organizar cifras com posições alternativas de acordes no violão.

<img width="1234" height="933" alt="image" src="https://github.com/user-attachments/assets/5e514154-fa05-4f85-81fa-166151f23310" />



## Visão geral


📖 Como usar o app

📖 Mini Tutorial

Inicie um projeto: Carregue um arquivo no formato .xml ou .musicxml (exportado do MuseScore, Finale, Sibelius, etc.) usando o botão de upload, ou crie um projeto do zero clicando em "Novo" para definir o título, fórmula de compasso e quantidade inicial de compassos.
Veja e ouça os diagramas e as notas: O app desenha automaticamente os diagramas de acordes (posições no braço do violão) no grid. Clique no diagrama para ouvir o acorde dedilhado em áudio sintetizado de alta fidelidade. A caixa de seleção "Visualizar Notas" (ativada por padrão) exibe as notas componentes do acorde (como Dó, Ré, Mi...) abaixo de cada diagrama.

Selecione posições alternativas: Clique no botão "Mudar" sob qualquer acorde para abrir a galeria com todas as posições correspondentes encontradas e clique na desejada.

Edite cifras e desfaça ações: Ative a caixa "Editar Cifras". Clique na cifra ou em "Editar" para digitar o acorde. O app corrige automaticamente o texto (minúsculas viram maiúsculas, o caractere 3 vira sustenido #, e o b vira bemol b), além de normalizar e validar musicalmente a cifra. Pressione Enter para salvar e avançar para o próximo compasso. Você pode desfazer ou refazer edições utilizando os botões "↶ Desfazer" e "↷ Refazer" (ou atalhos Ctrl+Z e Ctrl+Y).

Ouça uma prévia em andamento: Clique no botão "Prévia: Tocar" para escutar o arranjo acompanhado por uma bateria de bossa nova. O controle de BPM ao lado permite ajustar o andamento entre 60 e 200 (o padrão é 130 BPM). O seletor de estilo permite alternar a prévia entre Ataque (notas simultâneas), Com Arpejo (notas dedilhadas rapidamente) ou Em Colcheia (notas arpejadas sustentadas no tempo de colcheia). O acorde atual é destacado visualmente com um fundo verde no grid enquanto soa.

Gerencie a partitura: Adicione novas cifras com + Cifra, delete-as com o botão vermelho ×, ou aumente/diminua a quantidade total de compassos pelos botões + e - abaixo da partitura.

Filtre posições: Configure o limite de inversão de baixos, permissão de cordas soltas, registro de altura (grave, médio ou agudo) e a abertura de casas para adequar os diagramas.

Exporte o arranjo: Clique em "Exportar Imagem" para baixar os diagramas diagramados em páginas no formato retrato (A4), prontas para visualização ou impressão.

## Estrutura do repositório

- `index.html`: aplicação principal (HTML, CSS e JavaScript em um único arquivo);
- `posi-cifra-flex-demo.musicxml`: exemplo de partitura para teste;
- `violoes.png`: imagem de fundo da interface.

## Como executar

Como é uma aplicação estática, basta abrir o arquivo `index.html` em um navegador moderno.

### Opção 1 — abertura direta

1. Acesse a pasta raiz do projeto.
2. Abra o arquivo `index.html` no navegador.

### Opção 2 — servidor local (recomendado)

No diretório do projeto:

```bash
python3 -m http.server 8000
```

Depois, abra `http://localhost:8000`.

## Fluxo de uso rápido

1. Clique em **Novo** para iniciar um projeto ou carregue um arquivo MusicXML.
2. Ajuste os filtros de voicing conforme necessário.
3. Ative **Editar Cifras** para alterar acordes diretamente.
4. Use **Mudar** para selecionar posições alternativas.
5. Clique em **Exportar Imagem** para gerar páginas do arranjo.

## Dependências em CDN

A página carrega bibliotecas externas via CDN:

- Tonal.js
- Soundfont Player
- html2pdf.js
- html2canvas
- JSZip

## Autor

Desenvolvido por **Glauber Santiago (DAC/UFSCar)**.
