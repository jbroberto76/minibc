---
theme: default
colorSchema: dark
title: Estrutura da Blockchain
description: Grupo de Estudos em Blockchain
layout: image
image: /cover.svg
highlighter: shiki
lineNumbers: false
drawings:
  persist: false
transition: slide-left
mdc: true
author: José Roberto Bezerra
---

# {{ $slidev.configs.title }}
{{ $slidev.configs.description }}


---

# Objetivos de Aprendizagem

- Conhecer os princípios de funcionamento da *Blockchain*
- Identificar os três pilares que garantem imutabilidade e segurança

---
layout: fact
---

# Se eu alterar um dado em um arquivo no meu computador, por que ninguém fica sabendo?

---
layout: fact
---

# E se esse arquivo estivesse em 10.000 computadores ao mesmo tempo?

---
layout: section
---

# Blocos

---

# Blocos

> É uma estrutura de dados que agrupa informações dentro da *Blockchain*

---

# Blocos
Características

<v-clicks>

- É a **unidade básica** de armazenamento
- Contém **transações** (ou qualquer dado registrado)
- Possui uma **referência ao bloco anterior**
- Carrega um **hash próprio** (sua "impressão digital")
- É **validado** pela rede antes de ser aceito

</v-clicks>

---

# Partes de um Bloco

1. Cabeçalho (*Header*)
2. Corpo (*Body*)

---

# Cabeçalho
*Header*

> Contém metadados para identificação do bloco e conexão entre os blocos.

> O *header* garante a segurança da cadeia

---

# Corpo
*Body*

> A carga útil, geralmente corresponde a lista de transações.

> Contém as informações práticas registradas no bloco

---

# Campos do Cabeçalho
Campos típicos

- **Número do bloco**
- **Timestamp** — data e hora de criação
- **Hash do bloco anterior** (*previous hash*)
- **Merkle Root** — *hash*-resumo de todas as transações
- **Nonce** — número usado na mineração (*proof of work*)
- **Difficulty / Target** — dificuldade atual da rede
- **Versão** — versão do protocolo

---
layout: fact
---

# Cada *blockchain* possui variações dos campos que utiliza. 

---

# Exemplo
Cabeçaho do Bitcoin

> O cabeçalho do Bitcoin é fixo em 80 bytes. É isso que os mineradores hasheiam no PoW.

| Campo | Tamanho | Função |
|---|---|---|
| **nVersion** | 4 bytes | Versão do protocolo (sinaliza soft forks) |
| **hashPrevBlock** | 32 bytes | Hash SHA-256 do bloco anterior |
| **hashMerkleRoot** | 32 bytes | Raiz da árvore de Merkle das transações |
| **nTime** | 4 bytes | Timestamp Unix de criação |
| **nBits** | 4 bytes | Alvo de dificuldade (compacto) |
| **nNonce** | 4 bytes | Contador iterado pelo minerador |

---

# Exemplo 
Bloco Bitcoin #0 (Genesis)

<div class="p-5 rounded bg-gray-500 bg-opacity-10 border border-gray-500 font-mono text-xs leading-relaxed">

<div class="text-purple-400 font-bold mb-2">┌── CABEÇALHO (80 bytes) ─────────────────────────┐</div>
<div class="pl-4">
  <b>nVersion</b> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: <span class="text-white">01000000</span> &nbsp;<span class="opacity-60">(v1)</span><br/>
  <b>hashPrevBlock</b> &nbsp;: <span class="text-white">0000000000000000000000000000000000000000000000000000000000000000</span><br/>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="opacity-60">(zero — é o primeiro bloco)</span><br/>
  <b>hashMerkleRoot</b> &nbsp;: <span class="text-white">3ba3edfd7a7b12b27ac72c3e67768f61</span><br/>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="text-white">7fc81bc3888a51323a9fb8aa4b1e5e4a</span><br/>
  <b>nTime</b> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: <span class="text-white">29ab5f49</span> &nbsp;<span class="opacity-60">(2009-01-03 18:15:05 UTC)</span><br/>
  <b>nBits</b> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: <span class="text-white">ffff001d</span> &nbsp;<span class="opacity-60">(dificuldade 1)</span><br/>
  <b>nNonce</b> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: <span class="text-white">1dac2b7c</span> &nbsp;<span class="opacity-60">(2.083.236.829)</span>
</div>
<div class="text-purple-400 font-bold mt-2">└────────────────────────────────────────────────┘</div>

</div>

---

# Exemplo
Ethereum

