---
title: Configuration de la messagerie unifiée d’Exchange Server pour la messagerie vocale de Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/19/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Résumé : Configuration messagerie unifiée d’Exchange Server pour Skype pour la messagerie vocale Business Server.'
ms.openlocfilehash: 9f4cb3dcd43d8f6300a5fbe38bd37c40d48e8273
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-2015-voice-mail"></a><span data-ttu-id="91637-103">Configuration de la messagerie unifiée d’Exchange Server pour la messagerie vocale de Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="91637-103">Configure Exchange Server Unified Messaging for Skype for Business Server 2015 voice mail</span></span>
 
<span data-ttu-id="91637-104">**Résumé :** Configurer la messagerie unifiée Exchange Server pour Skype pour la messagerie vocale Business Server.</span><span class="sxs-lookup"><span data-stu-id="91637-104">**Summary:** Configure Exchange Server Unified Messaging for Skype for Business Server voice mail.</span></span>
  
<span data-ttu-id="91637-105">Skype pour Business Server 2015 vous permet d’avoir des messages vocaux stockées dans Exchange Server 2016 ou 2013 d’Exchange Server ; les messages de la messagerie vocale seront affiche alors en tant que messages électroniques dans les boîtes de réception de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="91637-105">Skype for Business Server 2015 enables you to have voicemail messages stored in Exchange Server 2016 or Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> 
  
<span data-ttu-id="91637-106">Si vous avez déjà configuré l’authentification de serveur à serveur entre Skype pour Business Server 2015 et 2016 d’Exchange Server ou Exchange Server 2013, vous êtes prêt à configurer la messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="91637-106">If you have already configured server-to-server authentication between Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you are ready to setup unified messaging.</span></span> <span data-ttu-id="91637-107">Pour ce faire, vous devez tout d’abord créer et affecter un nouveau plan de numérotation messagerie unifiée sur votre Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="91637-107">To do so, you must first create and assign a new unified messaging dial plan on your Exchange Server.</span></span> <span data-ttu-id="91637-108">Par exemple, ces deux commandes (exécuter à partir d’Exchange Management Shell) configurer un nouveau plan de numérotation de 3 chiffres pour Exchange :</span><span class="sxs-lookup"><span data-stu-id="91637-108">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="91637-p102">Dans la première commande de cet exemple, le paramètre VoIPSecurity et la valeur « Secured » du paramètre indiquent que le canal de signalisation est chiffré à l’aide du protocole TLS (Transport Layer Security). La valeur « SipName » de URIType indique que les messages seront envoyés et reçus à l’aide du protocole SIP et la valeur 1 de CountryOrRegionCode signifie que le plan de numérotation s’applique aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="91637-p102">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS). The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>
  
<span data-ttu-id="91637-111">Dans la seconde commande, la valeur transmise au paramètre ConfiguredInCountryOrRegionGroups indique quels groupes régionaux peuvent être utilisés avec ce plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="91637-111">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="91637-112">La valeur du paramètre « n’importe où,\*,\*,\*"définit les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="91637-112">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>
  
- <span data-ttu-id="91637-113">Nom du groupe (« Anywhere »)</span><span class="sxs-lookup"><span data-stu-id="91637-113">Group name ("Anywhere")</span></span>
    
- <span data-ttu-id="91637-114">AllowedNumberString (\*, un caractère générique qui indique que n’importe quelle chaîne numérique est autorisée)</span><span class="sxs-lookup"><span data-stu-id="91637-114">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>
    
- <span data-ttu-id="91637-115">DialNumberString (\*, un caractère générique qui indique que tous les numéros composés sont autorisée)</span><span class="sxs-lookup"><span data-stu-id="91637-115">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>
    
- <span data-ttu-id="91637-116">TextComment (\*, un caractère générique indiquant qu’une commande de texte est autorisée)</span><span class="sxs-lookup"><span data-stu-id="91637-116">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>
    
