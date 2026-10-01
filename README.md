# Press Start · José Neto

Portfólio em formato de apresentação com cara de game. São 13 fases em 1920×1080 que se ajustam a qualquer tela. É um arquivo HTML só, com CSS e JavaScript puros, sem build e sem dependências.

## Fases

1. **Capa**: nome em fonte pixelada com distorção de vidro (WarpText em WebGL2) e rastro de pixels no cursor.
2. **Player**: janela `jose_neto.exe` com GAME START que se desfaz em pixels e mostra o avatar caminhando pela cidade, com carros nas duas faixas e a barra "Now playing" da trilha.
3. **Formação**: as quatro formações destravando em sequência, com as certificações como conquistas.
4. **Save points**: o avatar caminha pela linha do tempo e para de frente no fim. Cada fase abre uma caixa de diálogo com as atribuições do cargo.
5. **Manifesto**: com peças de Tetris caindo ao lado.
6. **Mundos 1 a 4**: Sebrae RS (com uma fase bônus de landing pages rolando numa janela), Rider/Grendene, Sicredi/Jotacom e Agência Órbita. As peças aparecem em mosaico de pixels e mostram uma descrição ao passar o cursor.
7. **Missões especiais**: ilustração e editorial.
8. **Inventário**: uma mochila cai, abre, a câmera mergulha nela e o painel com 23 peças aparece.
9. **Continuar?**: contagem regressiva que nunca chega a zero.

## Controles

- `→` `espaço` `Enter`: próxima fase · `←`: anterior · `Home` / `End`: início e fim
- Rodinha do mouse, swipe no celular ou clique na barra de XP
- `F`: tela cheia
- `♪`: liga e desliga os efeitos sonoros
- Botão da trilha (canto superior ou barra Now playing): pausa e volta a música
- Abrir direto numa fase: `index.html#s5`

A trilha e os efeitos são 8-bit, sintetizados na hora com Web Audio. O navegador só libera som depois do primeiro clique ou tecla, por isso a música começa no start. Tudo respeita `prefers-reduced-motion`.

## Publicar no GitHub Pages

1. Crie um repositório vazio no GitHub, por exemplo `press-start`.
2. Na pasta do projeto:

   ```bash
   git remote add origin https://github.com/SEU-USUARIO/press-start.git
   git branch -M main
   git push -u origin main
   ```

3. Em **Settings → Pages**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`.
4. Em alguns minutos fica no ar em `https://SEU-USUARIO.github.io/press-start/`.

Pra testar local, basta abrir o `index.html` ou rodar `npx serve .`.

## Trocar conteúdo

- **Peças e prints**: tudo fica em `img/`. Salvar um arquivo novo com o mesmo nome troca a imagem na apresentação.
- **Textos das experiências**: lista `JOBS` no script do `index.html`.
- **Descrições das peças**: objeto `DESC` no script.
- **Painel do inventário**: lista `INV` no script.

Os efeitos WarpText, PixelTrail, PixelSwap e DriftWall foram adaptados dos componentes do [React Bits](https://reactbits.dev) para JavaScript puro.
