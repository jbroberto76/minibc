---
theme: default
colorSchema: dark
title: Blockchain vs. Bancos de Dados
description: Grupo de Estudos em *Blockchain*
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

# *Blockchain* versus Bancos de Dados
Duas formas de guardar informação

---

# Objetivos de Aprendizagem

- Listar as principais funções de um banco de dados tradicional
- Listar as principais funções de uma rede *blockchain*
- Comparar as duas tecnologias
- Identificar a aplicabilidade de cada tecnologia

---
layout: section
---

# Bancos de Dados Tradicionais

---
layout: fact
---

# Por que você confia no extrato do seu banco?

---

# Banco de Dados
Conceito

> Um sistema organizado para **armazenar, gerenciar e recuperar** informações.

<v-clicks>

- Coleção estruturada de dados
- Permite consultas rápidas (SQL ou NoSQL)
- Possui administração centralizada
- Suporta operações de leitura e escrita
- Amplamente adotado em sistemas digitais

</v-clicks>

---

# Bancos de dados
Características

<div class="grid grid-cols-2 gap-4 mt-6">

<div class="p-4 rounded bg-blue-500 bg-opacity-10 border border-blue-500">

### Centralizado
Geralmente há um servidor ou entidade que controla tudo.

</div>

<div class="p-4 rounded bg-green-500 bg-opacity-10 border border-green-500">

### Permissão Controlada
Quem define quem lê/escreve é o dono do sistema.

</div>

<div class="p-4 rounded bg-yellow-500 bg-opacity-10 border border-yellow-500">

### Modificável
`UPDATE` e `DELETE` são operações comuns.

</div>

<div class="p-4 rounded bg-purple-500 bg-opacity-10 border border-purple-500">

### Alta Performance
Projetado para velocidade e eficiência.

</div>

</div>

---

# Exemplos

- <logos-mysql />
- PostgreSQL <logos-postgresql />
- <logos-oracle />
- MongoDB <logos-mongodb-icon />
- Redis <logos-redis />
- SQL Sever

---
layout: section
---

# *Blockchain*

---
layout: quote
---

# *Blockchain*

> Um registro distribuído e encadeado de transações, mantido por vários participantes e regido por regras de governança.

<v-clicks>

- Blocos de dados ligados por ***hashes***
- Cópias verificáveis disponíveis em **todos os nós** da rede
- Regras de **consenso** definem o que é válido
- Uma vez registrado, o dado **não pode** ser modificado
- Não existe administração centralizada

</v-clicks>

---

# *Blockchain* 
Características

<div class="grid grid-cols-2 gap-4 mt-6">

<div class="p-4 rounded bg-blue-500 bg-opacity-10 border border-blue-500">

### Descentralizado
Não há autoridade central controlando os dados.

</div>

<div class="p-4 rounded bg-green-500 bg-opacity-10 border border-green-500">

### Imutável
Registros são permanentes (*append-only*).

</div>

<div class="p-4 rounded bg-yellow-500 bg-opacity-10 border border-yellow-500">

### Transparente
Todos os participantes veem o mesmo histórico.

</div>

<div class="p-4 rounded bg-purple-500 bg-opacity-10 border border-purple-500">

### Consenso
As regras definem o que é válido, não um admin.

</div>

</div>

---

# *Blockchains* Típicas
Exemplos

<div class="grid grid-cols-2 gap-4 mt-8 text-center">

<div class="p-6 rounded bg-gray-500 bg-opacity-10">
  <div class="text-4xl"><logos-bitcoin /></div>
  <div class="mt-2 font-bold">Bitcoin</div>
</div>

<div class="p-6 rounded bg-gray-500 bg-opacity-10">
  <div class="text-4xl"><token-branded-ethereum /></div>
  <div class="mt-2 font-bold">Ethereum</div>
</div>

<div class="p-6 rounded bg-gray-500 bg-opacity-10">
  <div class="text-4xl"><token-branded-solana /></div>
  <div class="mt-2 font-bold">Solana</div>
</div>

<div class="p-6 rounded bg-gray-500 bg-opacity-10">
  <div class="text-4xl"><token-branded-bnb /></div>
  <div class="mt-2 font-bold">BNB Chain</div>
</div>

</div>

---
layout: section
---

# Comparativo

---

# Bancos de Dados
Varejo e Finanças

<div class="grid grid-cols-2 gap-4 mt-4">

