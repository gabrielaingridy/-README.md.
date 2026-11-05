Documento de Definição de Escopo e Requisitos 
Projeto: Sistema de Gestão de Biblioteca

1. Definição do Problema 
Atualmente, a biblioteca registra os empréstimos e devoluções em papel ou planilhas isoladas. Esse processo manual resulta na perda do histórico de movimentações, gera grande dificuldade para saber quais livros estão efetivamente disponíveis no acervo e causa atrasos e inconsistências na cobrança de multas por devoluções fora do prazo.

2. Stakeholders (Público-Alvo)
Bibliotecários
Leitores (alunos, professores ou comunidade)
Administradores

3. Escopo do Projeto
Dentro do escopo: O sistema contemplará a gestão completa do catálogo de livros, o controle de empréstimos, a baixa de devoluções e o cálculo de multas geradas por atraso.
Fora do escopo: O sistema não incluirá um módulo de pagamento online integrado para as multas, nem permitirá a reserva de salas de estudo físicas da biblioteca.

4. Requisitos Funcionais (RF) Descrevem as ações e funcionalidades que o sistema deve executar para atender às necessidades do negócio:
RF01: O sistema deve permitir o registro de novos livros no catálogo.
RF02: O sistema deve permitir o registro de novos leitores.
RF03: O sistema deve registrar o empréstimo de um livro a um leitor.
RF04: O sistema deve registrar a devolução de livros.
RF05: O sistema deve permitir a pesquisa de livros por título ou autor.
RF06: O sistema deve calcular automaticamente a multa para devoluções em atraso.

5. Requisitos Não Funcionais (RNF) Descrevem as restrições, premissas de qualidade e critérios de desempenho do sistema:
RNF01: O sistema deve estar disponível via navegador web (plataforma web).
RNF02: O tempo de resposta para a pesquisa de livros não deve exceder 2 segundos.
RNF03: O sistema deve exigir autenticação segura por usuário e senha para o acesso dos bibliotecários e administradores.
