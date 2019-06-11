---
title: 'Lync Server 2013: configuration de la messagerie unifiée Microsoft Exchange Server 2013 pour Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e1d2bac84183e6cc274d6bb297c17401b3ff7f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a><span data-ttu-id="4fcc1-102">Configuration de la messagerie unifiée Microsoft Exchange Server 2013 pour Microsoft Lync Server 2013 la messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="4fcc1-102">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fcc1-103">_**Dernière modification de la rubrique:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="4fcc1-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="4fcc1-104">Microsoft Lync Server 2013 vous permet d’utiliser les messages vocaux stockés dans Microsoft Exchange Server 2013. ces messages vocaux apparaissent alors sous forme de courriers dans les boîtes de réception de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4fcc1-104">Microsoft Lync Server 2013 enables you to have voicemail messages stored in Microsoft Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> <span data-ttu-id="4fcc1-105">Cette fonctionnalité est également disponible dans les éditions 2010 de Lync Server et Exchange; Toutefois, le processus de configuration de ce «message unifié» a été simplifié dans les éditions 2013 grâce à l’introduction du composant routeur de messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="4fcc1-105">This capability was also found in the 2010 editions of Lync Server and Exchange; however, the process of configuring this "unified messaging" has been simplified in the 2013 editions thanks to the introduction of the UM Call Router component.</span></span> <span data-ttu-id="4fcc1-106">Ce composant est installé sur le serveur d’accès au client Exchange 2013, et tous les appels à la messagerie unifiée Exchange (par exemple, un message vocal) sont d’abord acheminés via le routeur d’appel, puis redirigés vers le serveur de boîte aux lettres approprié.</span><span class="sxs-lookup"><span data-stu-id="4fcc1-106">This component is installed on the Exchange 2013 Client Access server, and all calls to Exchange unified messaging (such as a voicemail) are first routed through the Call Router and then are redirected to the appropriate Mailbox server.</span></span>

<span data-ttu-id="4fcc1-107">Si vous avez déjà configuré l’authentification de serveur à serveur entre Lync Server 2013 et Exchange 2013, vous pouvez configurer la messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="4fcc1-107">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you are ready to setup unified messaging.</span></span> <span data-ttu-id="4fcc1-108">Pour ce faire, vous devez commencer par créer et affecter un nouveau plan de numérotation de messagerie unifiée sur votre serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="4fcc1-108">To do so, you must first create and assign a new unified messaging dial plan on your Exchange server.</span></span> <span data-ttu-id="4fcc1-109">Par exemple, ces deux commandes (exécutées à partir d’Exchange Management Shell) configurent un nouveau plan de numérotation à 3 chiffres pour Exchange:</span><span class="sxs-lookup"><span data-stu-id="4fcc1-109">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="4fcc1-p103">Dans la première commande de cet exemple, le paramètre VoIPSecurity et la valeur « Secured » du paramètre indiquent que le canal de signalisation est chiffré à l’aide du protocole TLS (Transport Layer Security). La valeur « SipName » de URIType indique que les messages seront envoyés et reçus à l’aide du protocole SIP et la valeur 1 de CountryOrRegionCode signifie que le plan de numérotation s’applique aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="4fcc1-p103">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS). The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>

<span data-ttu-id="4fcc1-112">Dans la seconde commande, la valeur transmise au paramètre ConfiguredInCountryOrRegionGroups indique quels groupes régionaux peuvent être utilisés avec ce plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="4fcc1-112">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="4fcc1-113">La valeur de paramètre «Anywhere\*,\*,\*» définit les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="4fcc1-113">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>

  - <span data-ttu-id="4fcc1-114">Nom du groupe (« Anywhere »)</span><span class="sxs-lookup"><span data-stu-id="4fcc1-114">Group name ("Anywhere")</span></span>

  - <span data-ttu-id="4fcc1-115">AllowedNumberString (\*un caractère générique indiquant qu’une chaîne numérique est autorisée)</span><span class="sxs-lookup"><span data-stu-id="4fcc1-115">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>

  - <span data-ttu-id="4fcc1-116">DialNumberString (\*un caractère générique indiquant qu’un numéro composé est autorisé)</span><span class="sxs-lookup"><span data-stu-id="4fcc1-116">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>

  - <span data-ttu-id="4fcc1-117">TextComment (\*un caractère générique indiquant qu’une commande de texte est autorisée)</span><span class="sxs-lookup"><span data-stu-id="4fcc1-117">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4fcc1-118">Quand vous créez un nouveau plan de numérotation, vous créez aussi une stratégie de boîte aux lettres par défaut.</span><span class="sxs-lookup"><span data-stu-id="4fcc1-118">Creating a new dial plan will also create a Default Mailbox Policy.</span></span>



