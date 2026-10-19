---
theme: default
colorSchema: dark
title: Software Descentralizado
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

- Trilema da escalabilidade
- Tipos de redes
- EVM
- IPFS

---
layout: section
---

# Trilema da Escalabilidade

- Descentralização
- Segurança
- Escalabilidade

---

# Trilema da Escalabilidade
Descentralização

> Refere-se a quantidade de nós validadores necessários para aprovar um bloco.

> Quanto maior a quantidade de nós, maior a resistência a censura

---

# Resistência a Censura
*Censorship resistance*

- Rede descentralizada
- Nenhum nó isoladamente é capaz de bloquear ou apagar uma transação
- Para reescrever o histórico seria necessário controlar mais de 50% da rede (Ataque de 51%)

[O que é um ataque de 51% e quais são os riscos?](https://www.coinbase.com/pt-br/learn/crypto-glossary/what-is-a-51-percent-attack-and-what-are-the-risks)

---

# Resistência a Censura
*Censorship resistance*

> Diferente de uma *blockchain*, onde o poder é distribuído por milhares de nós independentes, nas redes centralizadas existe um ponto único de falha. O proprietário dos servidores dita as regras de forma absoluta.

---

# Trilema da Escalabilidade
Segurança

- Confiança é distribuída por toda a rede, em vez de depender de uma entidade única
- Se apoia em três pilares fundamentais: 
    - Criptografia avançada, 
    - Mecanismos de consenso
    - Descentralização
- Juntos, esses elementos garantem que as informações registradas sejam praticamente invioláveis e imutáveis.

---

# Trilema da Escalabilidade
Escalabilidade

> Capacidade de processar transações (*throughput*)

---

# Trilema da Escalabilidade
Escalabilidade

> Capacidade da rede de processar um grande volume de Transações Por Segundo (TPS) de forma rápida e barata.

---

# Escalabilidade
Gargalos

- Processamento de CPU
- Largura de banda
- Armazenamento de estado

---



---

# Referências

[O que é um ataque de 51% e quais são os riscos?](https://www.coinbase.com/pt-br/learn/crypto-glossary/what-is-a-51-percent-attack-and-what-are-the-risks)

---
layout: fact
---

# Perguntas

---
src: /snippets/end.md 
---