> [!NOTE]
> <span data-ttu-id="91637-117">Quand vous créez un nouveau plan de numérotation, vous créez aussi une stratégie de boîte aux lettres par défaut.</span><span class="sxs-lookup"><span data-stu-id="91637-117">Creating a new dial plan will also create a Default Mailbox Policy.</span></span> 
  
<span data-ttu-id="91637-118">Après la création et la configuration du nouveau plan de numérotation, vous devez ajouter le nouveau plan à votre serveur de messagerie unifiée de composer et puis modifier le mode de démarrage du serveur ; en particulier, vous devez définir le mode de démarrage « Double ».</span><span class="sxs-lookup"><span data-stu-id="91637-118">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="91637-119">Vous pouvez effectuer ces tâches à partir d’Exchange Management Shell :</span><span class="sxs-lookup"><span data-stu-id="91637-119">You can perform both of these tasks from within the Exchange Management Shell:</span></span>
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

<span data-ttu-id="91637-120">Après avoir configuré le serveur de messagerie unifié vous devez ensuite exécuter l’applet de commande Enable-ExchangeCertificate pour vous assurer que votre certificat Exchange est appliqué au service de messagerie unifié :</span><span class="sxs-lookup"><span data-stu-id="91637-120">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

<span data-ttu-id="91637-p105">Une fois le certificat correctement affecté, vous devez arrêter et redémarrer le service MsExchangeUM sur le serveur de messagerie unifiée. Ce service doit être arrêté et redémarré à chaque fois que vous modifiez le mode de démarrage.</span><span class="sxs-lookup"><span data-stu-id="91637-p105">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>
  
<span data-ttu-id="91637-123">Une fois la configuration du serveur de messagerie unifiée terminée, vous pouvez passer à la configuration du routeur d’appels de la messagerie unifiée :</span><span class="sxs-lookup"><span data-stu-id="91637-123">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

<span data-ttu-id="91637-124">Comme le mode de démarrage a été modifié, vous devez arrêter et redémarrer le service MsExchangeUMCR sur l’ordinateur qui héberge le routeur d’appels de la messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="91637-124">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>
  
<span data-ttu-id="91637-p106">Pour terminer la configuration de la messagerie unifiée, vous devez ensuite créer une stratégie de boîte aux lettres de la messagerie unifiée et utiliser cette stratégie afin d’activer les utilisateurs pour la messagerie unifiée. Vous pouvez créer une stratégie de boîte aux lettres à l’aide d’une commande similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="91637-p106">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="91637-127">Vous pouvez également activer un utilisateur pour la messagerie unifiée en utilisant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="91637-127">And you can enable a user for unified messaging by using a command similar to this:</span></span>
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

<span data-ttu-id="91637-p107">Dans la commande précédente, le paramètre Extensions représente le numéro de poste de l’utilisateur. Dans cet exemple, le numéro de poste de l’utilisateur est le 100.</span><span class="sxs-lookup"><span data-stu-id="91637-p107">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>
  
<span data-ttu-id="91637-130">Une fois sa boîte aux lettres activée, l’utilisateur kenmyer@litwareinc.com doit être en mesure d’utiliser la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="91637-130">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="91637-131">Vous pouvez vérifier que l’utilisateur peut se connecter à la messagerie unifiée Exchange en exécutant l’applet de commande [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) à partir de la Skype pour Business Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="91637-131">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet from within the Skype for Business Server Management Shell:</span></span>
  
```
$credential = Get-Credential "litwareinc\kenmyer"

Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

<span data-ttu-id="91637-132">Si vous disposez d’un second utilisateur, qui a été activé pour la messagerie unifiée, vous pouvez utiliser l’applet de commande [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) pour vérifier que le second utilisateur peut laisser un message de messagerie vocale pour le premier utilisateur.</span><span class="sxs-lookup"><span data-stu-id="91637-132">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>
  
```
$credential = Get-Credential "litwareinc\pilar"

Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```


