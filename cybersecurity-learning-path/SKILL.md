---
name: cybersecurity-learning-path
description: Use quando o estudante quer aprender cibersegurança e não sabe por onde começar, qual área seguir ou como montar uma trilha de estudos estruturada na área de segurança.
---

# Skill: Trilha de Estudos em Cibersegurança

Ajuda o estudante a construir um caminho de aprendizado em cibersegurança — do zero até um objetivo concreto de carreira — conectado às experiências da DIO e ao mercado de trabalho.

## Quando usar

O estudante:
- quer entrar na área de cibersegurança mas não sabe por onde começar;
- perguntou sobre carreiras em segurança (Red Team, Blue Team, AppSec, Cloud Security, etc.);
- quer montar um plano de estudos focado em segurança;
- ou mencionou certificações como CompTIA Security+, CEH, OSCP, CISSP.

## Princípio: conecte o plano ao objetivo real do estudante

Cibersegurança é uma área ampla. Uma trilha genérica de "tudo sobre segurança" é longa demais e desmotivante. O plano precisa ser ancorando em:
- uma **área de atuação** (ex.: pentest, defesa, desenvolvimento seguro, forense);
- o **nível atual** do estudante (fundamentos de TI, programação, redes);
- um **objetivo concreto** (primeiro emprego, transição de área, certificação, desafio da DIO).

## Processo

### 1. Entenda o perfil e o objetivo

Descubra, uma pergunta de cada vez:
- O estudante já tem base em TI, redes ou programação? (Cibersegurança exige fundamentos.)
- Qual área de segurança mais desperta interesse? Use a tabela abaixo para orientar.
- Tem um objetivo claro? (ex.: vaga como analista SOC, certificação Security+, Bootcamp DIO.)
- Quanto tempo por semana consegue dedicar?

| Área | O que faz | Pré-requisitos principais |
|------|-----------|--------------------------|
| **Blue Team / SOC** | Monitora ameaças, responde a incidentes, analisa logs | Redes, sistemas operacionais |
| **Red Team / Pentest** | Simula ataques, identifica falhas | Redes, programação, SO Linux |
| **AppSec** | Analisa e protege código e aplicações | Programação, HTTP, bancos de dados |
| **Cloud Security** | Segurança em ambientes cloud (AWS, Azure, GCP) | Cloud computing, redes, IAM |
| **GRC / Compliance** | Governança, risco e conformidade | Frameworks (ISO 27001, LGPD, NIST) |
| **Digital Forensics** | Análise de incidentes, coleta de evidências | SO, redes, sistemas de arquivos |

Se o estudante não souber qual área escolher, ajude-o a descobrir com perguntas sobre o que já faz ou o que mais gosta.

### 2. Verifique os pré-requisitos

Antes de montar a trilha de segurança, confirme que o estudante tem (ou vai construir) os fundamentos:
- **Redes:** TCP/IP, DNS, HTTP/HTTPS, firewalls, VPNs.
- **Sistemas operacionais:** comandos Linux, permissões, processos.
- **Programação básica** (especialmente para AppSec e Pentest): Python ou outra linguagem.

Se faltar base, inicie a trilha pelos fundamentos e depois avance para segurança. Um plano sem base não funciona.

### 3. Monte a trilha em fases

Divida o plano em três fases progressivas:

**Fase 1 – Fundamentos** *(se necessário)*
- Redes de computadores
- Sistemas operacionais (Linux focus)
- Lógica de programação e Python básico
- Conceitos de cibersegurança: CIA, vulnerabilidade, ameaça, risco (`agent/knowledge/security-basics.md`)

**Fase 2 – Conhecimento específico da área**
- Ferramentas e técnicas da área escolhida (ex.: Nmap, Burp Suite, Splunk, Wireshark)
- Frameworks relevantes (OWASP, MITRE ATT&CK, NIST CSF)
- CTFs e laboratórios práticos (TryHackMe, Hack The Box, PicoCTF)

**Fase 3 – Prática e certificação**
- Desafios de Projeto na DIO com foco em segurança
- Simulados e preparação para certificações (Security+, eJPT, CEH)
- Portfólio no GitHub com write-ups e projetos de segurança

### 4. Conecte com a DIO

Verifique quais experiências da DIO cobrem o tema (Bootcamps, Formações, Cursos, Desafios de Projeto). Use a skill `study-plan` em conjunto se o estudante quiser um cronograma detalhado baseado em uma trilha específica da DIO.

> ℹ️ Não invente cursos ou Bootcamps da DIO. Conecte apenas com o que você sabe que existe ou peça ao estudante para compartilhar o link da trilha para montar um plano fiel.

### 5. Distribua no tempo e defina marcos

- Distribua as fases respeitando o tempo disponível do estudante.
- Defina marcos concretos (ex.: "ao fim da fase 1, você deve conseguir fazer um scan básico com Nmap e entender o resultado").
- Mostre que segurança é uma jornada contínua: o campo muda rápido, e o hábito de acompanhar novidades (CVEs, blogs, comunidades) é parte da carreira.

### 6. Entregue e ajuste

Apresente o plano de forma organizada. Pergunte se faz sentido com a rotina do estudante e ajuste conforme a resposta.

## Formato de saída

- Resumo do objetivo, da área escolhida e do nível atual.
- As três fases com tópicos e ferramentas relevantes.
- Marcos de progresso por fase.
- Indicações de recursos DIO e, quando adequado, recursos externos gratuitos (documentação oficial, plataformas de CTF).

## Lembre-se

- Cibersegurança sem fundamentos de TI é construir em areia. Não pule essa etapa.
- Prática vale mais que teoria: CTFs, labs e projetos reais ensinam mais do que cursos passivos.
- Comemore cada fase concluída. A área pode parecer intimidante no começo.
- Combine com as skills `explain-concept` (para conceitos novos) e `vulnerability-analysis` (quando surgir código vulnerável no caminho).

