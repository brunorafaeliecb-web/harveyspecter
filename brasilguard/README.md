# BrasilGuard Harvey Specter — piloto inicial

## Estado
DRAFT — alteração isolada na branch `feature/brasilguard-pilot`. NÃO ativa. Não executa descoberta nem dispara e-mails automaticamente.

## Origem e licença
Fork de https://github.com/ethanplusai/harvey (licença MIT, manter LICENSE e avisos do autor Ethan Rogers).

## Objetivo
Piloto de 20 empresas para qualificação com evidências de fontes públicas e rascunhos de mensagens sujeitos a aprovação humana. Integração CRM/Supabase posterior aos testes.

## Proteções obrigatórias
- 0 e-mails/dia, email.enabled=false; linkedin.enabled=false.
- Não conectar contas pessoais de e-mail ao piloto sem permissão explícita.
- Não inventar contatos nem enriquecer CPFs. Minimização LGPD, registro de fonte, opt-out.
- Nenhum envio automático sem revisão humana e avaliação de conformidade.
- Não misturar o repositório com bgd-get-brolls ou Cinematik.

## Plano de QA
1. Instalar em venv isolado Python >=3.11, inspecionando dependências antes.
2. Executar pytest e testes de isolamento Claude CLI; registrar logs e versões.
3. Validar que nenhuma campanha envia com channels.email.enabled=false.
4. Descobrir 20 empresas em modo não invasivo, verificar deduplicação/fonte e pontuação.
5. Revisão humana antes de ligar integrações ou publicar.

## Nota de configuração
`brasilguard/pilot.yaml` é um ESBOÇO de overlay e não substitui automaticamente `harvey.yaml`. Confirmar o parser e o merge antes de aplicá-lo. Na ausência de confirmação, bloqueio do envio deve ser implementado/testado na execução real.
