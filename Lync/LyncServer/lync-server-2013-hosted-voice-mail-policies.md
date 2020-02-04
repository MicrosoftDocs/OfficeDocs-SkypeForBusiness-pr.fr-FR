---
title: 'Lync Server 2013 : Stratégies de messagerie vocale hébergées'
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
ms.openlocfilehash: 811f975868dad7bc0fcf6d5a2867ca2f3b81cd59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="81b87-102">Stratégies de messagerie vocale hébergées dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81b87-102">Hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81b87-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="81b87-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="81b87-104">Une *stratégie de messagerie vocale hébergée* fournit des informations à l’application de routage de l’ExUM de Lync Server 2013 sur l’emplacement de routage des appels pour les utilisateurs dont la boîte aux lettres est située sur un service Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="81b87-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81b87-105">Les stratégies de messagerie vocale hébergées sont uniquement requises pour l’intégration de Lync Server 2013 à la messagerie unifiée Exchange hébergée.</span><span class="sxs-lookup"><span data-stu-id="81b87-105">Hosted voice mail policies are required only for Lync Server 2013 integration with hosted Exchange UM.</span></span> <span data-ttu-id="81b87-106">Elles ne sont pas nécessaires pour l’intégration à la messagerie unifiée Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="81b87-106">They are not needed for integration with on-premises Exchange UM.</span></span>



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a><span data-ttu-id="81b87-107">Étendue de la stratégie de messagerie vocale hébergée</span><span class="sxs-lookup"><span data-stu-id="81b87-107">Hosted Voice Mail Policy Scope</span></span>

<span data-ttu-id="81b87-108">L’étendue de la stratégie de messagerie vocale hébergée détermine le niveau hiérarchique auquel la stratégie s’applique.</span><span class="sxs-lookup"><span data-stu-id="81b87-108">Hosted voice mail policy scope determines the hierarchical level at which the policy applies.</span></span> <span data-ttu-id="81b87-109">Vous pouvez configurer des stratégies de messagerie vocale hébergées avec les niveaux d’étendue suivants :</span><span class="sxs-lookup"><span data-stu-id="81b87-109">You can configure hosted voice mail policies with the following scope levels:</span></span>

  - <span data-ttu-id="81b87-110">La stratégie *globale* peut potentiellement affecter tous les utilisateurs dans le déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81b87-110">The *global* policy can potentially affect all users in the Lync Server 2013 deployment.</span></span> <span data-ttu-id="81b87-111">Si un utilisateur est autorisé à utiliser l’accès à la messagerie unifiée Exchange hébergé sans avoir reçu une stratégie individuelle et qu’aucune stratégie de site ne lui a été attribuée, la politique globale s’applique.</span><span class="sxs-lookup"><span data-stu-id="81b87-111">If a user is enabled for hosted Exchange UM access and has not been assigned a per-user policy, and if a site policy has not been assigned to the user’s site, the global policy applies.</span></span> <span data-ttu-id="81b87-112">La stratégie globale est installée avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81b87-112">The global policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="81b87-113">Vous pouvez le modifier en fonction de vos besoins, mais vous ne pouvez pas le renommer ou le supprimer.</span><span class="sxs-lookup"><span data-stu-id="81b87-113">You can modify it to meet your needs, but you cannot rename or delete it.</span></span>

  - <span data-ttu-id="81b87-114">Une stratégie de *site* peut affecter tous les utilisateurs qui sont hébergés sur le site pour lesquels la stratégie est définie.</span><span class="sxs-lookup"><span data-stu-id="81b87-114">A *site* policy can affect all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="81b87-115">Si un utilisateur est configuré pour l’accès à la messagerie unifiée Exchange hébergé sans avoir reçu une stratégie par utilisateur, la stratégie de site s’applique.</span><span class="sxs-lookup"><span data-stu-id="81b87-115">If a user is configured for hosted Exchange UM access and has not been assigned a per-user policy, the site policy applies.</span></span>

  - <span data-ttu-id="81b87-116">Une stratégie *par utilisateur* peut affecter uniquement des utilisateurs ou des groupes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="81b87-116">A *per-user* policy can affect only individual users or groups.</span></span> <span data-ttu-id="81b87-117">Pour appliquer une stratégie par utilisateur, vous devez affecter explicitement la stratégie à des utilisateurs, des groupes et des objets de contact individuels.</span><span class="sxs-lookup"><span data-stu-id="81b87-117">To enforce a per-user policy, you must explicitly assign the policy to individual users, groups, and contact objects.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81b87-118">Dans la plupart des cas, une seule stratégie de messagerie vocale hébergée est requise.</span><span class="sxs-lookup"><span data-stu-id="81b87-118">In most cases, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="81b87-119">Vous pouvez souvent modifier la politique globale en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="81b87-119">You can often modify the global policy to meet all your needs.</span></span> <span data-ttu-id="81b87-120">Si vous déployez plusieurs stratégies de messagerie vocale hébergées, toutes les stratégies de ce type ont une étendue par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="81b87-120">If you deploy multiple hosted voice mail policies, all such policies have per-user scope.</span></span>



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a><span data-ttu-id="81b87-121">Attributs de la stratégie de messagerie vocale hébergée</span><span class="sxs-lookup"><span data-stu-id="81b87-121">Hosted Voice Mail Policy Attributes</span></span>

