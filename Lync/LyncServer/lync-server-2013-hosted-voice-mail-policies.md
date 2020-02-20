---
title: 'Lync Server 2013 : stratégies de messagerie vocale hébergées'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16570331d0d7e154388c51ecb11be591bf3bbd05
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="4f96b-102">Stratégies de messagerie vocale hébergées dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f96b-102">Hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f96b-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4f96b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4f96b-104">Une *stratégie de messagerie vocale hébergée* fournit des informations à l’application de routage ExUM de Lync Server 2013 sur l’emplacement des appels pour les utilisateurs dont les boîtes aux lettres se trouvent sur un service Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="4f96b-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4f96b-105">Les stratégies de messagerie vocale hébergées ne sont requises que pour l’intégration de Lync Server 2013 avec la messagerie unifiée Exchange hébergée.</span><span class="sxs-lookup"><span data-stu-id="4f96b-105">Hosted voice mail policies are required only for Lync Server 2013 integration with hosted Exchange UM.</span></span> <span data-ttu-id="4f96b-106">Elles ne sont pas nécessaires dans le cas d’une intégration à la messagerie Exchange sur site.</span><span class="sxs-lookup"><span data-stu-id="4f96b-106">They are not needed for integration with on-premises Exchange UM.</span></span>



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a><span data-ttu-id="4f96b-107">Étendue des stratégies de messagerie vocale hébergée</span><span class="sxs-lookup"><span data-stu-id="4f96b-107">Hosted Voice Mail Policy Scope</span></span>

<span data-ttu-id="4f96b-p102">L’étendue des stratégies de messagerie vocale hébergée détermine le niveau hiérarchique d’application des stratégies. Vous pouvez configurer les stratégies de messagerie vocale hébergée avec les niveaux d’étendue suivants :</span><span class="sxs-lookup"><span data-stu-id="4f96b-p102">Hosted voice mail policy scope determines the hierarchical level at which the policy applies. You can configure hosted voice mail policies with the following scope levels:</span></span>

  - <span data-ttu-id="4f96b-110">La stratégie *globale* peut potentiellement affecter tous les utilisateurs dans le déploiement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f96b-110">The *global* policy can potentially affect all users in the Lync Server 2013 deployment.</span></span> <span data-ttu-id="4f96b-111">Si un utilisateur est activé pour l’accès à la messagerie unifiée Exchange hébergée, mais qu’aucune stratégie par utilisateur ne lui a été attribuée, et si aucune stratégie de site n’a été attribuée au site de l’utilisateur, la stratégie globale s’applique.</span><span class="sxs-lookup"><span data-stu-id="4f96b-111">If a user is enabled for hosted Exchange UM access and has not been assigned a per-user policy, and if a site policy has not been assigned to the user’s site, the global policy applies.</span></span> <span data-ttu-id="4f96b-112">La stratégie globale est installée avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f96b-112">The global policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="4f96b-113">Vous pouvez la modifier en fonction de vos besoins, mais pas la renommer ni la supprimer.</span><span class="sxs-lookup"><span data-stu-id="4f96b-113">You can modify it to meet your needs, but you cannot rename or delete it.</span></span>

  - <span data-ttu-id="4f96b-p104">Une stratégie de *site* peut concerner tous les utilisateurs qui sont hébergés sur le site pour lequel la stratégie est définie. Si aucune stratégie par utilisateur n’a été attribuée à un utilisateur qui est configuré pour l’accès à la messagerie unifiée Exchange hébergée, la stratégie de site s’applique.</span><span class="sxs-lookup"><span data-stu-id="4f96b-p104">A *site* policy can affect all users that are homed on the site for which the policy is defined. If a user is configured for hosted Exchange UM access and has not been assigned a per-user policy, the site policy applies.</span></span>

  - <span data-ttu-id="4f96b-p105">Une stratégie *par utilisateur* peut uniquement affecter des utilisateurs individuels ou des groupes. Pour appliquer une stratégie par utilisateur, vous devez l’attribuer explicitement à des utilisateurs individuels, des groupes et des objets contact.</span><span class="sxs-lookup"><span data-stu-id="4f96b-p105">A *per-user* policy can affect only individual users or groups. To enforce a per-user policy, you must explicitly assign the policy to individual users, groups, and contact objects.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4f96b-p106">Généralement, une seule stratégie de messagerie vocale hébergée est requise. Dans de nombreux cas, vous pouvez modifier la stratégie globale pour qu’elle réponde à vos besoins. Si vous déployez plusieurs stratégies de messagerie vocale hébergée, toutes ont une étendue par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4f96b-p106">In most cases, only one hosted voice mail policy is required. You can often modify the global policy to meet all your needs. If you deploy multiple hosted voice mail policies, all such policies have per-user scope.</span></span>



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a><span data-ttu-id="4f96b-121">Attributs des stratégies de messagerie vocale hébergée</span><span class="sxs-lookup"><span data-stu-id="4f96b-121">Hosted Voice Mail Policy Attributes</span></span>

