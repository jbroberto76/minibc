---
theme: default
colorSchema: dark
title: *Blockchain* vs. Bancos de Dados
description: Grupo de Estudos em *Blockchain*
info: |
  ## Aula introdutória
  Diferenças entre blockchain e bancos de dados convencionais.
class: text-center
highlighter: shiki
lineNumbers: false
drawings:
  persist: false
transition: slide-left
mdc: true
---

# *Blockchain* versus Bancos de Dados

Duas formas de guardar informação — e por que elas não são a mesma coisa

<div class="pt-12">
  <span class="px-2 py-1 rounded bg-blue-500 text-white text-sm">
    Aula introdutória
  </span>
</div>

---
layout: fact
---

# Por que você confia no extrato do seu banco?

---

# Objetivos de Aprendizagem

<v-clicks>

- Listar as principais funções de um banco de dados tradicional
- Listar as principais funções de uma rede *blockchain*
- Comparar as duas tecnologias
- Identificar a aplicabilidade de cada tecnologia

</v-clicks>

---
layout: section
---

# Bancos de Dados Tradicionais

---

# Banco de Dados
Conceito

> Um sistema organizado para **armazenar, gerenciar e recuperar** informações.

<v-clicks>

- Coleção estruturada de dados
- Permite consultas rápidas (SQL, NoSQL)
- Possui administração centralizada
- Suporta operações de leitura e escrita
- Amplamente adotado em sistemas digitais

</v-clicks>

---

# Bancos de dados
Características

<div class="grid grid-cols-2 gap-4 mt-6">

<div class="p-4 rounded bg-blue-500 bg-opacity-10 border border-blue-500">

### 🏛️ Centralizado
Geralmente há um servidor ou entidade que controla tudo.

</div>

<div class="p-4 rounded bg-green-500 bg-opacity-10 border border-green-500">

### 🔑 Permissão Controlada
Quem define quem lê/escreve é o dono do sistema.

</div>

<div class="p-4 rounded bg-yellow-500 bg-opacity-10 border border-yellow-500">

### ✏️ Alterável
`UPDATE` e `DELETE` são operações comuns.

</div>

<div class="p-4 rounded bg-purple-500 bg-opacity-10 border border-purple-500">

### ⚡ Alta Performance
Projetado para velocidade e eficiência.

</div>

</div>

---

# Exemplos

- MySQL <logos-mysql />
- PostgreSQL <logos-postgresql />
- Oracle <logos-oracle />
- Oracle <logos-mongodb />
- Redis <logos-redis />
- SQL Sever <logos-sqlserver />

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

### 🌐 Descentralizado
Não há autoridade central controlando os dados.

</div>

<div class="p-4 rounded bg-green-500 bg-opacity-10 border border-green-500">

### 🔒 Imutável
Registros são permanentes (*append-only*).

</div>

<div class="p-4 rounded bg-yellow-500 bg-opacity-10 border border-yellow-500">

### 👁️ Transparente
Todos os participantes veem o mesmo histórico.

</div>

<div class="p-4 rounded bg-purple-500 bg-opacity-10 border border-purple-500">

### 🤝 Consenso
As regras definem o que é válido, não um admin.

</div>

</div>

---

# Exemplos Conhecidos

<div class="grid grid-cols-3 gap-4 mt-8 text-center">

<div class="p-6 rounded bg-gray-500 bg-opacity-10">
  <div class="text-4xl">₿</div>
  <div class="mt-2 font-bold">Bitcoin</div>
</div>

<div class="p-6 rounded bg-gray-500 bg-opacity-10">
  <div class="text-4xl">⟠</div>
  <div class="mt-2 font-bold">Ethereum</div>
</div>

<div class="p-6 rounded bg-gray-500 bg-opacity-10">
  <div class="text-4xl">🏢</div>
  <div class="mt-2 font-bold">Hyperledger Fabric</div>
</div>

<div class="p-6 rounded bg-gray-500 bg-opacity-10">
  <div class="text-4xl">◎</div>
  <div class="mt-2 font-bold">Solana</div>
</div>

<div class="p-6 rounded bg-gray-500 bg-opacity-10">
  <div class="text-4xl">🔷</div>
  <div class="mt-2 font-bold">Polygon</div>
</div>

<div class="p-6 rounded bg-gray-500 bg-opacity-10">
  <div class="text-4xl">🌾</div>
  <div class="mt-2 font-bold">AgriLedger</div>
</div>

</div>

---
layout: section
---

# Comparativo

---
layout: default
---