<span data-ttu-id="81b87-122">Une stratégie de messagerie vocale définit les deux attributs insérés par l’application de routage Lync Server 2013 dans l’URI de requête d’un message d’invitation qui est envoyé à l’implémentation de MU Exchange hébergée :</span><span class="sxs-lookup"><span data-stu-id="81b87-122">A voice mail policy defines two attributes that the Lync Server 2013 ExUM Routing application inserts in the request URI of an INVITE message that is sent to the hosted Exchange UM implementation:</span></span>

  - <span data-ttu-id="81b87-123">**Destination :** Nom de domaine complet (FQDN) du service de messagerie unifiée Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="81b87-123">**Destination:** The fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="81b87-124">Cette valeur est utilisée par le serveur Edge Lync Server local à des fins de routage.</span><span class="sxs-lookup"><span data-stu-id="81b87-124">This value is used by the on-premises Lync Server Edge Server for routing purposes.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="81b87-125">Le nom de domaine complet pour Exchange Online est exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="81b87-125">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

    
    </div>

  - <span data-ttu-id="81b87-126">**Organisation :** Nom de domaine complet (FQDN) du client sur le service de messagerie unifiée Exchange hébergé qui héberge les boîtes aux lettres des utilisateurs de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81b87-126">**Organization:** The FQDN of the tenant on the hosted Exchange UM service that homes your Lync Server 2013 users’ mailboxes.</span></span> <span data-ttu-id="81b87-127">Une stratégie de messagerie vocale peut contenir plusieurs organisations.</span><span class="sxs-lookup"><span data-stu-id="81b87-127">A voice mail policy can contain multiple organizations.</span></span> <span data-ttu-id="81b87-128">S’il s’agit de plusieurs organisations, cet attribut doit être une liste séparée par des virgules des clients du serveur Exchange qui se trouvent à l’origine de vos boîtes aux lettres d’utilisateur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81b87-128">If more than one organization is included in the policy, this attribute must be a comma-separated list of the Exchange Server tenants that home your Lync Server 2013 user mailboxes.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81b87-129">L’administrateur client de votre service UM Exchange hébergé fournit les valeurs nécessaires à votre destination et aux paramètres d’attribut de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="81b87-129">The tenant administrator of your hosted Exchange UM service will provide the necessary values for your Destination and Organization attribute settings.</span></span> <span data-ttu-id="81b87-130">Pour configurer votre stratégie, vous devez exécuter l’applet de nouvelle applet de nouveau-CsHostedVoicemailPolicy ou utiliser l’applet de passe Set-CsHostedVoicemailPolicy pour en modifier une qui existe (par exemple, la stratégie globale).</span><span class="sxs-lookup"><span data-stu-id="81b87-130">To configure your policy, you must run the New-CsHostedVoicemailPolicy cmdlet or use the Set-CsHostedVoicemailPolicy cmdlet to modify one that exists (for example, the global policy).</span></span>



</div>

<span data-ttu-id="81b87-131">Pour plus d’informations sur la gestion des stratégies de messagerie vocale hébergée, consultez la documentation Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="81b87-131">For details about managing hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="81b87-132">Nouveau-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="81b87-132">New-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="81b87-133">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="81b87-133">Set-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="81b87-134">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="81b87-134">Get-CsHostedVoicemailPolicy</span></span>

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a><span data-ttu-id="81b87-135">Affectation de stratégie de messagerie vocale par utilisateur</span><span class="sxs-lookup"><span data-stu-id="81b87-135">Per-User Voice Mail Policy Assignment</span></span>

<span data-ttu-id="81b87-136">Si votre stratégie de messagerie vocale hébergée est définie avec une étendue par utilisateur, vous devez l’attribuer explicitement.</span><span class="sxs-lookup"><span data-stu-id="81b87-136">If your hosted voice mail policy is defined with per-user scope, you must explicitly assign it.</span></span> <span data-ttu-id="81b87-137">Vous pouvez exécuter l’applet de passe Grant-CsHostedVoicemailPolicy pour affecter la stratégie à des utilisateurs ou groupes individuels.</span><span class="sxs-lookup"><span data-stu-id="81b87-137">You can run the Grant-CsHostedVoicemailPolicy cmdlet to assign the policy to individual users or groups.</span></span>

<span data-ttu-id="81b87-138">Pour plus d’informations sur l’attribution ou la suppression d’une stratégie de messagerie vocale hébergée par utilisateur, voir la documentation Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="81b87-138">For details about assigning or removing a per-user hosted voice mail policy, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="81b87-139">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="81b87-139">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="81b87-140">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="81b87-140">Remove-CsHostedVoicemailPolicy</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

