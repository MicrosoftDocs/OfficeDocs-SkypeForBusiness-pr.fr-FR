---
title: Envoyer un courrier de bienvenue aux utilisateurs d’appels entrants dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 'Résumé : Découvrez comment Bienvenue les utilisateurs à la Conférence rendez-vous dans Skype entreprise Server.'
ms.openlocfilehash: d9f0740128a8790052534e63c95a8305f65bb96d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992831"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>Envoyer un courrier de bienvenue aux utilisateurs d’appels entrants dans Skype entreprise Server
 
**Résumé :** Découvrez comment accueillir des utilisateurs dans la Conférence rendez-vous dans Skype entreprise Server.
  
Après avoir configuré les conférences rendez-vous et les tests pour vérifier qu’ils fonctionnent correctement, vous devez définir des codes confidentiels (pin) d’identification personnels pour les utilisateurs et informer les utilisateurs de la disponibilité de cette fonctionnalité. Vous pouvez inclure des instructions d’introduction telles que le code confidentiel initial et le lien vers la page Web des paramètres de conférence rendez-vous. 
  
En règle générale, vous utilisez l’applet de action **Set-CsClientPin** pour réinitialiser des épingles, mais vous pouvez utiliser la procédure décrite dans cette rubrique si vous voulez envoyer un message de bienvenue d’introduction contenant les informations du code confidentiel. Si vous ne souhaitez pas envoyer ce message, utilisez plutôt **Set-CsClientPin**.
  
Vous pouvez utiliser le script **Set-CsPinSendCAWelcomeMail** pour définir le code confidentiel et envoyer un message électronique de bienvenue à un utilisateur. Par défaut, le script ne réinitialise pas les codes confidentiels déjà définis, mais vous pouvez utiliser le paramètre Force pour forcer la réinitialisation d’un code confidentiel. Le message électronique est envoyé à l’aide du protocole SMTP (Simple Mail Transfer Protocol).
  
Vous pouvez créer un script qui exécute le script **Set-CsPinSendCAWelcomeMail** de manière itérative pour définir des codes confidentiels et envoyer un message électronique à un groupe d’utilisateurs. Vous pouvez modifier le modèle du message électronique (le fichier CAWelcomeEmailTemplate.html) pour ajouter des liens supplémentaires aux pages intranet ou modifier le texte du message.
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>Définition d’un code confidentiel initial et envoi d’un message électronique de bienvenue

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins.
    
2. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
3. Exécutez la commande suivante dans l’invite de commandes :
    
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

**SmtpServer** Par défaut, le script utilise la valeur de la variable d’environnement réservée **$PSEmailServer** pour ce paramètre. Si la variable **$PSEmailServer** n’est pas définie, vous devez spécifier ce paramètre.
    
**Informations d’identification** Par défaut, le script utilise les informations d’identification de l’utilisateur actuel. Si l’utilisateur actuel n’a pas le droit d’envoyer un message électronique au nom de l’expéditeur spécifié dans le champ De, vous devez entrer ce paramètre. En règle générale, spécifiez ce paramètre si vous n’indiquez pas votre adresse de messagerie dans le champ De.
    
L’exemple ci-dessous illustre la création d’un code confidentiel, puis l’envoi d’un message électronique de bienvenue à Bob de la part de Marco. Il utilise le texte du message électronique enregistré dans le modèle par défaut et crée le message électronique au format HTML. L’objet par défaut est « Bienvenue dans les conférences rendez-vous » :
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

L’exemple ci-dessous illustre la création forcée du code confidentiel « 383042650 » pour Bob, même s’il en possède déjà un, puis l’envoi d’un message électronique de bienvenue à Bob de la part de Marco. Comme le paramètre Credential est spécifié, la personne exécutant la commande est invitée à entrer un mot de passe. Le message électronique est envoyé avec le protocole SSL (Secure Sockets Layer) :
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
