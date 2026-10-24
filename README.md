# DIO Agent — GuardIA

Especialização do [DIO Agent](https://github.com/digitalinnovationone/dio-agent) com foco em **segurança da informação**.

---

## Sobre o projeto

O DIO Agent é um agente de IA mentor de estudantes da [DIO](https://dio.me). Esta versão — chamada de **GuardIA** — adiciona ao agente base um conjunto de conhecimentos e skills voltados para segurança da informação, com o objetivo de ensinar desenvolvedores a pensar em segurança desde a primeira linha de código.

A especialização foi escolhida porque a maioria dos cursos de programação ensina código funcional, mas raramente ensina código seguro. Integrar essa perspectiva dentro do fluxo natural de aprendizado da DIO faz com que o estudante absorva boas práticas de segurança sem precisar buscar esse conteúdo em outro lugar.

---

## O que foi adicionado

### Base de conhecimento: `agent/knowledge/security-basics.md`

Arquivo novo que serve de referência teórica para o agente sempre que o assunto envolver segurança. Contém:

- Definição de **vulnerabilidade**, **ameaça** e **risco**
- **Tríade CIA** (Confidencialidade, Integridade, Disponibilidade) com exemplos concretos
- **10 boas práticas de segurança de código**: validação de entrada, hash de senhas, menor privilégio, gerenciamento de recursos, logging, limitação de tentativas, patch de dependências, análise estática, defesa em profundidade e testes de segurança

### Skill: `vulnerability-analysis/SKILL.md`

Guia o agente a analisar código em busca de falhas de segurança. O processo tem 6 etapas:

1. Entender o contexto (linguagem, escopo)
2. Identificar a vulnerabilidade (injeção, credenciais, controle de acesso, erros, recursos)
3. Classificar pelo **MITRE ATT&CK** (ID e tática)
4. Avaliar o risco pela **tríade CIA** com severidade (Baixa / Média / Alta)
5. Orientar a mitigação — sem entregar a correção pronta
6. Confirmar o aprendizado com perguntas de verificação

### Skill: `cybersecurity-learning-path/SKILL.md`

Monta trilhas de estudo personalizadas para quem quer entrar na área de cibersegurança. Cobre as principais áreas de atuação (Blue Team/SOC, Red Team/Pentest, AppSec, Cloud Security, GRC, Forense Digital) e organiza o plano em três fases: fundamentos → conhecimento específico → prática e certificação. Conecta com experiências da DIO e recursos externos gratuitos.

### Skill: `devsecops-review/SKILL.md`

Orienta a revisão de código ou Pull Requests com olhar de segurança antes do merge ou deploy. Cobre as categorias de risco mais comuns em mudanças de código (entradas não validadas, autenticação, dependências, segredos, criptografia, sessão), apresenta um fluxo CI/CD DevSecOps recomendado e lista ferramentas open-source para cada etapa (Bandit, Semgrep, CodeQL, GitLeaks, OWASP ZAP, entre outras).

---

## O que foi alterado

### `AGENTS.md`

- Adicionada `agent/knowledge/security-basics.md` na seção de base de conhecimento
- Adicionadas as três novas skills na tabela de skills (`vulnerability-analysis`, `cybersecurity-learning-path`, `devsecops-review`)
- Adicionado o limite de segurança: o agente nunca entrega correções completas de vulnerabilidades sem antes conduzir o raciocínio do estudante

### `agent/persona.md`

- Adicionada a seção **Segurança da informação**: descreve o conhecimento do agente em CIA, vulnerabilidade, ameaça e risco, especifica quando acionar a skill `vulnerability-analysis` e reforça que o objetivo é ensinar a pensar em segurança, não apenas apontar e corrigir

---

## Estrutura dos arquivos adicionados

```
dio-agent-guardiai/
├── AGENTS.md                            ← alterado
├── agent/
│   ├── persona.md                       ← alterado
│   └── knowledge/
│       └── security-basics.md           ← novo
├── vulnerability-analysis/
│   └── SKILL.md                         ← novo
├── cybersecurity-learning-path/
│   └── SKILL.md                         ← novo
└── devsecops-review/
    └── SKILL.md                         ← novo
```

---

## Como rodar

Este projeto segue o padrão `AGENTS.md`. Qualquer harness compatível (Google Antigravity, Claude Code, Codex, Cursor, Gemini CLI) lê o arquivo automaticamente ao abrir a pasta.

1. Clone o repositório
2. Abra a pasta no harness de sua preferência
3. Comece a conversar — o agente já carrega a especialização em segurança

Consulte a [documentação do harness](https://antigravity.google/docs) para detalhes de instalação.