| Campo | Tamanho | Função |
|---|---|---|
| **parentHash** | 32 bytes | Hash Keccak-256 do bloco pai |
| **ommersHash** | 32 bytes |  Constante vazia pós-Merge |
| **beneficiary** | 20 bytes | Endereço que recebe as fees |
| **stateRoot** | 32 bytes |  Raiz da árvore de **estado global** |
| **transactionsRoot** | 32 bytes |  Raiz das transações |
| **receiptsRoot** | 32 bytes |  Raiz dos recibos (logs) |
| **logsBloom** | 256 bytes | Filtro Bloom para busca rápida |
| **difficulty** | — |  **0** (PoS substituiu PoW) |
| **number** | variável | Altura do bloco |
| **gasLimit** | variável | Limite de gas do bloco |
| **gasUsed** | variável | Gas efetivamente consumido |
| **timestamp** | ≤32 bytes | Timestamp de criação |
| **extraData** | ≤32 bytes | Dados livres (ex: mensagem do validador) |
| **prevRandao** | 32 bytes | 🎲 Randomicidade da Beacon Chain |
| **nonce** | 8 bytes |  **0** (PoS substituiu PoW) |
| **baseFeePerGas** | variável | 🔥 Fee base (EIP-1559, queimada) |

---

# Corpo do Bloco
Transações
- Lista de operações registradas
- Cada transação tem remetente, destinatário e valor (ou dados)
- Cada transação é assinada criptograficamente

---

# Árvore de Merkle
*Merkle root*
- Organização em **árvore binária de hashes**
- Permite verificar uma transação sem baixar o bloco inteiro
- Gera um único **Merkle Root**

---

# Anatomia Visual de um Bloco

<div class="p-6 rounded bg-gray-500 bg-opacity-10 border border-gray-500 font-mono text-sm leading-relaxed">

<div class="text-purple-400 font-bold">┌── CABEÇALHO ───────────────────────────────┐</div>
<div class="text-purple-300 pl-4">
  │ Número do bloco: &nbsp;&nbsp;&nbsp;<span class="text-white">#840.000</span><br/>
  │ Timestamp: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="text-white">2025-01-15 14:32:07</span><br/>
  │ Hash anterior: &nbsp;&nbsp;&nbsp;&nbsp;<span class="text-white">0000...a3f9</span><br/>
  │ Merkle Root: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="text-white">4b7c...e1d2</span><br/>
  │ Nonce: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="text-white">1.847.203.991</span><br/>
  │ Dificuldade: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="text-white">23.5 T</span>
</div>
<div class="text-purple-400 font-bold">├── CORPO ───────────────────────────────────┤</div>
<div class="text-green-300 pl-4">
  │ Transação 1: Alice → Bob — 0.5 BTC<br/>
  │ Transação 2: Carlos → Dani — 1.2 BTC<br/>
  │ Transação 3: Eva → Frank — 0.03 BTC<br/>
  │ ...
</div>
<div class="text-purple-400 font-bold">└────────────────────────────────────────────┘</div>

</div>

---
layout: section
---

# Encadeamento dos Blocos

---

# Encadeamento
*Chaining*

> Cada bloco aponta para o bloco anterior através do *hash*

---

<div class="mt-8 text-center font-mono text-sm">

<div class="inline-block p-3 rounded bg-blue-500 bg-opacity-20 border border-blue-500">
Bloco 1<br/>
<span class="text-xs opacity-70">hash: <b>AAA</b></span>
</div>

<div class="inline-block px-2 text-2xl">→</div>

<div class="inline-block p-3 rounded bg-blue-500 bg-opacity-20 border border-blue-500">
Bloco 2<br/>
<span class="text-xs opacity-70">prev: <b>AAA</b><br/>hash: <b>BBB</b></span>
</div>

<div class="inline-block px-2 text-2xl">→</div>

<div class="inline-block p-3 rounded bg-blue-500 bg-opacity-20 border border-blue-500">
Bloco 3<br/>
<span class="text-xs opacity-70">prev: <b>BBB</b><br/>hash: <b>CCC</b></span>
</div>

</div>

> O *hash* do bloco anterior é a "cola" que une tudo. É isso que forma a cadeia.


---

# *Hash*

> Um *hash* é uma função que transforma qualquer entrada em uma saída de tamanho fixo.

---

# *Hash*
Propriedades

- **Determinístico**; mesma entrada, mesma saída
- **Tamanho fixo**; sempre 256 bits (SHA-256)
- **Rápido**;
- **Irreversível**; não é possível desfazer a operação
- **Efeito avalanche**; 1 caractere muda tudo

