# LFINANCE

Aplicativo de finanças pessoais em português, feito com HTML, CSS e JavaScript puro. Funciona sem backend: os registros ficam no `localStorage` do navegador.

## Executar localmente

Como o service worker requer uma origem segura, sirva os arquivos por HTTP em vez de abrir o HTML diretamente. Por exemplo, com Python instalado:

```bash
python -m http.server 8000
```

Abra `http://localhost:8000`. Não há dependências nem etapa de build.

## Publicar no GitHub Pages

O workflow em `.github/workflows/pages.yml` publica automaticamente o conteúdo da raiz quando há push na branch `main`. No repositório, habilite **Settings → Pages → Build and deployment → Source: GitHub Actions**. Após a primeira execução, o app estará em `https://wswn5rb4th-cmd.github.io/LFINANCE/`.

Para instalação no iPhone, abra o endereço no Safari, use **Compartilhar → Adicionar à Tela de Início**. A interface e os arquivos essenciais são armazenados para uso offline após a primeira visita. O reconhecimento de voz depende do suporte do navegador e de permissão ao microfone; a entrada por texto permanece disponível.

## Recursos

- Resumo de saldo, receitas, despesas, fatura, gráfico mensal e gastos por categoria.
- Lançamentos editáveis e removíveis, com receita, despesa e compra no cartão.
- Cartões com limite, fatura calculada pelas compras registradas e parcelas futuras.
- Entrada por fala ou frase digitada em português.
- Preferências de nome e moeda, categorias editáveis, cartões, exportação/importação JSON e limpeza de dados.
- Manifesto PWA, ícones SVG, service worker e layout responsivo com áreas seguras do iPhone.

## Dados e privacidade

Os dados persistem no navegador deste dispositivo. Limpar os dados do site remove os registros locais; use **Ajustes → Exportar dados** para guardar um backup. A importação substitui o conjunto atual de dados.