</div>

<span data-ttu-id="4fcc1-119">Après avoir créé et configuré le nouveau plan de numérotation, vous devez ajouter le nouveau plan de numérotation à votre serveur de messagerie unifiée, puis modifier le mode de démarrage de ce serveur. en particulier, vous devez définir le mode de démarrage sur «Dual».</span><span class="sxs-lookup"><span data-stu-id="4fcc1-119">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="4fcc1-120">Vous pouvez effectuer les deux tâches suivantes à partir d’Exchange Management Shell:</span><span class="sxs-lookup"><span data-stu-id="4fcc1-120">You can perform both of these tasks from within the Exchange Management Shell:</span></span>

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

<span data-ttu-id="4fcc1-121">Après avoir configuré le serveur de messagerie unifiée, vous devez exécuter l’applet de certification Enable-ExchangeCertificate pour vous assurer que votre certificat Exchange est appliqué au service de messagerie unifiée:</span><span class="sxs-lookup"><span data-stu-id="4fcc1-121">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

<span data-ttu-id="4fcc1-p106">Une fois le certificat correctement affecté, vous devez arrêter et redémarrer le service MsExchangeUM sur le serveur de messagerie unifiée. Ce service doit être arrêté et redémarré à chaque fois que vous modifiez le mode de démarrage.</span><span class="sxs-lookup"><span data-stu-id="4fcc1-p106">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>

<span data-ttu-id="4fcc1-124">Une fois la configuration du serveur de messagerie unifiée terminée, vous pouvez passer à la configuration du routeur d’appels de la messagerie unifiée :</span><span class="sxs-lookup"><span data-stu-id="4fcc1-124">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

<span data-ttu-id="4fcc1-125">Comme le mode de démarrage a été modifié, vous devez arrêter et redémarrer le service MsExchangeUMCR sur l’ordinateur qui héberge le routeur d’appels de la messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="4fcc1-125">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>

<span data-ttu-id="4fcc1-p107">Pour terminer la configuration de la messagerie unifiée, vous devez ensuite créer une stratégie de boîte aux lettres de la messagerie unifiée et utiliser cette stratégie afin d’activer les utilisateurs pour la messagerie unifiée. Vous pouvez créer une stratégie de boîte aux lettres à l’aide d’une commande similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="4fcc1-p107">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="4fcc1-128">Vous pouvez également activer un utilisateur pour la messagerie unifiée en utilisant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="4fcc1-128">And you can enable a user for unified messaging by using a command similar to this:</span></span>

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

<span data-ttu-id="4fcc1-p108">Dans la commande précédente, le paramètre Extensions représente le numéro de poste de l’utilisateur. Dans cet exemple, le numéro de poste de l’utilisateur est le 100.</span><span class="sxs-lookup"><span data-stu-id="4fcc1-p108">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>

<span data-ttu-id="4fcc1-131">Une fois sa boîte aux lettres activée, l’utilisateur kenmyer@litwareinc.com doit être en mesure d’utiliser la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="4fcc1-131">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="4fcc1-132">Vous pouvez vérifier que l’utilisateur peut se connecter à la messagerie unifiée Exchange en exécutant l’applet de connexion [test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) à partir de Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="4fcc1-132">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet from within the Lync Server Management Shell:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="4fcc1-133">Si un second utilisateur a été activé pour la messagerie unifiée, vous pouvez utiliser l’applet de commande [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) pour vous assurer qu’il est en mesure de laisser un message vocal au premier utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4fcc1-133">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

