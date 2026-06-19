# Documento de Requisitos - DevUp

**Projeto:** DevUp - Produtividade com Saúde  
**Versão:** 1.0  
**Finalidade:** especificar, de forma resumida, os requisitos do DevUp, plataforma corporativa que une produtividade, hábitos saudáveis, gamificação e acompanhamento gerencial.

## Atores Principais

| Ator | Descrição |
|---|---|
| Colaborador | Registra hábitos, tarefas, humor e acompanha progresso. |
| Gestor | Consulta métricas, engajamento e desempenho da equipe. |
| Empresa/Admin | Mantém equipes, integrações e recompensas. |

## Escopo do MVP

| Item | Descrição |
|---|---|
| Aplicativo | Autenticação, hábitos, tarefas, progresso, ranking e notificações. |
| Painel do gestor | Visão de equipe, adesão semanal e colaboradores destaque. |
| Gestão de configuração | Controle de versão com `main`, `develop`, `feature/*` e Pull Requests. |

## Requisitos Funcionais

| ID | Requisito |
|---|---|
| RF01 | Permitir autenticação por e-mail e senha, gerando token de sessão e registrando data/hora do login. |
| RF02 | Permitir cadastro de usuários com perfil Colaborador ou Gestor, e impedir e-mails duplicados. |
| RF03 | Permitir criar hábitos nas categorias Saúde, Produtividade e Estudos, com frequência diária/semanal e lembrete opcional. |
| RF04 | Permitir registrar cumprimento de hábito uma vez por dia, atualizando pontos, sequência e progresso semanal. |
| RF05 | Permitir criar tarefas com prazo, prioridade e status; ao concluir, atribuir pontos conforme prioridade. |
| RF06 | Exibir progresso semanal com hábitos cumpridos e tarefas concluídas por dia. |
| RF07 | Calcular pontuação, sequência e conquistas por marcos de 3, 7, 14, 30, 60 e 100 dias. |
| RF08 | Exibir rankings por empresa/equipe e por categoria, notificando o usuário quando subir de posição. |
| RF09 | Oferecer painel do gestor com engajamento, taxa de adesão, hábitos frequentes e colaboradores destaque. |
| RF10 | Registrar humor diário com nota de 1 a 5 e alertar o gestor quando a nota for igual ou menor que 2. |
| RF11 | Gerar recompensas relâmpago com bônus, expiração de 2 horas e resgate único por usuário. |
| RF12 | Enviar notificações de lembrete, conquista, ranking e recompensa, com possibilidade de integração a Slack/Teams. |

## Regras de Negócio

| ID | Regra |
|---|---|
| RN01 | Hábitos concedem pontos conforme categoria: Saúde = 15, Produtividade = 10 e Estudos = 12. |
| RN02 | Tarefas concluídas concedem pontos conforme prioridade: Alta = 20, Média = 10 e Baixa = 5. |
| RN03 | O mesmo hábito não pode ser registrado mais de uma vez pelo mesmo usuário no mesmo dia. |
| RN04 | Gestores só podem visualizar equipes e colaboradores para os quais possuem permissão. |
| RN05 | Recompensas expiram após 2 horas e só podem ser resgatadas uma vez por usuário. |

## Requisitos Não Funcionais

| ID | Categoria | Requisito | Critério de verificação |
|---|---|---|---|
| RNF01 | Segurança | As senhas dos usuários devem ser armazenadas somente em formato criptografado/hash, sem gravação de senha em texto puro. | Validar cadastro/login e verificar que o banco não contém senha legível. |
| RNF02 | Autenticação | O acesso ao sistema deve usar token de sessão associado ao ID e ao perfil do usuário, impedindo uso de funcionalidades sem login. | Tentar acessar hábitos, tarefas, ranking e painel sem token válido. |
| RNF03 | Permissão | Funcionalidades de gestor devem exigir perfil Gestor e permissão sobre a equipe consultada. | Usuário sem permissão deve receber mensagem de acesso negado. |
| RNF04 | Privacidade | Dados de humor, saúde e comentários devem ser tratados como sensíveis, visíveis apenas ao próprio usuário e aos gestores autorizados. | Testar acesso cruzado entre usuários e equipes diferentes. |
| RNF05 | Usabilidade | O registro de hábito, tarefa e humor deve exigir poucos passos e apresentar mensagens claras de sucesso ou erro. | Usuário deve concluir cada registro sem ajuda externa e receber feedback imediato. |
| RNF06 | Confiabilidade | Falhas ao salvar registros, gerar gráficos ou carregar equipes devem cancelar a operação, preservar dados anteriores e gerar log interno. | Simular falha de gravação/carregamento e conferir mensagem e log. |
| RNF07 | Desempenho | Consultas principais, como progresso semanal, ranking e painel da equipe, devem carregar em tempo aceitável para uso diário. | Executar consulta com dados simulados e verificar resposta sem travamentos perceptíveis. |
| RNF08 | Rastreabilidade | Alterações em documentos, pseudocódigo e artefatos do projeto devem ser versionadas no GitHub com branches, Pull Requests e commits padronizados. | Conferir histórico com commits `docs`, `feat`, `fix` e fluxo `main`, `develop` e `feature/*`. |
| RNF09 | Manutenibilidade | Os módulos de autenticação, hábitos, tarefas, gamificação, ranking, gestor, humor e recompensas devem permanecer separados para facilitar evolução. | Revisar estrutura do pseudocódigo e confirmar responsabilidades por módulo. |

## Critérios de Aceite

| Critério | Condição de aceite |
|---|---|
| CA01 | Usuário inválido recebe mensagem de credenciais inválidas e não acessa o sistema. |
| CA02 | Cumprimento de hábito válido atualiza registro, pontuação, sequência e gráfico/progresso. |
| CA03 | Gestor visualiza apenas equipes permitidas e recebe erro de acesso negado quando não autorizado. |
| CA04 | Humor com nota baixa gera alerta ao gestor responsável. |
| CA05 | Recompensa dentro do prazo pode ser resgatada uma única vez e adiciona bônus ao usuário. |
