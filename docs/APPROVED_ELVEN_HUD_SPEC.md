# Age of Aether — referência visual aprovada (HUD mobile)

## Fonte das artes
As quatro imagens PNG de alta qualidade foram geradas na conversa do ChatGPT e distribuídas no arquivo `AGE_Elven_Art_Pack.zip`. **Os PNGs ainda precisam ser enviados para este repositório**; este documento não é prova de que foram publicados.

## Objetivo visual obrigatório
Reproduzir o HUD de referência aprovado com fidelidade visual, não apenas aplicar tema semelhante: orbes de HP/MP, barra contínua central com slots de habilidades e XP, botões de Personagem, Inventário, Habilidades, Mapa, Configurações, Menu e Chat claramente visíveis, botões de ataque/magias e poções, todos em posições equivalentes às imagens. Folhagens, flores, raízes, espinhos, madeira ancestral, filigranas douradas e cristais esmeralda detalhados. Preservar o inventário existente aprovado.

## Integração técnica
1. Adicionar as quatro imagens originais em `references/approved/` sem recompressão destrutiva.
2. Não usar captura completa como HUD funcional: extrair ou recriar componentes em PNG/WebP com alfa verdadeiro; **o padrão quadriculado na imagem de sprites não é transparência comprovada**.
3. Criar atlas e mapa `asset -> arquivo -> retângulo UV -> posição âncora -> hitbox -> ação -> estado`.
4. Manter composição visual equivalente nas proporções Android, com escalonamento responsivo e safe areas; preservar acesso a todas as ações, inclusive joystick, ataque e 7 magias.
5. Inspecionar imagens reais em jogo; não inventar botões apenas para igualar a arte se não houver funcionalidade; implementar ou sinalizar pendência.
6. Preservar package ID, assinatura, rollback e atualizador; publicar nova versão apenas após testes.

## Artefatos esperados
`references/approved/` PNGs, `assets/ui/age-of-aether/` atlas e componentes, `docs/UI_ASSET_MAP.md`, capturas de testes em Android e checklist visual por tela.
