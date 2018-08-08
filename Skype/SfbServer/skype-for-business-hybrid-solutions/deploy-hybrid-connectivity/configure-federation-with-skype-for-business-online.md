---
title: Configuration de la fédération avec Skype Entreprise Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/12/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
description: 'Résumé : Découvrez comment configurer l’interopérabilité entre votre déploiement sur site et les Skype pour Business en ligne.'
ms.openlocfilehash: 6a48e3cc579fd3827cc95f7f36d0c637d540ed56
ms.sourcegitcommit: 8a34b5f0295fc6059852dab6971429fda4d30b67
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2018
ms.locfileid: "20176118"
---
# <a name="configure-federation-with-skype-for-business-online"></a><span data-ttu-id="c94de-103">Configuration de la fédération avec Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="c94de-103">Configure federation with Skype for Business Online</span></span>
 
<span data-ttu-id="c94de-104">**Résumé :** Découvrez comment configurer l’interopérabilité entre votre déploiement sur site et les Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="c94de-104">**Summary:** Learn how to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>
  
<span data-ttu-id="c94de-105">Suivez les étapes décrites dans cette section pour configurer l’interopérabilité entre votre déploiement sur site et les Skype pour Business en ligne.</span><span class="sxs-lookup"><span data-stu-id="c94de-105">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="c94de-106">Configurer votre service de périphérie sur site pour la fédération avec Skype pour Business Online</span><span class="sxs-lookup"><span data-stu-id="c94de-106">Configure your on-premises Edge service for federation with Skype for Business Online</span></span>

<span data-ttu-id="c94de-107">La fédération permet aux utilisateurs de votre déploiement local de communiquer avec des utilisateurs Office 365 dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c94de-107">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="c94de-108">Pour configurer la fédération, exécutez les cmdlets suivantes dans le Skype pour Business Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="c94de-108">To configure federation, run the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="c94de-109">Configurer votre Skype pour Business Online client pour un espace d’adressage SIP partagé</span><span class="sxs-lookup"><span data-stu-id="c94de-109">Configure your Skype for Business Online tenant for a shared SIP address space</span></span>

<span data-ttu-id="c94de-110">Une adresse SIP (Session Initiation Protocol) est un identificateur unique pour chaque utilisateur d’un réseau, semblable à un numéro de téléphone ou à une adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="c94de-110">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="c94de-111">Avant d’essayer de déplacer les utilisateurs locaux vers Skype pour Business Online, vous devez configurer votre client Office 365 pour partager l’espace d’adressage partagé protocole SIP (Session Initiation) avec votre déploiement sur site.</span><span class="sxs-lookup"><span data-stu-id="c94de-111">Before you try to move users from on-premises to Skype for Business Online, you'll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="c94de-112">S’il n’est pas configuré, le message d’erreur ci-dessous peut s’afficher :</span><span class="sxs-lookup"><span data-stu-id="c94de-112">If this is not configured, you may see the following error message:</span></span>
  
<span data-ttu-id="c94de-113">Move-CsUser : HostedMigration tolérance : Error=(510), Description = (client de cet utilisateur n’est pas activé pour l’espace d’adressage sip partagé).</span><span class="sxs-lookup"><span data-stu-id="c94de-113">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user's tenant is not enabled for shared sip address space.)</span></span>
  
<span data-ttu-id="c94de-114">Pour configurer un espace d’adressage SIP partagé, établir une session PowerShell distante avec Skype pour Business Online, puis exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c94de-114">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="c94de-115">L’attribut SharedSipAddressSpace doit demeurer défini sur True jusqu’à ce que le déplacement vers Online soit finalisé et qu’aucun utilisateur ne soit hébergé en local.</span><span class="sxs-lookup"><span data-stu-id="c94de-115">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="c94de-116">Pour établir une session PowerShell distante avec Skype pour Business Online, vous devez d’abord installer le Skype pour module connecteur Business en ligne pour Windows PowerShell, vous pouvez obtenir ici : [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="c94de-116">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="c94de-117">Après avoir installé le module, vous pouvez établir une session distante avec les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="c94de-117">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```
Import-Module SkypeOnlineConnector
```

```
$cred = Get-Credential
```

```
$CSSession = New-CsOnlineSession -Credential $cred
```

```
Import-PSSession $CSSession -AllowClobber
```

<span data-ttu-id="c94de-118">Pour plus d’informations sur l’utilisation de PowerShell avec Skype pour Business Online, voir [configurer votre ordinateur pour Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c94de-118">For more information about using PowerShell with Skype for Business Online, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

  
## <a name="see-also"></a><span data-ttu-id="c94de-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c94de-119">See also</span></span>

[<span data-ttu-id="c94de-120">Nouvelle-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="c94de-120">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)