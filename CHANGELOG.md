# Changelog — Sistema de Gestão de Biblioteca ## [v0.2.0-beta] - 2026-11-18 ###
Adicionado (Added) - Implementada funcionalidade de pesquisa de livros por título
ou autor (RF05) na classe Acervo. - Adicionada validação de `status_conta ==
"ATIVO"` antes de autorizar novos empréstimos (alinhado ao DD da E4). - Adicionado
registro da matrícula do `Bibliotecario` responsável nas transações de empréstimo
e devolução. ### Corrigido (Fixed) - [Bug #01] Corrigido cálculo de multa em
devoluções antecipadas usando `max(0, dias_atraso)` para evitar valores negativos.
- Padronizadas constantes de `status_livro` para `DISPONIVEL`, `EMPRESTADO` e
`MANUTENCAO`. ## [v0.1.0-alpha] - 2026-11-12 ### Adicionado (Added) - Estrutura
inicial do projeto e modelagem OO (`Usuario`, `Leitor`, `Bibliotecario`, `Livro`,
`Emprestimo`). - Implementação do prazo padrão de 7 dias para empréstimo (RF03) e
multa de R$ 1,50 por dia de atraso (RF06).
