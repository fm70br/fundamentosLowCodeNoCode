# 📋 Administrador de Tarefas (Bubble.io)

![Status do Projeto](https://img.shields.io/badge/Status-Conclu%C3%ADdo-brightgreen)
![Plataforma](https://img.shields.io/badge/Plataforma-Bubble.io-0052CC)
![Licença](https://img.shields.io/badge/Licen%C3%A7a-MIT-blue)

Uma aplicação web completa desenvolvida sem código (No-Code) na plataforma **Bubble.io** para solucionar o desafio de gestão de tarefas, prazos e colaboração em equipes corporativas e pequenas organizações.

<img src="adm_tarefas_main.png" alt="Administrador de tarefas">

---

## 🔗 Links de Acesso

- **Aplicação Funcional (Ambiente de Teste):** [https://administradortarefas.bubbleapps.io/version-test](https://administradortarefas.bubbleapps.io/version-test)
- **Vídeo Pitch de Apresentação:** *(Insira o link do seu vídeo gravado aqui)*

---

## 🎯 Funcionalidades Principais

- **🔒 Autenticação e Gestão de Usuários:** Cadastro, login, perfis diferenciados e controle de acesso às rotas da aplicação.
- **📊 Painel Kanban / Lista de Tarefas:** Visualização clara das tarefas organizadas por status, prioridades e prazos de entrega.
- **📝 Gestão do Ciclo de Vida da Tarefa:** Criação, edição, atribuição de responsáveis e alteração dinâmica de status (*Pendente*, *Em Andamento*, *Concluído*).
- **💬 Central de Comentários & Colaboração:** Modais dedicadas para discussões internas em tempo real associadas a cada tarefa.
- **🔔 Notificações & E-mails Automáticos:** Envio automatizado de e-mails para notificantes/atribuídos quando uma nova interação ou alteração de status ocorre.
- **🎯 Modais Interativas:** Modais exclusivas para criação de tarefas, detalhes, novos usuários e central de notificações.

---

## 🗄️ Modelagem do Banco de Dados

A arquitetura de dados relacional (1:N) no Bubble é composta por três tipos de dados principais (*Data Types*):

### 1. `User` (Usuário)
* `email` *(text)*: Endereço de e-mail do usuário.
* `nome` *(text)*: Nome completo.
* `foto` *(image)*: Avatar de perfil.
* `role` *(text)*: Nível de permissão/função no sistema.

### 2. `Task` (Tarefa)
* `titulo` *(text)*: Título descritivo da tarefa.
* `descricao` *(text)*: Detalhamento das atividades.
* `status` *(text)*: Estado atual (*A Fazer*, *Em Andamento*, *Concluído*).
* `prioridade` *(text)*: Nível de urgência (*Baixa*, *Média*, *Alta*).
* `data_entrega` *(date)*: Prazo final limite.
* `atribuido_a` *(User)*: Usuário responsável pela execução.
* `criador` *(User)*: Usuário criador da tarefa.

### 3. `Comment` (Comentário)
* `texto` *(text)*: Conteúdo do comentário.
* `tarefa_relacionada` *(Task)*: Tarefa vinculada ao comentário.
* `autor` *(User)*: Usuário criador do comentário.
* `data_criacao` *(date)*: Timestamp da mensagem.

---

## ⚙️ Arquitetura de Workflows & Lógica

A aplicação utiliza **18 workflows customizados** para automação de processos de negócio:

1. **Criação e Edição de Tarefas:** Validação de campos obrigatórios e gravação no banco de dados.
2. **Atualização Dinâmica de Status:** Alteração dinâmica com atualização de timestamps e notificações associadas.
3. **Disparo de E-mails via SendGrid:** Notificação automática por e-mail quando tarefas são criadas ou comentadas.
4. **Navegação & Modais:** Abertura e fechamento condicional de modais com reset automático de campos.

---

## 🚀 Publicação & Manutenção

- **Ambiente de Teste (`version-test`):** Utilizado para desenvolvimento, validação de regras de negócio e inserção de dados fictícios.
- **Deploy em Produção:** Migração em um clique diretamente pelo painel administrativo do Bubble.
- **Plano de Manutenção Contínua:**
  - Backups automáticos de estado da aplicação.
  - Monitoramento de registros e logs de workflows.
  - Ajustes de permissões e privacidade (*Privacy Rules*).

---

## 🛠️ Tecnologias Utilizadas

- **Plataforma No-Code:** [Bubble.io](https://bubble.io/)
- **Provedor de E-mail (SMTP):** SendGrid integration via Bubble Workflow Actions
- **Banco de Dados:** Bubble Native Database

---

## ✒️ Autor

- **Nome:** Fabio Minami
- **Projeto:** Primeiro Produto Digital com Bubble (Low-Code / No-Code)
