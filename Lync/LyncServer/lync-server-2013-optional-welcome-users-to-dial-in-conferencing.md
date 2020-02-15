---
title: 'Lync Server 2013 : (facultatif) accueillir les utilisateurs pour la Conférence rendez-vous'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Welcome users to dial-in conferencing
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48185443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab4f4a7882c40095017d2678549edf618b78e29
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>Module Bienvenue les utilisateurs à la Conférence rendez-vous dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-30_

Après avoir configuré les conférences rendez-vous et testé leur bon fonctionnement, vous devez définir les codes confidentiels initiaux des utilisateurs et les avertir que cette fonctionnalité est disponible, sans oublier de leur fournir le code confidentiel initial et le lien vers la page Web Paramètres de conférence rendez-vous. Cette étape est facultative. En règle générale, vous utilisez la cmdlet **Set-CsClientPin** pour réinitialiser les codes confidentiels, mais vous pouvez faire appel à la procédure décrite dans cette rubrique la première fois si vous voulez envoyer un message électronique de bienvenue contenant ces informations. Si vous ne souhaitez pas envoyer ce message, utilisez plutôt **Set-CsClientPin**.

Vous pouvez utiliser le script **Set-CsPinSendCAWelcomeMail** pour définir le code confidentiel et envoyer un message électronique de bienvenue à un utilisateur. Par défaut, le script ne réinitialise pas les codes confidentiels déjà définis, mais vous pouvez utiliser le paramètre **Force** pour forcer la réinitialisation d’un code confidentiel. Le message électronique est envoyé à l’aide du protocole SMTP (Simple Mail Transfer Protocol).

Vous pouvez créer un script qui exécute le script **Set-CsPinSendCAWelcomeMail** de manière itérative pour définir des codes confidentiels et envoyer un message électronique à un groupe d’utilisateurs. Vous pouvez modifier le modèle du message électronique (le fichier **CAWelcomeEmailTemplate.html**) pour ajouter des liens supplémentaires aux pages intranet ou modifier le texte du message.

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>Pour définir un code confidentiel initial et envoyer un message électronique de bienvenue

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Exécutez la commande suivante à l’invite de commandes :
    
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
    
    **SmtpServer**   par défaut, le script utilise la valeur de la variable d’environnement réservée **$PSEmailServer** pour ce paramètre. Si la variable **$PSEmailServer** n’est pas définie, vous devez spécifier ce paramètre.
    
    **Credential**   par défaut, le script utilise les informations d’identification de l’utilisateur actuel. Si l’utilisateur actuel n’a pas le droit d’envoyer un message électronique au nom de l’expéditeur spécifié dans le champ De, vous devez entrer ce paramètre. En règle générale, spécifiez ce paramètre si vous n’indiquez pas votre adresse de messagerie dans le champ De.
    
    Par exemple :
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    Cet exemple illustre la création d’un code confidentiel, puis l’envoi d’un message électronique de bienvenue à Bob de la part de Marco. Il utilise le texte du message électronique enregistré dans le modèle par défaut et crée le message électronique au format HTML. L’objet par défaut est « Bienvenue dans les conférences rendez-vous ».
    
    Voici un autre exemple :
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    Cet exemple illustre la création forcée du code confidentiel « 383042650 » pour Bob, bien qu’il en ait déjà un, puis l’envoi d’un message électronique de bienvenue à Bob de la part de Marco. Comme le paramètre Credential est spécifié, la personne exécutant la commande est invitée à entrer un mot de passe. Le message électronique est envoyé avec le protocole SSL (Secure Sockets Layer).

</div>

</div>

<span> </span>

</div>

</div>

</div>