# Bancos de Dados
Varejo e Finanças

<div class="grid grid-cols-2 gap-4 mt-4">

<div class="p-4 rounded bg-blue-500 bg-opacity-10 border border-blue-500">

### 🛒 Varejo e E-commerce
- Carrinho de compras (Amazon, Mercado Livre)
- Catálogo de produtos
- Histórico de pedidos
- Estoque em tempo real

</div>

<div class="p-4 rounded bg-green-500 bg-opacity-10 border border-green-500">

### 🏦 Serviços Financeiros
- Core bancário (saldo, extrato)
- Sistema de cartões de crédito
- Folha de pagamento
- Score de crédito

</div>

</div>

<div class="mt-6 p-3 rounded bg-yellow-500 bg-opacity-10 border-l-4 border-yellow-500 text-sm">
⚡ <b>Por quê?</b> Alta performance, transações ACID e uma autoridade central clara (o banco ou a loja).
</div>

---

# Bancos de Dados
Saúde, Educação e Governo

<div class="grid grid-cols-2 gap-4 mt-4">

<div class="p-4 rounded bg-red-500 bg-opacity-10 border border-red-500">

### 🏥 Saúde
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

<div class="grid grid-cols-2 gap-4 mt-4">

<div class="p-4 rounded bg-indigo-500 bg-opacity-10 border border-indigo-500">

### 🏢 Corporativo / Governo
- ERP (SAP, TOTVS)
- CRM (Salesforce)
- RH e folha
- Receita Federal (CPF, IR)

</div>

<div class="p-4 rounded bg-pink-500 bg-opacity-10 border border-pink-500">

### 🎮 Mídia e Entretenimento
- Netflix / Spotify
- Redes sociais (posts, comentários)
- Games online (ranking, inventário)

</div>

</div>

<div class="mt-4 p-3 rounded bg-yellow-500 bg-opacity-10 border-l-4 border-yellow-500 text-sm">
🔐 <b>Por quê?</b> LGPD exige exclusão, dados sensíveis, correções são rotina e há um dono claro.
</div>

---

# *Blockchain*
Cadeia de Suprimentos

<div class="grid grid-cols-2 gap-3 mt-4 text-sm">

<div class="p-3 rounded bg-orange-500 bg-opacity-10 border border-orange-500">
☕ <b>Rastreio de café</b><br/>
<span class="opacity-70">Produtor → exportador → torrefação → loja</span>
</div>

<div class="p-3 rounded bg-green-500 bg-opacity-10 border border-green-500">
🥬 <b>Walmart + IBM Food Trust</b><br/>
<span class="opacity-70">Rastreia origem de contaminação em segundos</span>
</div>

<div class="p-3 rounded bg-blue-500 bg-opacity-10 border border-blue-500">
🚢 <b>Maersk TradeLens</b><br/>
<span class="opacity-70">Documentos entre armadores, portos e alfândegas</span>
</div>

<div class="p-3 rounded bg-pink-500 bg-opacity-10 border border-pink-500">
💎 <b>De Beers Tracr</b><br/>
<span class="opacity-70">Prova que o diamante não é "de sangue"</span>
</div>

<div class="p-3 rounded bg-red-500 bg-opacity-10 border border-red-500">
🥩 <b>Carne bovina</b> (JBS, Minerva)<br/>
<span class="opacity-70">Rastrear fazenda e evitar desmatamento</span>
</div>

</div>

<div class="mt-5 p-3 rounded bg-blue-500 bg-opacity-10 border-l-4 border-blue-500 text-sm">
💡 <b>Insight famoso:</b> o rastreio de alface no Walmart caiu de <b>7 dias</b> para <b>2,2 segundos</b>.
</div>

---

# *Blockchain*
Finanças, Arte e Governo

<div class="grid grid-cols-3 gap-3 mt-4 text-sm">

<div class="p-3 rounded bg-yellow-500 bg-opacity-10 border border-yellow-500">

### 💰 Cripto & DeFi
- Bitcoin
- Ethereum
- Stablecoins (USDC, USDT)
- DeFi (Aave, Uniswap)
- Ripple (remessas)

</div>

<div class="p-3 rounded bg-pink-500 bg-opacity-10 border border-pink-500">

### 🎨 NFTs
- Arte digital (Beeple)
- Ingressos de eventos
- ENS (domínios)
- Colecionáveis

</div>

<div class="p-3 rounded bg-blue-500 bg-opacity-10 border border-blue-500">

