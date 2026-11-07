1. Revisão e Correção dos Requisitos Pouco Claros (da E1)
Problema identificado nos requisitos iniciais: Requisitos genéricos como "permitir o registro" ou "pesquisa" podem gerar ambiguidades durante o projeto.
 
Requisitos Refinados e Clarificados:
RF01 (Catálogo): O sistema deve permitir que o bibliotecário cadastre, edite e inative livros informando título, autor, ISBN, editora e ano de publicação.
RF03 (Empréstimo): O sistema deve registrar o empréstimo vinculando um leitor ativo a um livro disponível, definindo a data de devolução em 7 dias e alterando o status do livro para "Emprestado".
RF06 (Multa): O sistema deve calcular automaticamente a multa de R$ 1,50 por dia útil de atraso no momento em que o bibliotecário registrar a devolução.
RNF02 (Desempenho): O tempo de resposta da consulta do acervo via interface web não deve ultrapassar 2 segundos para até 10.000 registros.
 ATIVIDADE AULA 1.pdf

2. Arquitetura de Alto Nível (4 Blocos)
[	 1. Web Frontend ] <---> [ 2. API RESTful ] <---> [ 3. Banco de Dados ] | v [ 4. Notificador Email ] 
Bloco 1: Web Frontend (Interface do Usuário)
Responsabilidade: Renderizar as telas de login, pesquisa de acervo, formulários de empréstimo/devolução e dashboard de pendências para leitores e bibliotecários.
Bloco 2: API RESTful (Camada de Regras de Negócio e Serviços)
Responsabilidade: Processar a lógica da aplicação: validar disponibilidade de exemplares, calcular valores de multas por atraso, controlar permissões e intermediar a persistência.
Bloco 3: Banco de Dados Relacional (Persistência de Dados)
Responsabilidade: Armazenar dados estruturados de leitores, livros, histórico de empréstimos, devoluções e multas geradas.
Bloco 4: Notificador de E-mails (Serviço de Apoio Externo)
Responsabilidade: Serviço assíncrono para envio diário automático de lembretes de devolução e avisos de multas para os leitores.


3. Diagramas UML do Projeto Integrador
Diagrama 1: Diagrama de Casos de Uso

Atores: Bibliotecário e Leitor.
Fronteira do Sistema: Sistema de Gestão de Biblioteca.
Casos de Uso Principais:
Leitor: [ Pesquisar Livros ], [ Consultar Empréstimos ], [ Receber Alerta de Multa ].
Bibliotecário: [ Cadastrar Livro ], [ Cadastrar Leitor ], [ Registrar Empréstimo ], [ Registrar Devolução ].

Diagrama 2: Diagrama de Classes
imagem no documento.

4. Interfaces Principais e Dados Manipulados
Interfaces Principais
Interface de Usuário (GUI Web):
Tela de Consulta do Acervo: Busca aberta para leitores por título/autor.
Painel do Bibliotecário: Formulário rápido de registro de empréstimo/devolução informando código do livro e matrícula do leitor.
Interface de Comunicação (API REST - JSON):
POST /api/emprestimos: Recebe { leitorId, livroId } e retorna status do agendamento.
POST /api/devolucoes: Recebe { emprestimoId } e retorna valor da multa calculada.

Principais Dados Manipulados
Dados de Leitores: Matrícula/ID, Nome Completo, E-mail, Tipo (Aluno/Professor), Status da Conta.
Dados do Acervo (Livros): Código/ISBN, Título, Autor, Editora, Ano, Status (Disponível, Emprestado, Manutenção).
Dados de Empréstimo e Cobrança: ID do Empréstimo, Data de Saída, Data Limite, Data Efetiva de Entrega, Valor da Multa, Status do Pagamento.

5. Plano de Gestão: Equipe, Recursos, Riscos e Acompanhamento
Equipe e Atribuições
Jéssica Vieira de Melo da Silva: Analista de Requisitos e Projetista (Modelagem UML e Documentação de Arquitetura).
Gabriela Ingridy De Andrade: Desenvolvedora e Testadora (Estruturação de Dados, Validação e Controle de Versão).

Recursos Necessários
Ferramentas de Modelagem: Astah / Mermaid.js / Diagrams.net para confecção dos diagramas UML.

Infraestrutura/Ambiente: Repositório GitHub, VS Code, ambiente Node.js/Python e banco de dados SQLite/PostgreSQL.

Riscos e Ações Preventivas
Risco 1: Falha de comunicação sobre regras de prazo/multa gerando divergências nos relatórios.
Ação Preventiva: Validação prévia da regra do cálculo de multas diretamente com os bibliotecários.
Risco 2: Perda de dados ou divergência de versões do código durante a modelagem.
Ação Preventiva: Adoção de padrão rígido de commits e branches no GitHub com atualizações diárias.

Estratégia de Acompanhamento
Reuniões Semanais (Sprints): Alinhamentos curtos de 15 minutos para verificação do progresso e ajuste do escopo.
Métricas de Entrega: Verificação do status de cada funcionalidade via repositório GitHub (Issues e Pull Requests).