<span data-ttu-id="4f96b-122">Une stratégie de messagerie vocale définit deux attributs que l’application de routage ExUM de Lync Server 2013 insère dans l’URI de requête d’un message d’invitation envoyé à l’implémentation de la messagerie unifiée Exchange hébergée :</span><span class="sxs-lookup"><span data-stu-id="4f96b-122">A voice mail policy defines two attributes that the Lync Server 2013 ExUM Routing application inserts in the request URI of an INVITE message that is sent to the hosted Exchange UM implementation:</span></span>

  - <span data-ttu-id="4f96b-123">**Destination :** Nom de domaine complet (FQDN) du service de messagerie unifiée Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="4f96b-123">**Destination:** The fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="4f96b-124">Cette valeur est utilisée par le serveur Edge Lync Server local à des fins de routage.</span><span class="sxs-lookup"><span data-stu-id="4f96b-124">This value is used by the on-premises Lync Server Edge Server for routing purposes.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f96b-125">Le nom de domaine complet pour Exchange Online est exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="4f96b-125">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

    
    </div>

  - <span data-ttu-id="4f96b-126">**Organisation :** Nom de domaine complet (FQDN) du client sur le service de messagerie unifiée Exchange hébergé qui héberge les boîtes aux lettres de vos utilisateurs Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f96b-126">**Organization:** The FQDN of the tenant on the hosted Exchange UM service that homes your Lync Server 2013 users’ mailboxes.</span></span> <span data-ttu-id="4f96b-127">Une stratégie de messagerie vocale peut contenir plusieurs organisations.</span><span class="sxs-lookup"><span data-stu-id="4f96b-127">A voice mail policy can contain multiple organizations.</span></span> <span data-ttu-id="4f96b-128">Si plusieurs organisations sont incluses dans la stratégie, cet attribut doit être une liste séparée par des virgules des clients Exchange Server qui hébergent vos boîtes aux lettres utilisateur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f96b-128">If more than one organization is included in the policy, this attribute must be a comma-separated list of the Exchange Server tenants that home your Lync Server 2013 user mailboxes.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4f96b-p109">L’administrateur client de votre service de messagerie unifiée Exchange hébergé fournit les valeurs nécessaires pour vos paramètres d’attribut de destination et d’organisation. Pour configurer votre stratégie, vous devez exécuter la cmdlet New-CsHostedVoicemailPolicy ou utiliser Set-CsHostedVoicemailPolicy pour modifier une stratégie existante (la stratégie globale, par exemple).</span><span class="sxs-lookup"><span data-stu-id="4f96b-p109">The tenant administrator of your hosted Exchange UM service will provide the necessary values for your Destination and Organization attribute settings. To configure your policy, you must run the New-CsHostedVoicemailPolicy cmdlet or use the Set-CsHostedVoicemailPolicy cmdlet to modify one that exists (for example, the global policy).</span></span>



</div>

<span data-ttu-id="4f96b-131">Pour plus d’informations sur la gestion des stratégies de messagerie vocale hébergée, reportez-vous à la documentation Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="4f96b-131">For details about managing hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="4f96b-132">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="4f96b-132">New-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="4f96b-133">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="4f96b-133">Set-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="4f96b-134">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="4f96b-134">Get-CsHostedVoicemailPolicy</span></span>

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a><span data-ttu-id="4f96b-135">Attribution de stratégies de messagerie vocale par utilisateur</span><span class="sxs-lookup"><span data-stu-id="4f96b-135">Per-User Voice Mail Policy Assignment</span></span>

<span data-ttu-id="4f96b-p110">Si votre stratégie de messagerie vocale hébergée est définie avec une étendue par utilisateur, vous devez l’attribuer explicitement. Vous pouvez exécute la cmdlet Grant-CsHostedVoicemailPolicy pour attribuer la stratégie à des utilisateurs individuels ou des groupes.</span><span class="sxs-lookup"><span data-stu-id="4f96b-p110">If your hosted voice mail policy is defined with per-user scope, you must explicitly assign it. You can run the Grant-CsHostedVoicemailPolicy cmdlet to assign the policy to individual users or groups.</span></span>

<span data-ttu-id="4f96b-138">Pour plus d’informations sur l’attribution ou la suppression d’une stratégie de messagerie vocale hébergée par utilisateur, reportez-vous à la documentation Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="4f96b-138">For details about assigning or removing a per-user hosted voice mail policy, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="4f96b-139">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="4f96b-139">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="4f96b-140">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="4f96b-140">Remove-CsHostedVoicemailPolicy</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

