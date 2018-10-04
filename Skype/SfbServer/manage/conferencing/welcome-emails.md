---
title: Envoyer un message électronique de Bienvenue à distance en les utilisateurs de Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 'Résumé : Découvrez comment Bienvenue aux utilisateurs de conférence rendez-vous dans Skype pour Business Server.'
ms.openlocfilehash: 90c56fd97d9eb51c96c1a0cb149f732a31a70743
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373712"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>Envoyer un message électronique de Bienvenue à distance en les utilisateurs de Skype pour Business Server
 
**Résumé :** Découvrez la bienvenue aux utilisateurs de conférence rendez-vous dans Skype pour Business Server.
  
Après avoir configuré la conférence rendez-vous et test pour vérifier qu’il fonctionne correctement, vous définissez initiale personnel confidentiels (PIN) pour les utilisateurs et avertir les utilisateurs sur la disponibilité de la fonctionnalité. Vous pouvez inclure des instructions introduction telles que le code confidentiel initial et le lien vers la page web paramètres de conférence rendez-vous. 
  
En règle générale, vous utilisez l’applet de commande **Set-CsClientPin** pour réinitialiser les codes confidentiels, mais vous pouvez utiliser la procédure de cette rubrique si vous souhaitez envoyer un message électronique de bienvenue introduction avec les informations de code confidentiel. Si vous ne souhaitez pas envoyer ce message, utilisez plutôt **Set-CsClientPin**.
  
Vous pouvez utiliser le script **Set-CsPinSendCAWelcomeMail** pour définir le code confidentiel et envoyer un message électronique de bienvenue à un utilisateur. Par défaut, le script ne réinitialise pas les codes confidentiels déjà définis, mais vous pouvez utiliser le paramètre Force pour forcer la réinitialisation d’un code confidentiel. Le message électronique est envoyé à l’aide du protocole SMTP (Simple Mail Transfer Protocol).
  
Vous pouvez créer un script qui exécute le script **Set-CsPinSendCAWelcomeMail** de manière itérative pour définir des codes confidentiels et envoyer un message électronique à un groupe d’utilisateurs. Vous pouvez modifier le modèle du message électronique (le fichier CAWelcomeEmailTemplate.html) pour ajouter des liens supplémentaires aux pages intranet ou modifier le texte du message.
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>Définition d’un code confidentiel initial et envoi d’un message électronique de bienvenue

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Exécutez la commande suivante dans l’invite de commandes :
    
   ```
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

**SmtpServer** Par défaut, le script utilise la valeur de l’environnement réservé variable **$PSEmailServer** pour ce paramètre. Si la variable **$PSEmailServer** n’est pas définie, vous devez spécifier ce paramètre.
    
**Informations d’identification** Par défaut, le script utilise les informations d’identification de l’utilisateur actuel. Si l’utilisateur actuel n’a pas le droit d’envoyer un message électronique au nom de l’expéditeur spécifié dans le champ De, vous devez entrer ce paramètre. En règle générale, spécifiez ce paramètre si vous n’indiquez pas votre adresse de messagerie dans le champ De.
    
L’exemple ci-dessous illustre la création d’un code confidentiel, puis l’envoi d’un message électronique de bienvenue à Bob de la part de Marco. Il utilise le texte du message électronique enregistré dans le modèle par défaut et crée le message électronique au format HTML. L’objet par défaut est « Bienvenue dans les conférences rendez-vous » :
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

L’exemple ci-dessous illustre la création forcée du code confidentiel « 383042650 » pour Bob, même s’il en possède déjà un, puis l’envoi d’un message électronique de bienvenue à Bob de la part de Marco. Comme le paramètre Credential est spécifié, la personne exécutant la commande est invitée à entrer un mot de passe. Le message électronique est envoyé avec le protocole SSL (Secure Sockets Layer) :
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```