# Loja Virtual 🛒

Projeto front-end simples (HTML/CSS/JS) com uma pequena loja demonstrando recursos práticos de UX e engenharia front-end.

## ✅ Recursos implementados

- Layout moderno e responsivo com grid de produtos e cartões refinados
- Seleção de quantidade no catálogo (antes de adicionar)
- Carrinho lateral (slide-in) com:
  - Contagem total de itens (soma das quantidades)
  - Alteração de quantidade por item (botões + / −)
  - Remoção por ícone de lixeira (botão SVG com `aria-label`)
  - Total recalculado por quantidade
- Persistência do carrinho via `localStorage` (itens e quantidades são preservados)
- Object pool simples para reaproveitamento de elementos DOM do carrinho (melhora performance)
- Placeholders de imagem (fallback) quando uma imagem falha ao carregar
- Acessibilidade: focus trap no painel do carrinho e fechamento com `ESC` + `aria-labels` em controles
- Header fixo que não muda de tamanho ao adicionar itens
- Código enxuto e modular no `scripts.js` (classes `Produto` e `Carrinho`)


## Estrutura do projeto

```
Site de Loja/
├─ index.html         # HTML principal
├─ styles.css         # Estilos (design refinado, responsividade)
├─ scripts.js         # Lógica: produtos, pool, carrinho, persistência e UI
├─ README.md          # Documentação (este arquivo)
├─ camisa.png
├─ calca.png
├─ tenis.png
├─ bone.png
```


## Como usar / testar rapidamente

1. Abra `index.html` no navegador ou sirva a pasta localmente (recomendado):

   - Python 3:
     ```bash
     python -m http.server 8000
     # Acesse http://localhost:8000
     ```

2. No catálogo, ajuste a quantidade no campo numérico e clique **Adicionar ao carrinho**.
3. O painel lateral abre automaticamente — verifique quantidades, use **+ / −** para ajustar e o ícone de lixeira para remover.
4. Recarregue a página: o carrinho (itens e quantidades) deve persistir.
5. Para testar fallback de imagem, altere temporariamente um caminho de imagem em `scripts.js` — um placeholder será exibido.
6. Abra o carrinho e teste o teclado: Tab/Shift+Tab devem ficar dentro do painel e ESC fecha-o.


## Notas técnicas rápidas

- Produtos: array `produtos` em `scripts.js`. Cada produto é instanciado como `new Produto(nome, preco, imagem)` e recebe um `id` gerado automaticamente.
- Persistência: chave `localStorage` = `carrinho`, formato salvo: `[{id, qty}, ...]`.
- Performance: `ObjectPool` reaproveita elementos DOM do painel para reduzir alocações e tornar re-renderizações mais suaves.
- A lógica principal está em `scripts.js`: `renderizarProdutos()`, `adicionarAoCarrinho()`, `renderizarCarrinho()`.


## Melhores práticas / próximos passos sugeridos

- Adicionar testes unitários (Jest) para a classe `Carrinho` e fluxos principais.
- Adicionar CI (GitHub Actions) para executar testes automaticamente.
- Publicar demo em GitHub Pages ou Netlify para compartilhar o projeto.
- Melhorias de UX: toasts de confirmação, animações subtis, suporte a filtros/categories.


---


## 📄 Licença

Projeto aberto — sinta-se à vontade para usar, adaptar ou enviar melhorias.

---



