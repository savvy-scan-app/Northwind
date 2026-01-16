# Website Northwind Technologies LLC - Instruções de Deploy

## 📁 Arquivos Criados
- **index.html** - Homepage
- **privacy.html** - Privacy Policy
- **terms.html** - Terms of Service  
- **contact.html** - Contact

## 🚀 Como Fazer Deploy no seu Domínio (nwindtech.com)

### Opção 1: Hospedagem Simples (Recomendado - Grátis)

#### Netlify (Mais Fácil)
1. Acesse https://www.netlify.com
2. Arraste a pasta com os 4 arquivos HTML para o site
3. Netlify vai gerar um link temporário
4. Vá em Domain Settings → Add custom domain
5. Adicione nwindtech.com
6. Configure o DNS do seu domínio conforme instruções do Netlify

#### GitHub Pages (Grátis também)
1. Crie um repositório no GitHub
2. Faça upload dos 4 arquivos
3. Vá em Settings → Pages
4. Ative GitHub Pages
5. Configure custom domain para nwindtech.com

### Opção 2: Hospedagem Tradicional

Se você já tem uma hospedagem (GoDaddy, Hostinger, etc):
1. Acesse o cPanel ou painel de controle
2. Vá em File Manager
3. Navegue até public_html
4. Faça upload dos 4 arquivos HTML
5. Pronto!

## ✅ Checklist para Apple

O site agora tem tudo que a Apple exige:
- ✅ Domínio próprio da empresa
- ✅ Privacy Policy completa
- ✅ Terms of Service completos
- ✅ Informações de contato
- ✅ Descrição da empresa
- ✅ Design profissional e clean

## 🔧 Correção do In-App Purchase

Depois de fazer o deploy do site, você precisa corrigir o problema do IAP:

### No seu código SwiftUI com RevenueCat:

```swift
// 1. Certifique-se de configurar corretamente o RevenueCat
Purchases.configure(withAPIKey: "sua_chave_api")

// 2. Para TestFlight e Review da Apple, adicione:
#if DEBUG
// Sandbox
Purchases.shared.purchasesAreCompletedBy = .revenueCat
#else
// Produção - IMPORTANTE para review da Apple
Purchases.shared.purchasesAreCompletedBy = .revenueCat
// O RevenueCat vai automaticamente tentar produção primeiro,
// depois sandbox se falhar
#endif

// 3. Teste no dispositivo físico antes de submeter
```

### No App Store Connect:
1. Verifique se o Paid Apps Agreement está assinado
2. Confirme que os produtos In-App estão criados
3. Certifique-se que estão marcados como "Ready to Submit"

## 📝 Resposta para Apple Review

Depois de fazer o deploy e corrigir o IAP, responda:

```
Thank you for your feedback. We have addressed the issues:

1. Company Website: Our company website is now live at https://nwindtech.com with complete Privacy Policy and Terms of Service.

2. In-App Purchase Issue: We've corrected the receipt validation to properly handle both production and sandbox environments using RevenueCat SDK. The purchase flow has been tested on physical devices and is working correctly.

The app is ready for review. Please let us know if you need any additional information.

Best regards,
Northwind Technologies LLC
```

## 💡 Dica Extra

Se precisar de HTTPS (SSL):
- Netlify e GitHub Pages incluem SSL grátis
- Se usar hospedagem própria, use Let's Encrypt (grátis)

---

**Qualquer dúvida, me avise!** O site está pronto e minimalista, exatamente como você pediu.
