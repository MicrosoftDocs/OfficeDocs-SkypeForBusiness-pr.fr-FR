---
title: 'Lync Server 2013 : Création des objets de contact pour la messagerie unifiée Exchange hébergée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0ce65ed39e67068fcd57aba1177ecb72f553ccf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="85d0e-102">Création des objets de contact pour la messagerie unifiée Exchange hébergée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85d0e-102">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85d0e-103">_**Dernière modification de la rubrique:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="85d0e-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="85d0e-104">La procédure suivante vous explique comment créer des objets de contact de standard automatique (AA) ou d’accès d’abonné (SA) pour la messagerie unifiée Exchange hébergée.</span><span class="sxs-lookup"><span data-stu-id="85d0e-104">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="85d0e-105">Pour plus d’informations, reportez-vous à la rubrique [gestion des objets de contact Exchange hébergés dans Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="85d0e-105">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="85d0e-106">Pour plus d’informations sur la configuration des objets de contact, consultez la documentation Lync Server Management Shell pour les applets de commande suivantes:</span><span class="sxs-lookup"><span data-stu-id="85d0e-106">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="85d0e-107">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="85d0e-107">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="85d0e-108">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="85d0e-108">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="85d0e-109">Pour que les objets de contact Lync Server 2013 puissent être activés pour la messagerie unifiée Exchange hébergée, une stratégie de messagerie vocale hébergée qui s’applique à ces derniers doit être déployée.</span><span class="sxs-lookup"><span data-stu-id="85d0e-109">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="85d0e-110">Pour plus d’informations, reportez-vous <A href="lync-server-2013-hosted-voice-mail-policies.md">à stratégies de messagerie vocale hébergées dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="85d0e-110">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="85d0e-111">Pour créer des objets de contact AA ou SA pour le UM Exchange hébergé</span><span class="sxs-lookup"><span data-stu-id="85d0e-111">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="85d0e-112">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="85d0e-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="85d0e-113">Exécutez l’applet de nouvelle applet de CsExUmContact pour créer des objets de contact requis pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="85d0e-113">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment.</span></span> <span data-ttu-id="85d0e-114">Par exemple, exécutez la commande suivante pour créer un objet de contact AA et son:</span><span class="sxs-lookup"><span data-stu-id="85d0e-114">For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="85d0e-115">Ces exemples définissent les paramètres suivants:</span><span class="sxs-lookup"><span data-stu-id="85d0e-115">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="85d0e-116">**SipAddress** spécifie l’adresse SIP de l’objet contact.</span><span class="sxs-lookup"><span data-stu-id="85d0e-116">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="85d0e-117">Il doit s’agir d’une adresse qui n’a pas encore été utilisée pour configurer un objet utilisateur ou contact dans les services de domaine Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="85d0e-117">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="85d0e-118">Cette valeur doit être au format "SIP:\<*SIP Address*\>" comme le montre l’exemple précédent.</span><span class="sxs-lookup"><span data-stu-id="85d0e-118">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="85d0e-119">**RegistrarPool** spécifie le nom de domaine complet (FQDN) du pool sur lequel le service de bureau d’enregistrement est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="85d0e-119">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="85d0e-120">Les objets de contact de MU Exchange ne peuvent pas être déplacés vers des pools qui font partie des déploiements Lync Server 2013 antérieurs à Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85d0e-120">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="85d0e-121">**UO** spécifie l’unité d’organisation Active Directory dans laquelle se trouve l’objet contact.</span><span class="sxs-lookup"><span data-stu-id="85d0e-121">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="85d0e-122">**DisplayNumber** spécifie le numéro de téléphone de l’objet contact.</span><span class="sxs-lookup"><span data-stu-id="85d0e-122">**DisplayNumber** specifies the telephone number of the contact object.</span></span> <span data-ttu-id="85d0e-123">Le numéro de téléphone de chaque objet contact doit être unique.</span><span class="sxs-lookup"><span data-stu-id="85d0e-123">The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="85d0e-124">\*\*\*\* Le standard automatique indique si l’objet contact est un standard automatique.</span><span class="sxs-lookup"><span data-stu-id="85d0e-124">**AutoAttendant** specifies whether the Contact object is an Auto Attendant.</span></span> <span data-ttu-id="85d0e-125">Le standard automatique propose un ensemble d’invites vocales permettant aux appelants de naviguer dans le système téléphonique et de joindre la partie qu’ils souhaitent contacter.</span><span class="sxs-lookup"><span data-stu-id="85d0e-125">Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact.</span></span> <span data-ttu-id="85d0e-126">La valeur **false** (valeur par défaut) pour ce paramètre indique un objet contact d’accès abonné.</span><span class="sxs-lookup"><span data-stu-id="85d0e-126">A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