<div class="p-4 rounded bg-blue-500 bg-opacity-10 border border-blue-500">

### Varejo e E-commerce
- Carrinho de compras (Amazon, Mercado Livre)
- Catálogo de produtos
- Histórico de pedidos
- Estoque em tempo real

</div>

<div class="p-4 rounded bg-green-500 bg-opacity-10 border border-green-500">

### Serviços Financeiros
- Core bancário (saldo, extrato)
- Sistema de cartões de crédito
- Folha de pagamento
- Score de crédito

</div>

</div>


> Por quê? Alta performance, transações ACID e uma autoridade central clara (o banco ou a loja).

---

# Bancos de Dados
Saúde e Educação

<div class="grid grid-cols-2 gap-4 mt-4">

<div class="p-4 rounded bg-red-500 bg-opacity-10 border border-red-500">

### Saúde
- Prontuário eletrônico
- Agendamento de consultas
- Estoque de medicamentos
- Faturamento hospitalar

</div>

<div class="p-4 rounded bg-purple-500 bg-opacity-10 border border-purple-500">

### 🎓 Educação
- Sistema acadêmico (notas, matrícula)
- Plataforma EAD (Moodle)
- Biblioteca digital
- Portal do aluno

</div>

</div>

---

# Bancos de Dados
Corporativo e Governos

<div class="grid grid-cols-2 gap-4 mt-4">

<div class="p-4 rounded bg-indigo-500 bg-opacity-10 border border-indigo-500">

### Corporativo / Governo
- ERP (SAP, TOTVS)
- CRM (Salesforce)
- RH e folha
- Receita Federal (CPF, IR)

</div>

<div class="p-4 rounded bg-pink-500 bg-opacity-10 border border-pink-500">

### Mídia e Entretenimento
- Netflix / Spotify
- Redes sociais (posts, comentários)
- Games online (ranking, inventário)

</div>

</div>


> Por quê? LGPD exige exclusão, dados sensíveis, correções são rotina e há um dono claro.

---

# *Blockchain*
Cadeia de Suprimentos

<div class="grid grid-cols-2 gap-3 mt-4 text-sm">

<div class="p-3 rounded bg-orange-500 bg-opacity-10 border border-orange-500">
<b>Rastreio de café</b><br/>
<span class="opacity-70">Produtor → exportador → torrefação → loja</span>
</div>

<div class="p-3 rounded bg-green-500 bg-opacity-10 border border-green-500">
<b>Walmart + IBM Food Trust</b><br/>
<span class="opacity-70">Rastreia origem de contaminação em segundos</span>
</div>

<div class="p-3 rounded bg-blue-500 bg-opacity-10 border border-blue-500">
<b>Maersk TradeLens</b><br/>
<span class="opacity-70">Documentos entre armadores, portos e alfândegas</span>
</div>

<div class="p-3 rounded bg-pink-500 bg-opacity-10 border border-pink-500">
<b>De Beers Tracr</b><br/>
<span class="opacity-70">Prova que o diamante não é "de sangue"</span>
</div>

<div class="p-3 rounded bg-red-500 bg-opacity-10 border border-red-500">
<b>Carne bovina</b> (JBS, Minerva)<br/>
<span class="opacity-70">Rastrear fazenda e evitar desmatamento</span>
</div>

</div>

> Insight famoso: o rastreio de alface no Walmart caiu de <b>7 dias</b> para <b>2,2 segundos</b>.

---

# *Blockchain*
Finanças, Arte e Governo

<div class="grid grid-cols-3 gap-3 mt-4 text-sm">

<div class="p-3 rounded bg-yellow-500 bg-opacity-10 border border-yellow-500">

### Cripto & DeFi
- Bitcoin
- Ethereum
- Stablecoins (USDC, USDT)
- DeFi (Aave, Uniswap)
- Ripple (remessas)

</div>

<div class="p-3 rounded bg-pink-500 bg-opacity-10 border border-pink-500">

### NFTs
- Arte digital (Beeple)
- Ingressos de eventos
- ENS (domínios)
- Colecionáveis

</div>

<div class="p-3 rounded bg-blue-500 bg-opacity-10 border border-blue-500">

### Governo
- Registro de imóveis (Suécia, Geórgia)
- Cartório digital (Brasil)
- e-Residency (Estônia)
- Votação eletrônica
- Diplomas (Blockcerts)

</div>

</div>

