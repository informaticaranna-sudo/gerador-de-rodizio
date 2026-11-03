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