---

# Efeito Dominó
- Alterar o Bloco 1 → seu hash muda →<br/>
- Bloco 2 aponta para um hash que não existe mais →<br/>
- Bloco 3 idem → **toda a cadeia se rompe**.

> Para adulterar um bloco, seria preciso refazer todos os blocos seguintes

---
layout: section
---

# Imutabilidade

# Visão Geral

<div class="grid grid-cols-3 gap-4 mt-12 text-center">

<div class="p-6 rounded bg-blue-500 bg-opacity-10 border-2 border-blue-500">
  <div class="text-5xl">🔐</div>
  <div class="mt-3 font-bold text-lg">Criptografia</div>
  <div class="mt-2 text-sm opacity-70">Hashes encadeados</div>
</div>

<div class="p-6 rounded bg-green-500 bg-opacity-10 border-2 border-green-500">
  <div class="text-5xl">🌐</div>
  <div class="mt-3 font-bold text-lg">Descentralização</div>
  <div class="mt-2 text-sm opacity-70">Cópias em milhares de nós</div>
</div>

<div class="p-6 rounded bg-purple-500 bg-opacity-10 border-2 border-purple-500">
  <div class="text-5xl">🤝</div>
  <div class="mt-3 font-bold text-lg">Consenso</div>
  <div class="mt-2 text-sm opacity-70">Regras aceitas por todos</div>
</div>

</div>

<div class="mt-10 text-center text-lg opacity-80">
Os três juntos tornam a blockchain <b>praticamente imutável</b>.
</div>

---

# 🔐 Pilar 1 — Criptografia

<div class="grid grid-cols-2 gap-4 mt-4">

<div class="p-4 rounded bg-blue-500 bg-opacity-10 border border-blue-500">

### Como funciona
- Cada bloco tem um **hash único**
- Cada bloco guarda o **hash do anterior**
- Alterar qualquer dado → hash muda
- O encadeamento de hashes forma uma "corrente inviolável"

</div>

<div class="p-4 rounded bg-blue-500 bg-opacity-10 border border-blue-500">

### Garantias
- **Integridade** — o dado não foi alterado
- **Autenticidade** — assinaturas digitais
- **Não-repúdio** — quem assinou, assinou

</div>

</div>

<div class="mt-6 p-3 rounded bg-blue-500 bg-opacity-10 border-l-4 border-blue-500 text-sm">
Em resumo, a criptografia torna <b>detectável</b> qualquer tentativa de adulteração.
</div>

---

# Pilar 2 — Descentralização

<div class="grid grid-cols-2 gap-4 mt-4">

<div class="p-4 rounded bg-green-500 bg-opacity-10 border border-green-500">

### Como funciona
- A *Blockchain* é **copiada em milhares de nós**
- Cada nó valida e guarda a cópia completa
- Não existe um "servidor central"
- Se um nó cai, os outros continuam

</div>

<div class="p-4 rounded bg-green-500 bg-opacity-10 border border-green-500">

### Garantias
- **Resistência a censura** — ninguém desliga tudo
- **Alta disponibilidade** — sempre há cópias
- **Confiança distribuída** — não depende de um ator

</div>

</div>

<div class="mt-6 p-3 rounded bg-green-500 bg-opacity-10 border-l-4 border-green-500 text-sm">
<b>Resumo:</b> para alterar o passado, seria preciso convencer <b>a maioria da rede</b> — não apenas um servidor.
</div>

---

# Pilar 3 — Consenso

<div class="grid grid-cols-2 gap-4 mt-4">

<div class="p-4 rounded bg-purple-500 bg-opacity-10 border border-purple-500">

### Como funciona
- Regras definem **o que é um bloco válido**
- Os nós "votam" implicitamente ao aceitar/rejeitar blocos
- Só a **cadeia mais longa** (ou mais votada) vence
- Blocos inválidos são ignorados

</div>

<div class="p-4 rounded bg-purple-500 bg-opacity-10 border border-purple-500">

### Algoritmos comuns
- **Proof of Work (PoW)** — Bitcoin
- **Proof of Stake (PoS)** — Ethereum 2.0
- **PBFT / Raft** — redes permissionadas
- **Delegated PoS** — EOS, Tron

</div>

</div>

