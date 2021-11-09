---
title: Envoyer un e-mail de bienvenue aux utilisateurs d’appels Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 'Résumé : Découvrez comment accueillir les utilisateurs à la conférence Skype Entreprise Server.'
ms.openlocfilehash: 672e386c223e2b5b9f872334634ac315c9e900e1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848537"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>Envoyer un e-mail de bienvenue aux utilisateurs d’appels Skype Entreprise Server
 
**Résumé :** Découvrez comment accueillir les utilisateurs à des conférences téléphoniques dans Skype Entreprise Server.
  
Après avoir configuré les conférences téléphoniques et vérifié qu’elles fonctionnent correctement, vous devez définir des numéros d’identification personnelle initiaux pour les utilisateurs et informer les utilisateurs de la disponibilité de la fonctionnalité. Vous pouvez inclure des instructions d’introduction telles que le code confidentiel initial et le lien vers la page web conférence Paramètres conférence. 
  
En règle générale, vous utilisez l’cmdlet **Set-CsClientPin** pour réinitialiser les code confidentiels, mais vous pouvez utiliser la procédure de cette rubrique si vous souhaitez envoyer un message électronique de bienvenue d’introduction avec les informations de code confidentiel. Si vous ne souhaitez pas envoyer ce message, utilisez plutôt **Set-CsClientPin**.
  
Vous pouvez utiliser le script **Set-CsPinSendCAWelcomeMail** pour définir le code confidentiel et envoyer un message électronique de bienvenue à un utilisateur. Par défaut, le script ne réinitialise pas les codes confidentiels déjà définis, mais vous pouvez utiliser le paramètre Force pour forcer la réinitialisation d’un code confidentiel. Le message électronique est envoyé à l’aide du protocole SMTP (Simple Mail Transfer Protocol).
  
Vous pouvez créer un script qui exécute le script **Set-CsPinSendCAWelcomeMail** de manière itérative pour définir des codes confidentiels et envoyer un message électronique à un groupe d’utilisateurs. Vous pouvez modifier le modèle du message électronique (le fichier CAWelcomeEmailTemplate.html) pour ajouter des liens supplémentaires aux pages intranet ou modifier le texte du message.
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>Définir un code confidentiel initial et envoyer un e-mail de bienvenue

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins.
    
2. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
3. Exécutez la commande suivante à l’invite de commandes :
    
   ```PowerShell
   Set-CsPinSendCAWelcomeMail -UserUri <user identifier>
   -From <email address of sender> [-Subject <subject for email message>]
   [-UserEmailAddress <destination email address>]
   [-Cc <email address of recipients who receive copy of email>]
   [-Bcc <email address of recipients who receive blind copies>]
   [-TemplatePath <path for email template>]
   [-SmtpServer] <SMTP server name>]
   [-BodyAsPlainText] [-UseSsl]
   [-Pin <new numeric PIN>] [-Force] `
   [-Credential <SMTP server credentials used to send email with the specified From address>]
   ```

**SmtpServer** Par défaut, le script utilise la valeur de la variable **d’environnement réservée $PSEmailServer** pour ce paramètre. Si la variable **$PSEmailServer** n’est pas définie, vous devez spécifier ce paramètre.
    
**Informations d’identification** Par défaut, le script utilise les informations d’identification de l’utilisateur actuel. Si l’utilisateur actuel n’a pas le droit d’envoyer un message électronique au nom de l’expéditeur spécifié dans le champ De, vous devez entrer ce paramètre. En règle générale, spécifiez ce paramètre si vous n’indiquez pas votre adresse de messagerie dans le champ De.
    
L’exemple suivant crée un code confidentiel, puis envoie un message électronique de bienvenue de Marco à Bob. Il utilise le texte du message électronique enregistré dans le modèle par défaut et crée le message électronique au format HTML. L’objet par défaut est « Bienvenue dans les conférences téléphoniques » :
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

L’exemple suivant force un nouveau code confidentiel avec la valeur « 383042650 » pour Bob, même si Bob en avait déjà un, puis envoie un message électronique de bienvenue de Marco à Bob. Comme le paramètre Credential est spécifié, la personne exécutant la commande est invitée à entrer un mot de passe. Le courrier électronique est envoyé à l’aide du SSL (Secure Sockets Layer) :
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
