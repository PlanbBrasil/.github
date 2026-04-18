
### 🔄 Fluxo de Integração: Rebase First

Para manter um histórico limpo e facilitar o `bisect` caso surjam bugs, adotamos a estratégia de **Rebase**:

1.  **Sempre faça Rebase:** Antes de finalizar seu trabalho e abrir o PR (ou antes de mergear), faça o rebase da sua branch com a `develop` (ou branch de destino). Isso garante que seus commits fiquem no topo do histórico atualizado.
    ```bash
    git checkout feature/sua-task
    git fetch origin
    git rebase origin/develop
    ```
2.  **Resolva conflitos localmente:** Se houver conflitos, resolva-os durante o rebase. Isso evita que o PR chegue "sujo" ou quebre o CI.
3.  **Force Push (com cuidado):** Após o rebase, será necessário usar o push forçado na sua branch de feature. Use preferencialmente:
    ```bash
    git push --force-with-lease
    ```
4.  **Merge Limpo:** No GitHub, preferimos a opção **"Squash and merge"** ou **"Rebase and merge"** para manter a linha principal sempre linear e funcional.

---
