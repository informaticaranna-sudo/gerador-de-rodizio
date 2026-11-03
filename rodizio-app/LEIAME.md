# Rodízio de Organistas (app)

Reproduz a planilha "GERADOR DE RODÍZIO AUTOMÁTICO" (v5-a). Tudo roda no aparelho, sem internet.

## Testar agora
Abra `index.html` no navegador do celular ou do computador.

## Instalar no Android como app
1. Hospede esta pasta em qualquer site HTTPS gratuito (GitHub Pages, Netlify, Cloudflare Pages).
2. Abra o endereço no Chrome do Android > menu ⋮ > **Instalar app**.

## Gerar o arquivo .apk
Opção mais simples: https://www.pwabuilder.com
1. Cole o endereço HTTPS do passo anterior > Package for stores > **Android** > Generate.
2. Baixe o pacote; dentro vem o `.apk` para instalar direto no celular.

Opção para desenvolvedores (Capacitor):
```
npm init -y && npm i @capacitor/core @capacitor/cli @capacitor/android
npx cap init Rodizio br.app.rodizio --web-dir=.
npx cap add android && npx cap sync
npx cap open android      # Android Studio > Build > Build APK(s)
```

## Banco de dados e relatório
- Tudo é guardado no próprio aparelho, em banco de dados (IndexedDB), um registro por ano: dados, rodízio gerado, ensaios, batismos, santas ceias e telefones.
- A aba **Relatório** lê do banco e mostra, para o ano escolhido: resumo, rodízio completo, telefones, batismos e santas ceias. Pode imprimir/salvar em PDF, compartilhar como texto ou excluir o ano.
- Os dados ficam no navegador/app do aparelho; limpar os dados do navegador apaga o banco.

## Novidades desta versão
- **Rodízio em formato de planilha**: uma tabela por mês (Dia · Sem · Culto), com cabeçalho, linhas alternadas e domingos destacados. O botão **Baixar planilha** gera um arquivo .csv que abre no Excel / Google Planilhas.
- **Organistas só da meia-hora** (opcional): se a lista ficar vazia, a meia-hora repete as organistas do culto oficial.
- **Reunião de jovens e menores** (opcional): marque “Incluir reunião de jovens e menores”, escolha o(s) dia(s) e, se quiser, informe as organistas. Lista vazia = repete as organistas do culto oficial. Aparece como coluna própria no rodízio, no relatório, na planilha e no texto compartilhado.
- Ao usar **Próximo ano**, a sequência das organistas de meia-hora e de jovens e menores também continua de onde parou.
- Visual novo, mais delicado (tons de rosa e lilás, claro e escuro).
- Se você já instalou o app, feche e abra de novo (ou limpe o cache) para pegar a versão nova. Os dados já guardados continuam.
