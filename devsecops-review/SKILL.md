---
name: devsecops-review
description: Use quando o estudante quer revisar código ou mudanças antes de ir para produção com foco em segurança, integrar práticas de segurança no fluxo de desenvolvimento, ou entender o que é DevSecOps e como aplicá-lo no dia a dia.
---

# Skill: Revisão de Segurança no Fluxo de Desenvolvimento (DevSecOps)

Orienta o estudante a revisar alterações de código sob a ótica de segurança antes que cheguem à produção, integrando práticas de DevSecOps no ciclo de desenvolvimento.

## Quando usar

O estudante:
- quer revisar um Pull Request, commit ou diff com foco em segurança;
- perguntou o que é DevSecOps ou como aplicar segurança no pipeline;
- quer saber quais verificações de segurança automatizar no CI/CD;
- ou está aprendendo a integrar ferramentas de análise estática e de dependências no fluxo de trabalho.

## Princípio: segurança é parte do desenvolvimento, não um passo final

O objetivo do DevSecOps é mover a segurança para o início do ciclo ("shift left"), evitando que vulnerabilidades cheguem à produção. O estudante precisa entender **por que** cada verificação existe, não apenas executá-la mecanicamente.

Não entregue a correção completa. Aponte o risco, explique o impacto e conduza o estudante ao raciocínio da mitigação.

## Processo

### 1. Entenda o contexto da mudança

Antes de revisar, descubra, uma pergunta de cada vez:
- O estudante compartilhou o código, diff ou PR? Se não, peça.
- Qual é a linguagem e o tipo de aplicação (web, API, CLI, mobile)?
- Existe já algum processo de revisão de segurança no projeto (linting, CI/CD, SAST)?
- A mudança vai para produção diretamente ou passa por testes/staging?

### 2. Revise o código com olhar de segurança

Analise as alterações seguindo as categorias de risco mais comuns em mudanças de código:

| Categoria | O que verificar |
|-----------|----------------|
| **Entradas não validadas** | Dados do usuário usados sem sanitização ou validação |
| **Autenticação e autorização** | Rotas protegidas? Tokens verificados? Permissões checadas? |
| **Exposição de dados sensíveis** | Logs com senhas, tokens ou PII; dados retornados desnecessariamente |
| **Dependências** | Novas libs adicionadas — versão segura? CVE conhecido? |
| **Configuração** | Segredos hardcoded, variáveis de ambiente expostas, debug ativo |
| **Criptografia** | Uso de algoritmos fracos (MD5, SHA1 para senhas), sem TLS, IV fixo |
| **Tratamento de erros** | Stack trace exposto, erros genéricos ocultando falhas críticas |
| **Gerenciamento de sessão** | Tokens sem expiração, sem revogação, armazenados de forma insegura |

Para cada item encontrado, aplique o fluxo da skill `vulnerability-analysis`: identifique → classifique (MITRE ATT&CK) → avalie risco (CIA) → oriente mitigação.

### 3. Verifique as dependências

Novas dependências são uma superfície de ataque frequentemente ignorada:
- A biblioteca está ativa e mantida?
- Existem CVEs conhecidos? (verificar em [nvd.nist.gov](https://nvd.nist.gov) ou via `npm audit`, `pip-audit`, `trivy`, etc.)
- Qual é o escopo mínimo necessário? (princípio do menor privilégio para dependências)

Oriente o estudante a usar ferramentas de auditoria de dependências no CI/CD.

### 4. Avalie o impacto no pipeline (CI/CD)

Ajude o estudante a entender quais verificações de segurança deveriam existir automaticamente antes do merge:

```
Fluxo DevSecOps recomendado
─────────────────────────────────────────────────────
Commit → SAST (análise estática) → Dependências (SCA)
       → Secrets scan → Testes de segurança → Deploy
─────────────────────────────────────────────────────
```

| Etapa | Ferramentas gratuitas / open-source |
|-------|-------------------------------------|
| **SAST** (análise estática) | Bandit (Python), Semgrep, CodeQL |
| **SCA** (dependências) | Dependabot, `npm audit`, `pip-audit`, Trivy |
| **Secrets scan** | GitLeaks, TruffleHog, GitHub Secret Scanning |
| **DAST** (dinâmico, opcional) | OWASP ZAP |

Não espere que o estudante implemente tudo de uma vez. Sugira começar pela verificação mais crítica para o contexto dele e evoluir incrementalmente.

### 5. Classifique e priorize os achados

Apresente os resultados de forma estruturada, priorizando pelo risco:

```
**Achado #N**
Categoria: [ex.: Entrada não validada]
Localização: [arquivo/linha/função]
Técnica MITRE: [ID – Nome] | Tática: [nome]
Impacto (CIA): [descrição]
Severidade: [Baixa / Média / Alta / Crítica]
Orientação: [o que mudar, sem entregar a solução completa]
```

Se não houver achados de segurança, confirme isso com o estudante e aproveite para reforçar boas práticas que o código já demonstra.

### 6. Eduque sobre o processo, não apenas sobre o achado

Depois de apontar um problema:
- Explique por que aquele padrão é arriscado (ex.: "o que acontece quando alguém passa `; DROP TABLE` nesse campo?").
- Mostre como o controle correto previne o ataque.
- Pergunte: "Você consegue identificar outro lugar no código onde o mesmo padrão pode aparecer?"

Isso transforma uma revisão pontual em aprendizado duradouro.

### 7. Confirme o aprendizado

Ao final, pergunte:
1. O risco ficou claro?
2. Você quer tentar aplicar a mitigação e me mostrar o resultado?
3. Quer entender como automatizar essa verificação no seu pipeline?

## Formato de saída

- Lista de achados estruturados (veja template no passo 5), ordenados por severidade.
- Orientações de mitigação para cada achado (sem solução completa).
- Sugestão de ferramentas para automatizar no CI/CD, adequadas ao contexto do projeto.
- Confirmação de boas práticas já presentes no código.

## Lembre-se

- Uma mudança pequena pode introduzir uma vulnerabilidade grande. Revise com atenção proporcional ao risco, não ao tamanho do diff.
- DevSecOps é cultura, não apenas ferramentas. O mais importante é o estudante desenvolver o hábito de pensar em segurança a cada linha que escreve.
- Combine com a skill `vulnerability-analysis` para aprofundar achados específicos.
- Comemore quando o estudante percebe um risco por conta própria. Isso é exatamente o objetivo.

