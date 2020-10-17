---
title: 'Lync Server 2013 : configuration de la découverte automatique pour les déploiements hybrides'
description: 'Lync Server 2013 : configuration de la découverte automatique pour les déploiements hybrides.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6797e3f6b77e3016f6cef87f2a930f5a7c1fce6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562490"
---
# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a><span data-ttu-id="ce100-103">Configuration de la découverte automatique dans Lync Server 2013 pour les déploiements hybrides</span><span class="sxs-lookup"><span data-stu-id="ce100-103">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce100-104">_**Dernière modification de la rubrique :** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="ce100-104">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="ce100-105">Les déploiements hybrides sont des configurations qui utilisent à la fois le service Cloud de Microsoft Lync Online et le déploiement local.</span><span class="sxs-lookup"><span data-stu-id="ce100-105">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="ce100-106">Dans ce type de configuration, le service de découverte automatique doit être capable de localiser l’emplacement actuel de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ce100-106">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="ce100-107">Cela signifie que la découverte automatique facilite la recherche du compte d’utilisateur et l’emplacement du serveur qui héberge le compte de l’utilisateur, qu’il se trouve dans le déploiement local ou dans le déploiement Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ce100-107">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="ce100-108">Par exemple, si un compte d’utilisateur est hébergé sur un serveur dans Lync Online, la tentative de localisation de l’utilisateur se déroule comme suit, dans un processus appelé « *détectabilité*» :</span><span class="sxs-lookup"><span data-stu-id="ce100-108">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="ce100-109">L’utilisateur lance une tentative de connexion au déploiement sur site, **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="ce100-109">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="ce100-110">La tentative est envoyée à lyncdiscover.contoso.com, le nom de DNS associé au service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="ce100-110">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="ce100-111">La découverte automatique fait référence au pool de serveurs d’inscriptions supposés au niveau du déploiement contoso.com sur site et reçoit des informations sur le serveur d’accueil réel de l’utilisateur hébergé dans Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ce100-111">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="ce100-112">Le service de découverte automatique envoie ensuite à l’utilisateur une référence vers le service de découverte automatique en ligne **lync.com**.</span><span class="sxs-lookup"><span data-stu-id="ce100-112">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="ce100-113">L’utilisateur lance une tentative de connexion vers le service de découverte automatique en ligne lync.com et peut localiser le compte et le serveur d’hébergement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ce100-113">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="ce100-114">Pour permettre aux clients de découvrir le déploiement où se trouve le serveur d’accueil de l’utilisateur, vous devez configurer le service de découverte automatique avec une nouvelle URL (Uniform Resource Locator).</span><span class="sxs-lookup"><span data-stu-id="ce100-114">To enable clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="ce100-115">Pour configurer le service de découverte automatique, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ce100-115">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="ce100-116">Configuration du service de découverte automatique pour les déploiements hybrides</span><span class="sxs-lookup"><span data-stu-id="ce100-116">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="ce100-117">Dans la rubrique [configuration du service de découverte automatique requise pour Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), vous utilisez Get-CsHostingProvider pour récupérer la valeur de l’attribut ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="ce100-117">In the topic, [Autodiscover service requirements for Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), you use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="ce100-118">À partir de Lync Server Management Shell, tapez</span><span class="sxs-lookup"><span data-stu-id="ce100-118">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    <span data-ttu-id="ce100-119">Où \[ Identity \] est remplacé par le nom de domaine de l’espace d’adressage SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="ce100-119">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ce100-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ce100-120">See Also</span></span>


[<span data-ttu-id="ce100-121">Get-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="ce100-121">Get-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[<span data-ttu-id="ce100-122">Set-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="ce100-122">Set-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

