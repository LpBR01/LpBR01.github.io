# LoopingBR Publisher — Site institucional

Site estático (HTML/CSS), com **página inicial, política de privacidade e termos de serviço**. Não contém qualquer segredo nem código de publicação do GitHub Actions.

## ⚠️ Antes de colocar no ar

1. O e-mail de contato configurado é **gustarch26@gmail.com** nas páginas de privacidade e termos. **Esse endereço ficará público** quando o site for hospedado. Confirme que deseja divulgá-lo e que monitora esta caixa de entrada.
2. Leia a Política de Privacidade inteira e confirme que corresponde à sua configuração real. Os textos foram montados com base no código atual `publicar_youtube.py` e `bridge_pedido_chatgpt.py` no repositório privado, consultados em novembro de 2026. Revise especialmente se você alterar permissões OAuth, guardar outros dados ou habilitar recursos adicionais.
3. Revise se o nome do app no Google Cloud é exatamente `LoopingBR Publisher` (ou atualize o site e as informações do Google para combinar).
4. Nenhum token, `GOOGLE_CLIENT_SECRET`, refresh token, ID de cliente ou configuração privada deve ser colocado em HTML, JavaScript, commit público ou formulário deste site.
5. Depois de hospedar, teste os links da página inicial, `/privacidade.html` e `/termos.html` em navegador anônimo e no celular.

## Como visualizar agora (sem publicar)

Abra `index.html` no navegador ou execute, dentro desta pasta:

```bash
python -m http.server 8000
```

E acesse `http://localhost:8000`.

## Hospedagem gratuita (exemplo: GitHub Pages)

**Crie um repositório NOVO para o site, separado do repositório PRIVADO do publisher.** Publicar o repositório do site não publica o repositório da automação.

1. Crie no GitHub um novo repositório chamado, por exemplo, `loopingbr-publisher-site` (público somente depois de revisar os arquivos e o contato).
2. Faça upload de `index.html`, `privacidade.html`, `termos.html`, `styles.css` e `favicon.svg`. Não envie o ZIP completo do publisher, scripts de publicação, pedidos JSON nem credenciais.
3. No novo repositório, vá a **Settings → Pages → Build and deployment**, selecione `Deploy from a branch`, branch `main`, pasta `/ (root)` e salve.
4. Aguarde o link `https://SEU_USUARIO.github.io/loopingbr-publisher-site/` aparecer e teste as três páginas.
5. Configure os links reais do site no Branding do Google Auth Platform **somente quando os conteúdos estiverem corretos**.

### Observações essenciais sobre o Google OAuth

- **Hospedar o site, por si só, não garante a publicação nem a verificação OAuth.** O Google pode exigir domínio verificável sob seu controle, informações do Branding e avaliação dos escopos solicitados.
- Um subdomínio gratuito como `github.io` **não deve ser tratado como prova automática de controle de domínio para verificação no Search Console**. Para uma verificação que exija domínio próprio, pode ser necessário registrar um domínio.
- Os escopos do projeto atual incluem `drive.readonly`, `youtube.readonly` e `youtube.upload` e podem sujeitar o app a requisitos adicionais de verificação.
- O limite de sete dias para refresh tokens do app externo em Testing não é resolvido pela mera criação do site. Ele depende do estado/configuração do projeto OAuth e da autorização nova.
- Publicar o OAuth não torna o GitHub nem os secrets públicos, mas pode tornar nome do app, contatos e URLs visíveis na tela de consentimento.
- **Não altere credenciais nem publique o aplicativo OAuth sem revisar as configurações e, se for preciso, obter nova autorização.**

## Estrutura

- `index.html` — landing page sem login, formulários ou rastreadores.
- `privacidade.html` — explicação das permissões, dados e revogação OAuth.
- `termos.html` — condições e limitações de uso.
- `styles.css` — layout responsivo, sem fontes externas.
- `favicon.svg` — ícone vetorial local.

Este material é um ponto de partida para o site e não é parecer jurídico nem garantia de aprovação no Google OAuth.
