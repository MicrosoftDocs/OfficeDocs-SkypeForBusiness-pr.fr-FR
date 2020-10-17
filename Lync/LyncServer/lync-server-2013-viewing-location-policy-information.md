---
title: 'Lync Server 2013 : affichage des informations de stratégie d’emplacement'
description: 'Lync Server 2013 : affichage des informations de stratégie d’emplacement.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fecc5de5fb71014a1641038e9e09afba0e90cdb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565420"
---
# <a name="viewing-location-policy-information-in-lync-server-2013"></a><span data-ttu-id="24e8a-103">Affichage des informations de stratégie d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24e8a-103">Viewing location policy information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24e8a-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="24e8a-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="24e8a-105">Dans Lync Server 2013, vous pouvez utiliser la stratégie d’emplacement pour appliquer les paramètres liés à la fonctionnalité Enhanced 9-1-1 (E9-1-1) et aux paramètres de localisation pour les utilisateurs ou les contacts.</span><span class="sxs-lookup"><span data-stu-id="24e8a-105">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="24e8a-106">La stratégie d’emplacement détermine si un utilisateur peut avoir recours au système E9-1-1 et, le cas échéant, le comportement d’un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="24e8a-106">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="24e8a-107">Par exemple, la stratégie d’emplacement permet de définir le numéro d’appel d’urgence (par exemple 911 aux États-Unis, 15 en France), de déterminer si le service de sécurité de l’entreprise doit être automatiquement averti et comment l’appel doit être acheminé.</span><span class="sxs-lookup"><span data-stu-id="24e8a-107">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="24e8a-108">Vous pouvez configurer des stratégies d’emplacement à partir du groupe **Configuration réseau** dans le panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24e8a-108">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="24e8a-109">Dans le panneau de configuration Lync Server, vous pouvez afficher, créer, modifier ou supprimer des stratégies d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="24e8a-109">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="24e8a-110">Utilisez les procédures suivantes pour afficher des informations sur les stratégies d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="24e8a-110">Use the following procedure to view information about location policies.</span></span> <span data-ttu-id="24e8a-111">Pour plus d’informations sur la création ou la modification de stratégies d’emplacement, reportez-vous à [la rubrique création ou modification d’une stratégie d’emplacement dans Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="24e8a-111">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-view-information-about-a-location-policy"></a><span data-ttu-id="24e8a-112">Pour afficher des informations sur une stratégie d’emplacement</span><span class="sxs-lookup"><span data-stu-id="24e8a-112">To view information about a location policy</span></span>

1.  <span data-ttu-id="24e8a-113">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="24e8a-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="24e8a-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="24e8a-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="24e8a-115">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="24e8a-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="24e8a-116">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie d’emplacement**.</span><span class="sxs-lookup"><span data-stu-id="24e8a-116">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="24e8a-117">Dans la page **Stratégie d’emplacement**, sélectionnez la stratégie d’emplacement que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="24e8a-117">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="24e8a-118">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="24e8a-118">On the **Edit** menu, click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="24e8a-119">Vous ne pouvez afficher des informations que sur une seule stratégie d’emplacement à la fois.</span><span class="sxs-lookup"><span data-stu-id="24e8a-119">You can only view information about one location policy at a time.</span></span>

    
    </div>

<span data-ttu-id="24e8a-p104">Une stratégie unique, appelée Globale, existe par défaut. Il n’est pas possible de supprimer ou de renommer cette stratégie. Vous pouvez cependant la modifier. Cette stratégie s’applique à tous les utilisateurs et contacts, sauf si vous créez des stratégies de site ou par utilisateur. Les stratégies par utilisateur doivent être appliquées à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="24e8a-p104">A single policy, called Global, exists by default and cannot be deleted or renamed. However, you can modify the Global policy. This policy will apply to all users and contacts, unless you create site policies or per-user policies. Per-user policies must be applied to specific users.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="24e8a-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="24e8a-124">See Also</span></span>


[<span data-ttu-id="24e8a-125">Création ou modification d’une stratégie d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24e8a-125">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="24e8a-126">Créer des stratégies d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24e8a-126">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)  
[<span data-ttu-id="24e8a-127">Création ou modification d’un site réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24e8a-127">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)  


[<span data-ttu-id="24e8a-128">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="24e8a-128">New-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[<span data-ttu-id="24e8a-129">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="24e8a-129">Set-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[<span data-ttu-id="24e8a-130">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="24e8a-130">Remove-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[<span data-ttu-id="24e8a-131">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="24e8a-131">Get-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

