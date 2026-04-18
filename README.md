🚀 Padrões de Engenharia | PlanB
Este documento define como nos comunicamos através do código. Seguir estes padrões facilita o rastreio de bugs, automatiza changelogs e torna o Code Review muito mais fluido.

📍 1. Padrões de Commit
Na PlanB, utilizamos o Conventional Commits. Cada commit deve ser claro e seguir a estrutura:
<tipo>(escopo): descrição curta

Tipos principais:
feat: Uma nova funcionalidade para o usuário.

fix: Correção de um bug.

docs: Alterações apenas na documentação.

style: Alterações que não afetam o sentido do código (espaço em branco, formatação, ponto e vírgula, etc).

refactor: Alteração de código que não corrige um bug nem adiciona um recurso.

perf: Mudança de código que melhora o desempenho.

test: Adição de testes ausentes ou correção de testes existentes.

chore: Atualizações de tarefas de build, configurações de pacotes, etc.

Exemplos:
feat(auth): adiciona suporte a login com JWT

fix(api): corrige timeout na busca de produtos

chore(deps): atualiza versao do react-native

🌿 2. Branching Strategy
Para manter a organização, nomeie suas branches com o tipo e o identificador da tarefa:

feature/PB-123-nome-da-task

bugfix/PB-456-descricao-do-erro

hotfix/ajuste-urgente

🔍 3. Pull Requests (PRs)
O PR é o momento de compartilhar conhecimento. Para que ele seja aprovado rápido, siga este checklist:

O que um bom PR deve ter:
Título Claro: Ex: [PB-123] Implementa módulo de pagamento.

Descrição: O que foi feito? Por que foi feito? Alguma observação técnica?

Contexto Visual: Se houver mudança de UI, anexe um Screenshot ou GIF.

Auto-Review: Antes de pedir revisão, leia seu próprio código no GitHub para pegar erros bobos ou console.log esquecidos.

Template de PR (Sugerido):
Markdown
## 📝 Descrição
Breve resumo do que este PR resolve.

## 🛠️ O que foi feito?
- [x] Implementação da função X.
- [x] Refatoração do componente Y.
- [x] Adição de testes unitários.

## 🧪 Como testar?
1. Faça o checkout da branch...
2. Execute o comando `npm install`...
3. Verifique o comportamento em...

## 📸 Screenshots (Opcional)
[Insira imagens aqui]
💡 Boas Práticas no Code Review
Atomicidade: Tente manter commits pequenos e PRs focados. PRs com +500 linhas são difíceis de revisar e propensos a erros.

Feedback Construtivo: Ao revisar, sugira melhorias em vez de apenas apontar erros. Use: "O que você acha de usar X aqui para melhorar a performance?"

Aprovação: Um PR só deve sofrer merge após o Approve de pelo menos um par e a passagem de todos os testes no CI.
