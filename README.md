# Aplicação TF — Web

Visualizador publicado da **Aplicação TF** (dashboard financeiro pessoal, precursor do Gerenciador Financeiro).

**Acesso protegido por senha.** Apenas o conteúdo encriptado client-side (AES-256-GCM via PBKDF2) está neste repo. Senha custódia pessoal de `tiago@freitas.com`.

Fonte: repo privado [`tiagofreitas83/aplicacao-tf`](https://github.com/tiagofreitas83/aplicacao-tf).

## Para atualizar

1. No working tree do repo `aplicacao-tf`: `npm run build:standalone` → gera `Aplicação TF.html`.
2. Encriptar:

   ```bash
   export STATICRYPT_PASSWORD='<senha>'
   npx staticrypt "Aplicação TF.html" --short -o index.html --title "Aplicação TF — Tiago Freitas"
   unset STATICRYPT_PASSWORD
   ```

   (staticrypt v4 cria pasta `encrypted/` — mover `encrypted/Aplicação TF.html` para `./index.html` na raiz do repo `-web`.)
3. `git add index.html && git commit -m "Atualiza build" && git push`.