<div class="mt-6 p-3 rounded bg-purple-500 bg-opacity-10 border-l-4 border-purple-500 text-sm">
<b>Resumo:</b> o consenso garante que <b>todos os nós cheguem ao mesmo estado</b>, mesmo sem confiar uns nos outros.
</div>

---

# Os Três Pilares em Ação

Cenário: **um atacante tenta alterar uma transação antiga**.

<v-clicks>

1. 🔐 **Criptografia** → o hash do bloco muda imediatamente
2. 🌐 **Descentralização** → os outros milhares de nós ainda têm a versão original
3. 🤝 **Consenso** → a rede rejeita a versão adulterada e mantém a original

</v-clicks>

<div class="mt-8 p-4 rounded bg-red-500 bg-opacity-10 border-l-4 border-red-500">
Resultado: o atacante precisaria <b>refazer todos os blocos seguintes</b> e <b>convencer 51% da rede</b>. Custo astronômico.
</div>

---

# O Custo de um Ataque (51%)

Para reescrever a história, seria necessário:

<v-clicks>

- **Energia** — no PoW, refazer todo o trabalho computacional
- **Hardware** — mais poder de mineração que o resto da rede somada
- **Tempo** — refazer blocos mais rápido que a rede cria novos
- **Dinheiro** — custo inviável na maioria das redes grandes
- **Incentivo** — ainda assim, a rede poderia rejeitar a cadeia

</v-clicks>

<div class="mt-6 text-center text-lg">
<b>Não é impossível — é economicamente inviável.</b>
</div>

---

# Nuances Importantes

<v-clicks>

- **Imutabilidade não é absoluta** — é probabilística
- **Blocos recentes** são mais fáceis de reverter (poucas confirmações)
- **Redes permissionadas** (Hyperledger) têm imutabilidade mais fraca
- **Forks** podem reescrever história se a maioria concordar
- **LGPD vs. imutabilidade** — tensão real e não resolvida

</v-clicks>

<div class="mt-6 p-3 rounded bg-yellow-500 bg-opacity-10 border-l-4 border-yellow-500 text-sm">
Blockchain é <b>tamper-evident</b> (evidencia adulteração) mais do que <b>tamper-proof</b> (à prova de adulteração).
</div>

---
layout: section
---

# Para ir além

<div class="text-left inline-block mt-8">

- 📖 **"Mastering Bitcoin"** — Andreas Antonopoulos (cap. 7 e 9)
- 📖 **"Blockchain Basics"** — Daniel Drescher
- 🎥 **Anders Brownworth** — *Blockchain Demo* (visual interativo)
- 🎥 **3Blue1Brown** — vídeo sobre hashes e SHA-256
- 🧪 **Etherscan** e **Blockchain.com** — exploradores reais

</div>

---
layout: fact
---

# Perguntas?

---

<div class="grid grid-cols-3 gap-4 mt-12 text-center">

<div class="p-6 rounded bg-blue-500 bg-opacity-10 border-2 border-blue-500">
  <div class="text-5xl">🔐</div>
  <div class="mt-3 font-bold text-lg">Criptografia</div>
  <div class="mt-2 text-sm opacity-70">Hashes encadeados</div>
</div>

<div class="p-6 rounded bg-green-500 bg-opacity-10 border-2 border-green-500">
  <div class="text-5xl">🌐</div>
  <div class="mt-3 font-bold text-lg">Descentralização</div>
  <div class="mt-2 text-sm opacity-70">Cópias em milhares de nós</div>
</div>

<div class="p-6 rounded bg-purple-500 bg-opacity-10 border-2 border-purple-500">
  <div class="text-5xl">🤝</div>
  <div class="mt-3 font-bold text-lg">Consenso</div>
  <div class="mt-2 text-sm opacity-70">Regras aceitas por todos</div>
</div>

</div>

---

# Pilar 1
Criptografia

<div class="grid grid-cols-2 gap-4 mt-4">

<div class="p-4 rounded bg-blue-500 bg-opacity-10 border border-blue-500">

# Como funciona
- Cada bloco tem um **hash único**
- Cada bloco guarda o **hash do anterior**
- Alterar qualquer dado → hash muda
- O encadeamento de hashes forma uma "corrente inviolável"

</div>

<div class="p-4 rounded bg-blue-500 bg-opacity-10 border border-blue-500">

# Garantias
- **Integridade** — o dado não foi alterado
- **Autenticidade** — assinaturas digitais
- **Não-repúdio** — quem assinou, assinou

</div>

</div>

