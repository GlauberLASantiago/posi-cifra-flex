# Posi-Cifra-Flex

Aplicação web para gerar, editar e organizar cifras com posições alternativas de acordes no violão.

<img width="1234" height="933" alt="image" src="https://github.com/user-attachments/assets/5e514154-fa05-4f85-81fa-166151f23310" />



## Visão geral

O **Posi-Cifra-Flex** permite:

- importar arquivos MusicXML (`.xml`, `.musicxml` e `.mxl`);
- criar projetos novos do zero;
- visualizar e ouvir diagramas de acordes;
- trocar automaticamente entre posições alternativas de um mesmo acorde;
- editar cifras diretamente na grade;
- filtrar posições por inversão, cordas soltas, registro e abertura;
- exportar o arranjo como imagem pronta para impressão.

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
