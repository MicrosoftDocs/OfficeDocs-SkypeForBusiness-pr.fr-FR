---
title: 'Lync Server 2013: configuration de la Fédération avec Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d690b21614ec416d82834761772cee05ee16f26e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a><span data-ttu-id="ce6b2-102">Configurer la Fédération de Lync Server 2013 avec Lync Online</span><span class="sxs-lookup"><span data-stu-id="ce6b2-102">Configure federation of Lync Server 2013 with Lync Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce6b2-103">_**Dernière modification de la rubrique:** 2016-08-15_</span><span class="sxs-lookup"><span data-stu-id="ce6b2-103">_**Topic Last Modified:** 2016-08-15_</span></span>

<span data-ttu-id="ce6b2-104">Suivez les étapes décrites dans cette section pour configurer l’interopérabilité entre votre déploiement local et Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="ce6b2-104">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="ce6b2-105">Configurer votre service Edge local pour la Fédération avec Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="ce6b2-105">Configure Your On-Premises Edge Service for Federation with Skype for Business Online</span></span>

<span data-ttu-id="ce6b2-106">La Fédération permet aux utilisateurs de votre déploiement local de communiquer avec les utilisateurs d’Office 365 au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ce6b2-106">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="ce6b2-107">Pour configurer la Fédération, exécutez les applets de commande suivantes:</span><span class="sxs-lookup"><span data-stu-id="ce6b2-107">To configure federation, run the following cmdlets:</span></span>

   ```
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="ce6b2-108">Configurer votre client Skype entreprise Online pour un espace d’adressage SIP partagé</span><span class="sxs-lookup"><span data-stu-id="ce6b2-108">Configure Your Skype for Business Online Tenant for a Shared SIP Address Space</span></span>

<span data-ttu-id="ce6b2-109">Une adresse SIP (Session Initiation Protocol) est un identificateur unique pour chaque utilisateur d’un réseau, semblable à un numéro de téléphone ou à une adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="ce6b2-109">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="ce6b2-110">Avant d’essayer de déplacer des utilisateurs de Lync en local vers Skype entreprise Online, vous devez configurer votre client Office 365 pour partager l’espace d’adressage SIP (Session Initiation Protocol) avec votre déploiement local.</span><span class="sxs-lookup"><span data-stu-id="ce6b2-110">Before you try to move Lync users from on-premises to Skype for Business Online, you’ll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="ce6b2-111">S’il n’est pas configuré, le message d’erreur ci-dessous peut s’afficher :</span><span class="sxs-lookup"><span data-stu-id="ce6b2-111">If this is not configured, you may see the following error message:</span></span>

<span data-ttu-id="ce6b2-112">Move-CsUser : HostedMigration fault: Error=(510), Description=(Le client de cet utilisateur n’est pas activé pour l’espace d’adressage SIP partagé.)</span><span class="sxs-lookup"><span data-stu-id="ce6b2-112">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user’s tenant is not enabled for shared sip address space.)</span></span>

<span data-ttu-id="ce6b2-113">Pour configurer un espace d’adressage SIP partagé, établissez une session PowerShell distante avec Skype entreprise Online, puis exécutez l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="ce6b2-113">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>

    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true

<span data-ttu-id="ce6b2-114">Pour établir une session PowerShell distante avec Skype entreprise Online, vous devez d’abord installer le module Skype entreprise Online pour Windows PowerShell, que vous pouvez consulter: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span><span class="sxs-lookup"><span data-stu-id="ce6b2-114">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online module for Windows PowerShell, which you can get here: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>

<span data-ttu-id="ce6b2-115">Après avoir installé le module, vous pouvez établir une session distante avec les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="ce6b2-115">After you install the module, you can establish a remote session with the following cmdlets:</span></span>

   ```
    Import-Module LyncOnlineConnector
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

<span data-ttu-id="ce6b2-116">Pour plus d’informations sur l’établissement d’une session PowerShell distante avec Skype entreprise Online, reportez-vous à la rubrique [connexion à Skype entreprise Online à l’aide de Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="ce6b2-116">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Skype for Business Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

<span data-ttu-id="ce6b2-117">Pour plus d’informations sur l’utilisation du module PowerShell de Skype entreprise Online, reportez-vous à la rubrique [utilisation de Windows PowerShell pour gérer Skype entreprise Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="ce6b2-117">For more information about using the Skype for Business Online PowerShell module, see [Using Windows PowerShell to manage Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ce6b2-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ce6b2-118">See Also</span></span>


[<span data-ttu-id="ce6b2-119">Nouveau-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="ce6b2-119">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

