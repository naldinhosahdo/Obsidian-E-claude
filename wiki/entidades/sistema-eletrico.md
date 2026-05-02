---
titulo: "Sistema Elétrico Automotivo"
tipo: entidade
tags: [mecanica-automotiva, sistema-eletrico, eletronica-embarcada, diagnostico]
data_criacao: 2026-05-02
data_atualizacao: 2026-05-02
fontes: []
---

# Sistema Elétrico Automotivo

*Página stub — será expandida com a ingestão de fontes.*

## Descrição Geral

Alimenta e controla praticamente todos os subsistemas do veículo moderno, desde a partida do motor até os módulos eletrônicos de controle e redes de comunicação embarcada.

## Subsistemas Principais

### Geração e Armazenamento
- **Bateria**: armazena energia, alimenta o motor de partida e o sistema em repouso
- **Alternador**: gera corrente contínua regulada em operação (tipicamente 13,5–14,7 V)
- **Motor de partida**: aciona o motor para o primeiro ciclo de combustão

### Redes de Comunicação
- **CAN bus** (Controller Area Network): protocolo serial de alta confiabilidade entre módulos
- **LIN bus**: rede secundária de baixo custo para sensores e atuadores simples
- **FlexRay / Ethernet automotivo**: veículos modernos com ADAS e sistemas avançados

### Módulos de Controle Principais
- **ECU** (Engine Control Unit): gerencia injeção, ignição e emissões
- **BCM** (Body Control Module): iluminação, travas, vidros elétricos, alarme
- **TCM** (Transmission Control Module): gerencia câmbio automático/DCT
- **ABS/ESC Module**: controle de frenagem e estabilidade

### Sensores Comuns
- MAP (pressão absoluta no coletor), MAF (vazão de ar), TPS (posição da borboleta)
- CKP (posição do virabrequim), CMP (posição da árvore de cames)
- Sonda Lambda / O₂ (teor de O₂ no escapamento)
- ECT (temperatura do líquido de arrefecimento), IAT (temperatura do ar admitido)

## Diagnóstico

Leitura de **DTCs** (Diagnostic Trouble Codes) via porta **OBD-II** com scanner automotivo. Veja [[obd-ii]] quando disponível.

## Relação com Outros Sistemas

- [[motor]] — ECU gerencia todos os parâmetros do motor
- [[transmissao]] — TCM controla o câmbio automático
- [[sistema-de-freios]] — módulo ABS/ESC
- [[sistema-de-arrefecimento]] — sensor ECT, controle da ventoinha elétrica
- [[sistema-de-combustivel]] — ECU comanda bomba e bicos injetores

## Falhas Comuns

*(a preencher com ingestão de fontes)*

## Fontes

*(nenhuma fonte ingerida ainda)*
