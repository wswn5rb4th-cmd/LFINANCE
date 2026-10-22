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


## Módulos Finanças + Academia

A tela **Hoje** reúne um resumo financeiro e os treinos recentes. **Finanças** mantém lançamentos, cartões, parcelas e gráficos; **Academia** permite registrar sessões com exercício, séries, repetições, carga e duração. O **Assistente** interpreta frases de gasto/receita já existentes e prepara um registro de treino para revisão antes de salvar.

Os dados novos são salvos localmente junto aos dados financeiros. Na primeira abertura da versão unificada, os dados da chave antiga `lfinance-data-v1` são copiados para `lfinance-data-v2`; a chave antiga permanece intacta como cópia de segurança. Exportações JSON incluem os treinos também.

### WhatsApp

A tela mostra o estado de preparação da integração. Receber mensagens, áudios e fotos pelo WhatsApp requer um servidor HTTPS, configuração de webhook e credenciais da API oficial da Meta. Segredos de API não devem ser incluídos no JavaScript público do GitHub Pages. A interface não indica a conexão como ativa até esse serviço ser configurado.
