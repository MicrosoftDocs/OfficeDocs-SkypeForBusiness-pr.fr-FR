---
title: 'Lync Server 2013 : (Facultatif) Accueil des utilisateurs dans les conférences rendez-vous'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Welcome users to dial-in conferencing
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48185443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df3defde18a01ed09ac529ba9b289749f28c4cdd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>(Facultatif) Accueil des utilisateurs dans les conférences rendez-vous dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-30_

Après avoir configuré les conférences rendez-vous et les tests pour vérifier qu’ils fonctionnent correctement, vous devez définir des codes confidentiels (pin) pour les utilisateurs et informer les utilisateurs de la disponibilité de la fonctionnalité, y compris des instructions d’introduction telles que comme code confidentiel initial et le lien vers la page Web des paramètres de conférence rendez-vous. Cette étape est facultative. En règle générale, vous utilisez l’applet de connexion **Set-CsClientPin** pour réinitialiser des épingles, mais vous pouvez utiliser la procédure décrite dans cette rubrique pour la première fois si vous voulez envoyer un message de bienvenue aux informations. Si vous ne souhaitez pas envoyer ce message, utilisez plutôt **Set-CsClientPin**.

Vous pouvez utiliser le script **Set-CsPinSendCAWelcomeMail** pour définir le code confidentiel et envoyer un message électronique de bienvenue à un utilisateur. Par défaut, le script ne réinitialise pas de code confidentiel s’il est déjà défini, mais vous pouvez utiliser le paramètre **force** pour réinitialiser le code confidentiel. Le message électronique est envoyé à l’aide du protocole SMTP (Simple Mail Transfer Protocol).

Vous pouvez créer un script qui exécute le script **Set-CsPinSendCAWelcomeMail** de manière itérative pour définir des codes confidentiels et envoyer un message électronique à un groupe d’utilisateurs. Vous pouvez modifier le modèle de courrier électronique (c’est-à-dire, le fichier **CAWelcomeEmailTemplate. html** ) pour ajouter d’autres liens vers des pages intranet ou modifier le texte du message.

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>Pour définir un code confidentiel initial et envoyer un message de bienvenue

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez la commande suivante dans l’invite de commandes :
    
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
    
    **Informations d’identification**   par défaut, le script utilise les informations d’identification de l’utilisateur actuel. Si l’utilisateur actuel n’a pas le droit d’envoyer un message électronique au nom de l’expéditeur spécifié dans le champ De, vous devez entrer ce paramètre. En règle générale, spécifiez ce paramètre si vous n’indiquez pas votre adresse de messagerie dans le champ De.
    
    Par exemple :
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    Cet exemple crée un nouveau code confidentiel, puis envoie un courrier de bienvenue de Marco à Bob. Il utilise le texte du message électronique enregistré dans le modèle par défaut et crée le message électronique au format HTML. Le sujet par défaut est «bienvenue dans la conférence téléphonique».
    
    Autre exemple:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    Cet exemple force un nouveau code secret dont la valeur est «383042650» pour Bob, même si Bob possédait un code confidentiel existant, puis envoie un courrier de bienvenue de Marco à Bob. Comme le paramètre Credential est spécifié, la personne exécutant la commande est invitée à entrer un mot de passe. Le message est envoyé à l’aide du protocole SSL (Secure Sockets Layer).

</div>

</div>

<span> </span>

</div>

</div>

</div>