### 🏛️ Governo
- Registro de imóveis (Suécia, Geórgia)
- Cartório digital (Brasil)
- e-Residency (Estônia)
- Votação eletrônica
- Diplomas (Blockcerts)

</div>

</div>

<div class="mt-5 p-3 rounded bg-purple-500 bg-opacity-10 border-l-4 border-purple-500 text-sm">
🌍 <b>Por quê?</b> Múltiplos atores, ausência de autoridade central e necessidade de auditoria pública.
</div>

---

# *Blockchain*
Outros Setores

<div class="grid grid-cols-2 gap-4 mt-4">

<div class="p-4 rounded bg-red-500 bg-opacity-10 border border-red-500">

### 🏥 Saúde
- Prontuário compartilhado entre hospitais
- Rastreio de medicamentos
- Ensaios clínicos
- Consentimento do paciente

</div>

<div class="p-4 rounded bg-purple-500 bg-opacity-10 border border-purple-500">

### 🎓 Educação
- Diplomas e certificados verificáveis
- Histórico escolar portável
- Credenciais profissionais

</div>

</div>

<div class="grid grid-cols-2 gap-4 mt-4">

<div class="p-4 rounded bg-green-500 bg-opacity-10 border border-green-500">

### ⚡ Energia & ESG
- Créditos de carbono
- Comércio de energia solar (Power Ledger)
- Reciclagem (Plastic Bank)
- Auditoria de metas ESG

</div>

<div class="p-4 rounded bg-indigo-500 bg-opacity-10 border border-indigo-500">

### 🎮 Outros
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
layout: two-cols
---

# 📓 Analogia

::left::

<div class="pr-4">

### 🗄️ Banco de Dados

Um **caderno numa sala trancada**.

Só quem tem a chave (admin) entra, escreve, apaga ou corrige.

**Rápido e eficiente**, mas você precisa confiar em quem tem a chave.

</div>

::right::

<div class="pl-4">

### 🔗 Blockchain

Um **caderno fotocopiado para 1.000 pessoas**.

Quando alguém escreve uma página nova, todos verificam juntos.

Ninguém consegue apagar uma página antiga **sem que todos percebam**.

</div>

---
layout: section
---

# Aplicação

---

# Use Banco de Dados Tradicional quando...

<v-clicks>

- Há uma **entidade confiável** que controla os dados
- **Performance** e **custo** são críticos
- Dados precisam ser **atualizados ou excluídos**
- Requisitos legais como **LGPD** exigem exclusão
- Ex: sistema de RH, e-commerce, app bancário interno

</v-clicks>

<div class="mt-8 p-4 rounded bg-blue-500 bg-opacity-10 border-l-4 border-blue-500">
💡 <b>Na dúvida, comece por aqui.</b> Bancos tradicionais resolvem 90% dos casos.
</div>

---

# ✅ Use Blockchain quando...

<v-clicks>

- **Múltiplas partes** que não confiam totalmente entre si precisam compartilhar dados
- **Rastreabilidade** e **auditoria** são essenciais
- **Imutabilidade** é um requisito real
- Não existe (ou não se quer) uma autoridade central
- Ex: cadeia de suprimentos, registros de propriedade, criptomoedas

</v-clicks>

<div class="mt-8 p-4 rounded bg-purple-500 bg-opacity-10 border-l-4 border-purple-500">
⚠️ <b>Cuidado:</b> blockchain é caro, lento e complexo. Só use quando o problema exigir.
</div>

---
layout: fact
---

# *Blockchain* não substitui os bancos de dados.

---

# *Blockchain*

> É uma **ferramenta diferente** voltada para um **problema diferente**: confiança sem intermediário.

---
layout: center
class: text-center
---

# Para ir além

<div class="text-left inline-block mt-8">

- **"Blockchain Basics"** — Daniel Drescher
- **"Mastering Bitcoin"** — Andreas Antonopoulos
- **Explorador de blocos:** [etherscan.io](https://etherscan.io)
- **Visualização:** [blockchain-demo.herokuapp.com](https://blockchain-demo.herokuapp.com)

</div>

---
layout: center
class: text-center
---

# Obrigado! 🙌

<div class="mt-8 text-lg opacity-70">
Perguntas?
</div>

<div class="mt-12 text-sm opacity-50">
Slides feitos com <a href="https://sli.dev" target="_blank">Slidev</a>
</div>

---

# Referências

- [Blockchain vs Banco de Dados: Entenda a Diferença](https://101blockchains.com/pt/blockchain-vs-banco-de-dados/)
- 