<div class="mt-6 p-3 rounded bg-blue-500 bg-opacity-10 border-l-4 border-blue-500 text-sm">
<b>Resumo:</b> a criptografia torna <b>detectável</b> qualquer tentativa de adulteração.
</div>

---

# Pilar 2
Descentralização

<div class="grid grid-cols-2 gap-4 mt-4">

<div class="p-4 rounded bg-green-500 bg-opacity-10 border border-green-500">

# Como funciona
- A blockchain é **copiada em milhares de nós**
- Cada nó valida e guarda a cópia completa
- Não existe um "servidor central"
- Se um nó cai, os outros continuam

</div>

<div class="p-4 rounded bg-green-500 bg-opacity-10 border border-green-500">

Garantias
- 🛡️ **Resistência a censura** — ninguém desliga tudo
- 🔁 **Alta disponibilidade** — sempre há cópias
- 🗳️ **Confiança distribuída** — não depende de um ator

</div>

</div>

<div class="mt-6 p-3 rounded bg-green-500 bg-opacity-10 border-l-4 border-green-500 text-sm">
💡 <b>Resumo:</b> para alterar o passado, seria preciso convencer <b>a maioria da rede</b> — não apenas um servidor.
</div>

---

# Pilar 3
Consenso

<div class="grid grid-cols-2 gap-4 mt-4">

<div class="p-4 rounded bg-purple-500 bg-opacity-10 border border-purple-500">

### Como funciona
- Regras definem **o que é um bloco válido**
- Nós "votam" implicitamente ao aceitar/rejeitar blocos
- Só a **cadeia mais longa** (ou mais votada) vence
- Blocos inválidos são ignorados

</div>

<div class="p-4 rounded bg-purple-500 bg-opacity-10 border border-purple-500">

### Algoritmos comuns
- ⛏️ **Proof of Work (PoW)** — Bitcoin
- 💰 **Proof of Stake (PoS)** — Ethereum 2.0
- 🏛️ **PBFT / Raft** — redes permissionadas
- 🗳️ **Delegated PoS** — EOS, Tron

</div>

</div>

<div class="mt-6 p-3 rounded bg-purple-500 bg-opacity-10 border-l-4 border-purple-500 text-sm">
💡 <b>Resumo:</b> o consenso garante que <b>todos os nós cheguem ao mesmo estado</b>, mesmo sem confiar uns nos outros.
</div>

---

# Os Três Pilares em Ação

> Cenário: **um atacante tenta alterar uma transação antiga**.

---

# Os Três Pilares em Ação

<v-clicks>

1. 🔐 **Criptografia** → o hash do bloco muda imediatamente
2. 🌐 **Descentralização** → os outros milhares de nós ainda têm a versão original
3. 🤝 **Consenso** → a rede rejeita a versão adulterada e mantém a original

</v-clicks>

<div class="mt-8 p-4 rounded bg-red-500 bg-opacity-10 border-l-4 border-red-500">
❌ Resultado: o atacante precisaria <b>refazer todos os blocos seguintes</b> e <b>convencer 51% da rede</b>. Custo astronômico.
</div>

---

# O Custo de um Ataque (51%)

> Para reescrever a história, seria necessário:

<v-clicks>

- **Energia** — no PoW, refazer todo o trabalho computacional
- **Hardware** — mais poder de mineração que o resto da rede somada
- **Tempo** — refazer blocos mais rápido que a rede cria novos
- **Dinheiro** — custo inviável na maioria das redes grandes
- **Incentivo** — ainda assim, a rede poderia rejeitar a cadeia

</v-clicks>

<div class="mt-6 text-center text-lg">
<b>Não é impossível — é economicamente inviável.</b>
</div>

---

# Conclusões

<v-clicks>

- **Imutabilidade não é absoluta** — é probabilística
- **Blocos recentes** são mais fáceis de reverter (poucas confirmações)
- **Redes permissionadas** (Hyperledger) têm imutabilidade mais fraca
- **Forks** podem reescrever história se a maioria concordar
- **LGPD vs. imutabilidade** — tensão real e não resolvida

</v-clicks>

<div class="mt-6 p-3 rounded bg-yellow-500 bg-opacity-10 border-l-4 border-yellow-500 text-sm">
🧠 Blockchain é <b>tamper-evident</b> (evidencia adulteração) mais do que <b>tamper-proof</b> (à prova de adulteração).
</div>

---



---

# Referências

- [Merkle Trees e Merkle Roots](https://www.binance.com/pt-BR/academy/articles/merkle-trees-and-merkle-roots-explained)


---
src: /snippets/end.md
---