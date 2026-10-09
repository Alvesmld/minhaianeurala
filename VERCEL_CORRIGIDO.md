# ALVESMLD v11 — pacote corrigido para Vercel

- O backend grava arquivos gerados em `/tmp/projetos_web`, evitando a tentativa de escrita em `/var/task`.
- A interface web é servida pelo próprio FastAPI no mesmo domínio; `web/config.js` usa URL vazia para chamadas same-origin.
- `pyproject.toml` declara `[project]` e o entrypoint `api_server:app`.
- Dependências de deploy reduzidas a FastAPI e Pydantic para evitar instalar bibliotecas pesadas de ML que não são usadas pela API web.

**Importante:** `/tmp` é temporário e pode ser limpo entre execuções. Links de download de projetos gerados podem expirar quando a função reiniciar. Para armazenamento persistente é necessário conectar um serviço de armazenamento externo.

**Publicação:** extraia o conteúdo desta pasta e envie todos os arquivos para a raiz do repositório GitHub ligado à Vercel. O `Root Directory` da Vercel deve ser `./` (ou `.`). Faça um novo deployment após o commit.
