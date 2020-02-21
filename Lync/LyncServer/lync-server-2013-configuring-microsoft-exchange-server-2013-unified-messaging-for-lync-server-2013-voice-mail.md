---
title: 'Lync Server 2013 : configuration de la messagerie unifiée Microsoft Exchange Server 2013 pour Lync Server 2013 Voice Mail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebce894ae93b9071a880b35dffd039225b5485cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a>Configuration de la messagerie unifiée Microsoft Exchange Server 2013 pour Microsoft Lync Server 2013 Voice Mail

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-04_

Microsoft Lync Server 2013 vous permet de stocker des messages vocaux dans Microsoft Exchange Server 2013 ; ces messages vocaux apparaissent alors sous forme de messages électroniques dans la boîte de réception de vos utilisateurs. Cette fonctionnalité est également disponible dans les éditions 2010 de Lync Server et d’Exchange ; Toutefois, le processus de configuration de cette « messagerie unifiée » a été simplifié dans les éditions de 2013, grâce à l’introduction du composant routeur des appels de messagerie unifiée. Ce composant est installé sur le serveur d’accès au client Exchange 2013 et tous les appels à la messagerie unifiée Exchange (par exemple, une messagerie vocale) sont d’abord acheminés via le routeur d’appel, puis sont redirigés vers le serveur de boîtes aux lettres approprié.

Si vous avez déjà configuré l’authentification de serveur à serveur entre Lync Server 2013 et Exchange 2013, vous êtes prêt à configurer la messagerie unifiée. Pour ce faire, vous devez d’abord créer et attribuer un nouveau plan de numérotation de messagerie unifiée sur votre serveur Exchange. Par exemple, ces deux commandes (exécutées à partir de l’environnement de ligne de commande Exchange Management Shell) configurent un nouveau plan de numérotation à 3 chiffres pour Exchange :

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

Dans la première commande de cet exemple, le paramètre VoIPSecurity et la valeur « Secured » du paramètre indiquent que le canal de signalisation est chiffré à l’aide du protocole TLS (Transport Layer Security). La valeur « SipName » de URIType indique que les messages seront envoyés et reçus à l’aide du protocole SIP et la valeur 1 de CountryOrRegionCode signifie que le plan de numérotation s’applique aux États-Unis.

Dans la seconde commande, la valeur transmise au paramètre ConfiguredInCountryOrRegionGroups indique quels groupes régionaux peuvent être utilisés avec ce plan de numérotation. La valeur du paramètre « Anywhere\*,\*,\*, » définit les éléments suivants :

  - Nom du groupe (« Anywhere »)

  - AllowedNumberString (\*, un caractère générique indiquant que n’importe quelle chaîne de numéros est autorisée)

  - DialNumberString (\*, un caractère générique indiquant que n’importe quel numéro composé est autorisé)

  - TextComment (\*, un caractère générique indiquant que n’importe quelle commande de texte est autorisée)

<div>


> [!NOTE]  
> La création d’un plan de numérotation entraîne également la création d’une stratégie de boîte aux lettres par défaut.



</div>

Après avoir créé et configuré le nouveau plan de numérotation, vous devez ajouter le nouveau plan de numérotation à votre serveur de messagerie unifiée, puis modifier le mode de démarrage de ce serveur ; en particulier, vous devez définir le mode de démarrage sur « double ». Vous pouvez effectuer ces deux tâches à partir de l’environnement de commande Exchange Management Shell :

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

Une fois le serveur de messagerie unifiée configuré, vous devez exécuter la cmdlet Enable-ExchangeCertificate pour vous assurer que votre certificat Exchange est appliqué au service de messagerie unifiée :

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

Une fois le certificat correctement affecté, vous devez arrêter et redémarrer le service MsExchangeUM sur le serveur de messagerie unifiée. Ce service doit être arrêté et redémarré à chaque fois que vous modifiez le mode de démarrage.

Une fois la configuration du serveur de messagerie unifiée terminée, vous pouvez passer à la configuration du routeur d’appels de la messagerie unifiée :

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

Comme le mode de démarrage a été modifié, vous devez arrêter et redémarrer le service MsExchangeUMCR sur l’ordinateur qui héberge le routeur d’appels de la messagerie unifiée.

Pour terminer la configuration de la messagerie unifiée, vous devez ensuite créer une stratégie de boîte aux lettres de la messagerie unifiée et utiliser cette stratégie afin d’activer les utilisateurs pour la messagerie unifiée. Vous pouvez créer une stratégie de boîte aux lettres à l’aide d’une commande similaire à celle-ci :

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

Et vous pouvez activer un utilisateur pour la messagerie unifiée en utilisant une commande semblable à celle-ci :

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

Dans la commande précédente, le paramètre Extensions représente le numéro de poste de l’utilisateur. Dans cet exemple, le numéro de poste de l’utilisateur est le 100.

Une fois sa boîte aux lettres activée, l’utilisateur kenmyer@litwareinc.com doit être en mesure d’utiliser la messagerie unifiée Exchange. Vous pouvez vérifier que l’utilisateur peut se connecter à la messagerie unifiée Exchange en exécutant l’applet de commande [test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) à partir de Lync Server Management Shell :

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Si un second utilisateur a été activé pour la messagerie unifiée, vous pouvez utiliser l’applet de commande [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) pour vous assurer qu’il est en mesure de laisser un message vocal au premier utilisateur.

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

