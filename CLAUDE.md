# Wiki de Mecânica Automotiva — Schema e Instruções

Leia este arquivo no início de cada sessão antes de qualquer operação na wiki.

## Propósito

Wiki pessoal de mecânica automotiva mantida pelo LLM. Acumula conhecimento de PDFs técnicos, manuais, artigos e pesquisas. Alimentada tanto pelo usuário (PDFs, artigos) quanto pela IA (sugestões, sínteses, análises). O objetivo é uma base de conhecimento estruturada, interligada e sempre atualizada.

## Estrutura de Diretórios

```
obsidian-e-claude/
├── CLAUDE.md                  ← schema e instruções (este arquivo)
├── wiki/
│   ├── index.md               ← catálogo de todas as páginas
│   ├── log.md                 ← registro cronológico
│   ├── visao-geral.md         ← visão geral e mapa de domínios
│   ├── entidades/             ← sistemas, componentes, veículos
│   ├── conceitos/             ← princípios, fenômenos, terminologia
│   ├── procedimentos/         ← diagnóstico, manutenção, reparo
│   └── comparacoes/           ← análises comparativas
└── raw/
    ├── assets/                ← imagens (Obsidian baixa aqui automaticamente)
    └── [fontes brutas]        ← PDFs e arquivos de origem (imutáveis)
```

## Idioma

**Português Brasileiro** em todo o conteúdo. Termos técnicos sem tradução consagrada ficam em inglês com explicação na primeira ocorrência.

## Tipos de Página e Estrutura Padrão

### Entidades (`wiki/entidades/`)
Componentes físicos, sistemas, veículos, sensores, fabricantes.

Estrutura: Descrição → Funcionamento → Tipos/Variantes → Relação com Outros Sistemas → Falhas Comuns → Fontes

### Conceitos (`wiki/conceitos/`)
Princípios, fenômenos, teorias, terminologia técnica.

Estrutura: Definição → Contexto → Fórmulas (se aplicável) → Impacto Prático → Fontes

### Procedimentos (`wiki/procedimentos/`)
Diagnósticos, manutenções e reparos passo a passo.

Estrutura: Objetivo → Ferramentas → Passo a Passo → Pontos de Atenção → Fontes

### Comparações (`wiki/comparacoes/`)
Análises comparativas de sistemas, tecnologias ou abordagens.

Estrutura: Critérios → Tabela Comparativa → Análise → Conclusão → Fontes

## Frontmatter YAML

Toda página wiki deve começar com:

```yaml
---
titulo: "Nome da Página"
tipo: entidade | conceito | procedimento | comparacao
tags: [mecanica-automotiva, tag-especifica]
data_criacao: YYYY-MM-DD
data_atualizacao: YYYY-MM-DD
fontes: []
---
```

## Links e Nomenclatura

- Links internos: `[[nome-da-pagina]]` ou `[[nome-da-pagina|texto exibido]]`
- Sempre crie links para entidades e conceitos mencionados
- Nomes de arquivo: kebab-case sem acentos (`transmissao.md`, não `transmissão.md`)

## index.md

Catálogo de todas as páginas. Atualizar a cada ingestão ou criação de página.

Formato:
```
- [[nome-da-pagina]] — descrição de uma linha
```

## log.md

Registro append-only. Formato de cada entrada:
```
## [YYYY-MM-DD] operacao | Descrição
```

Operações: `ingest`, `query`, `ai-suggest`, `lint`, `create`

Buscar últimas 5 entradas: `grep "^## \[" wiki/log.md | tail -5`

## Fluxos de Trabalho

### Ingestão de PDF (`ingest`)
1. Ler o arquivo em `raw/` (ou conteúdo enviado pelo usuário)
2. Extrair pontos-chave; discutir com o usuário se for fonte individual
3. Criar ou atualizar páginas relevantes na wiki
4. Sinalizar contradições com conteúdo já existente
5. Atualizar `wiki/index.md`
6. Adicionar entrada em `wiki/log.md`

Para ingestão em lote: processar sequencialmente e reportar resumo ao final.

### Resposta a Perguntas (`query`)
1. Ler `wiki/index.md` para identificar páginas relevantes
2. Ler as páginas encontradas
3. Sintetizar resposta com citações
4. Oferecer arquivar resposta rica como nova página wiki
5. Adicionar entrada em `wiki/log.md`

### Sugestão de Conteúdo pela IA (`ai-suggest`)
A IA pode identificar proativamente:
- Lacunas (conceito mencionado sem página própria)
- Temas importantes ainda não cobertos
- Fontes úteis a buscar (livros, normas, manuais)
- Conexões entre páginas não linkadas

Sempre apresentar sugestões ao usuário antes de criar páginas.

### Limpeza da Wiki (`lint`)
Verificar: páginas órfãs, contradições, claims desatualizados, links quebrados, frontmatter incompleto, conceitos sem página própria.

## Domínios Principais

| Sistema | Tópicos Cobertos |
|---|---|
| Motor | Ciclos termodinâmicos, componentes internos, lubrificação, cabeçote |
| Transmissão | Manual, automático, CVT, DCT, embreagem |
| Freios | Disco, tambor, ABS, EBD, freio regenerativo |
| Sistema Elétrico | Bateria, alternador, partida, CAN bus, sensores, módulos |
| Arrefecimento | Radiador, bomba d'água, termostato, fluido refrigerante |
| Combustível | Injeção direta/indireta, bomba, bico injetor, mapeamento |
| Suspensão | Tipos (MacPherson, multilink), geometria, amortecedores, molas |
| Diagnóstico | OBD-II, códigos de falha (DTC), osciloscópio automotivo, scanner |
