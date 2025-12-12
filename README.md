# uriasfutmaster

FutMaster — sistema para gerir filas e formar times (Racha). Esta versão corrige o sorteio dos 10 primeiros, sincronização Firebase e comportamento de reset.

## Deploy (GitHub Pages)

1. O repositório já tem um `index.html` na raiz. Para publicar com GitHub Pages:
   - Vá a Settings → Pages → Source e escolha `main` branch (root) e salve.
   - Aguarde alguns segundos — a página ficará disponível em https://<your-username>.github.io/<repo-name>/ (ex.: https://jmartins94.github.io/uriasfutmaster/).

2. Atualizações:
   - Faça commit e push para `main`. O GitHub Pages re-publicará automaticamente.

## Deploy alternativo (Netlify)

1. Conecte o repositório ao Netlify e selecione a branch `main`.
2. Para sites estáticos sem build step, deixe os comandos de build vazios e configure o diretório de publicação para `/`.

## Notas sobre Firebase

- O código inclui sincronização com Firebase Realtime Database. A sincronização é controlada pela constante `ENABLE_FIREBASE` no `index.html`.
- Para evitar sobrescrita indesejada, o app usa um campo `updatedAt` no estado e aplica remotamente apenas updates mais recentes.
- Se preferir desativar a sincronização temporariamente para debug, defina `ENABLE_FIREBASE` para `false`.

## Correções aplicadas

- Sortear os 10 primeiros: agora copia os 10 primeiros, embaralha apenas estes, cria Time A e Time B e em seguida forma os times do restante da fila em sequência (sem embaralhar).
- Reset (Nova Noite): limpa state e permite adicionar nomes novamente sem precisar recarregar.
- Proteção Firebase: comparação por `updatedAt` para evitar sobrescrita acidental.


---
