# Conceitos básicos de segurança

## Vulnerabilidade
Uma **vulnerabilidade** é uma fraqueza ou erro em um sistema (código, configuração, processo ou infraestrutura) que pode ser explorado por um agente mal‑intencionado ou até por acidente.  
Exemplos comuns: injeção de SQL, uso de senhas em texto plano, permissões excessivas, falta de validação de entrada.

## Ameaça
A **ameaça** representa a possibilidade de que alguém ou algo (atacante, malware, falha humana, evento natural) tente explorar uma vulnerabilidade. Cada ameaça tem um *perfil*: motivação, capacidade, oportunidade.

## Risco
**Risco** = Probabilidade de que a ameaça explore a vulnerabilidade × Impacto potencial.  
É avaliado qualitativamente (Baixo, Médio, Alto) ou quantitativamente (ex.: CVSS). O risco orienta a priorização de mitigação.

## Tríade CIA
- **Confidencialidade** – garantir que dados sensíveis estejam acessíveis apenas a quem tem permissão. Falhas típicas: vazamento de credenciais, exposição de arquivos.
- **Integridade** – assegurar que a informação não seja alterada, corrompida ou destruída sem detecção. Exemplos: alteração de registros de banco sem validação, ataques de replay.
- **Disponibilidade** – assegurar que os recursos estejam operacionais e acessíveis quando necessários. Exemplos: DoS, corrupção de arquivos críticos.

## Boas práticas de segurança de código
1. **Validação e sanitização de entrada** – Use *prepared statements*, ORMs ou bibliotecas que escapem dados; valide formato, tamanho e tipo.
2. **Armazenamento seguro de credenciais** – Nunca grave senhas em texto plano; utilize hash forte (bcrypt, argon2) com *salt*.
3. **Gerenciamento de recursos** – Use *context managers* (`with` em Python, `try‑with‑resources` em Java) para garantir fechamento de conexões, arquivos e sockets.
4. **Princípio do menor privilégio** – Conceda apenas as permissões necessárias a usuários, processos e bibliotecas.
5. **Registro (logging) e monitoramento** – Logar tentativas de login, erros críticos e atividades suspeitas; monitorar logs em busca de padrões de ataque.
6. **Limitação de tentativas** – Implementar bloqueio temporário, CAPTCHA ou atrasos exponenciais após falhas repetidas.
7. **Patch e atualização** – Manter dependências, bibliotecas e runtime atualizados para corrigir vulnerabilidades conhecidas.
8. **Revisão de código e análise estática** – Use ferramentas como Bandit, Semgrep, SonarQube ou OWASP Dependency‑Check para detectar falhas antes do deploy.
9. **Defesa em profundidade** – Camadas múltiplas de controle (validação de entrada, controle de acesso, criptografia, monitoramento) reduzem a probabilidade de sucesso de uma exploração.
10. **Teste de segurança** – Incorporar testes de penetração, fuzzing e análises de risco no ciclo de desenvolvimento (SDLC).