<div class="mt-5 p-3 rounded bg-purple-500 bg-opacity-10 border-l-4 border-purple-500 text-sm">
<b>Por quê?</b> Múltiplos atores, ausência de autoridade central e necessidade de auditoria pública.
</div>

---

# *Blockchain*
Outros Setores

<div class="grid grid-cols-2 gap-4 mt-4">

<div class="p-4 rounded bg-red-500 bg-opacity-10 border border-red-500">

### Saúde
- Prontuário compartilhado entre hospitais
- Rastreio de medicamentos
- Ensaios clínicos
- Consentimento do paciente

</div>

<div class="p-4 rounded bg-purple-500 bg-opacity-10 border border-purple-500">

### Educação
- Diplomas e certificados verificáveis
- Histórico escolar portável
- Credenciais profissionais

</div>

</div>

---

# *Blockchain*
Outros Setores

<div class="grid grid-cols-2 gap-4 mt-4">

<div class="p-4 rounded bg-green-500 bg-opacity-10 border border-green-500">

### Energia & ESG
- Créditos de carbono
- Comércio de energia solar (Power Ledger)
- Reciclagem (Plastic Bank)
- Auditoria de metas ESG

</div>

<div class="p-4 rounded bg-indigo-500 bg-opacity-10 border border-indigo-500">

### Outros
- Axie Infinity (game)
- Decentraland (metaverso)
- Jornalismo (Civil)
- ONGs e doações

</div>

</div>

---

# Tabela Comparativa

| Critério | BD  | *Blockchain* |
|---|---|---|
| **Arquitetura** | Centralizada | Distribuída |
| **Confiança** | Autoridade central | Protocolo/consenso |
| **Imutabilidade** | Dados alteráveis | Registros permanentes |
| **Controle de acesso** | Administrador | Chaves criptográficas |
| **Performance** | Milhões de TPS | Dezenas a milhares de TPS |
| **Custo por transação** | Baixo | Geralmente maior |
| **Auditoria** | Logs internos | Histórico completo |
| **Escalabilidade** | Alta e madura | Ainda desafiadora |
| **Governança** | Empresa/instituição | Rede/protocolo |

---
layout: two-cols-header
---

# Analogia

::left::

### Banco de Dados

Um **caderno numa sala trancada**.

Só quem tem a chave (admin) entra, escreve, apaga ou corrige.

**Rápido e eficiente**, mas você precisa confiar em quem tem a chave.

::right::

### Blockchain

Um **caderno fotocopiado para 1.000 pessoas**.

Quando alguém escreve uma página nova, todos verificam juntos.

Ninguém consegue apagar uma página antiga **sem que todos percebam**.

---
layout: section
---

# Aplicação

---

# Use Banco de Dados Tradicional quando...

> Na dúvida, comece por aqui. Bancos tradicionais resolvem 90% dos casos.

<v-clicks>

- Há uma **entidade confiável** que controla os dados
- **Performance** e **custo** são críticos
- Dados precisam ser **atualizados ou excluídos**
- Requisitos legais, como **LGPD** exigem exclusão
- Ex: sistema de RH, e-commerce, app bancário interno

</v-clicks>

---

# *Blockchain*
Aplicabilidade

> Cuidado: *Blockchain* é caro, lento e complexo. Só use quando o problema exigir.

<v-clicks>

- **Múltiplas partes** que não confiam totalmente entre si precisam compartilhar dados
- **Rastreabilidade** e **auditoria** são essenciais
- **Imutabilidade** é um requisito real
- Não existe (ou não se quer) uma autoridade central
- Ex: cadeia de suprimentos, registros de propriedade, criptomoedas

</v-clicks>


---
layout: fact
---

# *Blockchain* não substitui os bancos de dados.

---

# *Blockchain*

> É uma **ferramenta diferente** voltada para um **problema diferente**: confiança sem intermediário.

---

# Referências

- [Blockchain vs Banco de Dados: Entenda a Diferença](https://101blockchains.com/pt/blockchain-vs-banco-de-dados/)
- *Blockchain Basics* — Daniel Drescher
- *Mastering Bitcoin* — Andreas Antonopoulos [Bitcoin Book](https://github.com/bitcoinbook/bitcoinbook)
- Explorador de blocos do Ethereum: [etherscan.io](https://etherscan.io)
- Explorador de blocos do Bitcoin: [Mempool](https://mempool.space/pt/)

---
layout: fact
---

# Perguntas

---
src: /snippets/end.md 
---