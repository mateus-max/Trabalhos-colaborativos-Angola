# Trabalhos Colaborativos Angola

Aplicação web inicial de colaboração empresarial, publicada por GitHub Pages e ligada ao Firebase do projeto `trabalhos-colaborativos-angola`.

## Funcionalidades implementadas
- Registo e início de sessão por e-mail e palavra-passe (Firebase Authentication).
- Criação e listagem de projetos.
- Documentos partilhados com sincronização automática pela Realtime Database.
- Tarefas com responsável, prazo e estado concluído.
- Chat por projeto em tempo real.
- Upload e partilha de ficheiros através do Firebase Storage.
- Indicador simples de utilizadores online.
- Interface adaptável a computador e telemóvel.

## Publicação
O ficheiro de entrada é `index.html`. Configure GitHub Pages na branch `main`, pasta raiz. O domínio personalizado é mantido no ficheiro `CNAME`.

## Configuração Firebase necessária
1. Authentication > Sign-in method > Email/Password deve estar ativado.
2. Realtime Database deve estar criada.
3. Ative Firebase Storage e configure regras de acesso autenticado.
4. Autorize o domínio publicado em Authentication > Settings > Authorized domains.

A aplicação utiliza a URL da Realtime Database: `https://trabalhos-colaborativos-angola-default-rtdb.firebaseio.com`.

## Segurança — antes de abrir ao público
A autenticação no ecrã não substitui regras de segurança. Esta versão inicial ainda não implementa convites, gestão de membros nem isolamento completo de projetos por utilizador. Não coloque dados confidenciais ou empresariais reais até configurar e testar regras que validem a associação do utilizador a cada projeto na Realtime Database e no Storage. Nunca use regras públicas (`.read: true` / `.write: true`) em produção.

A listagem inicial consulta o nó `workspaces`; por isso, uma política de produção deverá evoluir para um índice por utilizador (por exemplo, `userWorkspaces/{uid}`) e regras que permitam ler apenas os projetos dos quais o utilizador é membro.

## Próximas etapas recomendadas
1. Convites por e-mail, funções de administrador, gestor e colaborador, e permissões por projeto.
2. Editor rico com cursores/edição simultânea real (CRDT/Operational Transformation), histórico e comentários.
3. Folhas de cálculo colaborativas, calendário, reuniões de áudio/vídeo e partilha de ecrã.
4. Kanban, cronogramas, aprovações, formulários, relatórios e notificações.
5. Auditoria, backups, limites de upload, antivírus e políticas de retenção.
