---
title: 'Lync Server 2013 : configuration de la découverte automatique pour les déploiements hybrides'
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
ms.openlocfilehash: 8924194d89eafb75c06ff78ed3b765699e36b196
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a><span data-ttu-id="a86b0-102">Configuration de la découverte automatique dans Lync Server 2013 pour les déploiements hybrides</span><span class="sxs-lookup"><span data-stu-id="a86b0-102">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a86b0-103">_**Dernière modification de la rubrique :** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="a86b0-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="a86b0-104">Les déploiements hybrides sont des configurations utilisant à la fois le service de Cloud Computing Microsoft Lync Online et le déploiement local.</span><span class="sxs-lookup"><span data-stu-id="a86b0-104">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="a86b0-105">Dans ce type de configuration, le service de découverte automatique doit être en mesure de localiser l’emplacement où l’utilisateur se trouve réellement.</span><span class="sxs-lookup"><span data-stu-id="a86b0-105">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="a86b0-106">Par exemple, la fonction de découverte automatique facilite la recherche du compte d’utilisateur et l’emplacement du serveur qui héberge le compte de l’utilisateur, même s’il se trouve dans le déploiement local ou dans le déploiement Lync Online.</span><span class="sxs-lookup"><span data-stu-id="a86b0-106">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="a86b0-107">Par exemple, si le compte d’un utilisateur est hébergé sur un serveur dans Lync Online, la tentative de localisation de l’utilisateur se déroule comme suit, dans un processus connu sous le nom de *découverte*:</span><span class="sxs-lookup"><span data-stu-id="a86b0-107">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="a86b0-108">Un utilisateur commence une tentative de connexion à un déploiement local, **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="a86b0-108">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="a86b0-109">La tentative est envoyée à lyncdiscover.contoso.com, le nom DNS associé au service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="a86b0-109">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="a86b0-110">La découverte automatique fait référence au pool d’inscriptions présumées au niveau du déploiement local de contoso.com et dispose d’informations sur le véritable serveur d’accueil hébergé dans Lync Online.</span><span class="sxs-lookup"><span data-stu-id="a86b0-110">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="a86b0-111">La découverte automatique envoie ensuite à l’utilisateur une référence au service de découverte automatique **Lync.com** online.</span><span class="sxs-lookup"><span data-stu-id="a86b0-111">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="a86b0-112">L’utilisateur entame une tentative de connexion au service de découverte automatique lync.com Online et est en mesure de trouver le compte de l’utilisateur et le serveur associé de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a86b0-112">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="a86b0-113">Pour permettre aux clients de découvrir le déploiement sur lequel se trouve le serveur associé de l’utilisateur, vous devez configurer le service de découverte automatique à l’aide d’une nouvelle URL (Uniform Resource Locator).</span><span class="sxs-lookup"><span data-stu-id="a86b0-113">To enable clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="a86b0-114">Procédez comme suit pour configurer le service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="a86b0-114">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="a86b0-115">Configuration de la découverte automatique pour les déploiements hybrides</span><span class="sxs-lookup"><span data-stu-id="a86b0-115">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="a86b0-116">Dans la rubrique [Configuration requise pour le service de découverte automatique pour Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), vous utilisez Get-CsHostingProvider pour récupérer la valeur de l’attribut ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="a86b0-116">In the topic, [Autodiscover service requirements for Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), you use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="a86b0-117">À partir de Lync Server Management Shell, tapez</span><span class="sxs-lookup"><span data-stu-id="a86b0-117">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    <span data-ttu-id="a86b0-118">Où \[Identity\] est remplacé par le nom de domaine de l’espace d’adressage SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="a86b0-118">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a86b0-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a86b0-119">See Also</span></span>


[<span data-ttu-id="a86b0-120">Get-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="a86b0-120">Get-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[<span data-ttu-id="a86b0-121">Set-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="a86b0-121">Set-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

