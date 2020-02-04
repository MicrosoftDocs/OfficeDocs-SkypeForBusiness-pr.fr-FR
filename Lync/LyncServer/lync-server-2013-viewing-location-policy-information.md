---
title: 'Lync Server 2013 : affichage des informations de stratégie d’emplacement'
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
ms.openlocfilehash: 0f68ad38ffbc8bb1b4abdfbf8119add7d9f965e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-location-policy-information-in-lync-server-2013"></a><span data-ttu-id="24ab4-102">Affichage des informations de stratégie d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24ab4-102">Viewing location policy information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24ab4-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="24ab4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="24ab4-104">Dans Lync Server 2013, vous pouvez utiliser la stratégie d’emplacement pour appliquer les paramètres relatifs à la fonctionnalité améliorée 9-1-1 (E9-1-1) et aux paramètres d’emplacement des utilisateurs ou des contacts.</span><span class="sxs-lookup"><span data-stu-id="24ab4-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="24ab4-105">La stratégie d’emplacement détermine si un utilisateur est activé pour E9-1-1 et, si oui, le comportement d’un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="24ab4-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="24ab4-106">Par exemple, vous pouvez utiliser la stratégie d’emplacement pour définir le numéro constituant un appel d’urgence (par exemple, 911 aux États-Unis), si la sécurité d’entreprise doit être automatiquement notifiée et la manière dont l’appel doit être routé.</span><span class="sxs-lookup"><span data-stu-id="24ab4-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="24ab4-107">Vous pouvez configurer des stratégies d’emplacement à partir du groupe de **Configuration réseau** dans Lync Server 2013 Control Panel.</span><span class="sxs-lookup"><span data-stu-id="24ab4-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="24ab4-108">Le panneau de configuration de Lync Server vous permet d’afficher, de créer, de modifier ou de supprimer des stratégies d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="24ab4-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="24ab4-109">Pour afficher des informations sur les stratégies d’emplacement, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="24ab4-109">Use the following procedure to view information about location policies.</span></span> <span data-ttu-id="24ab4-110">Pour plus d’informations sur la création ou la modification de stratégies d’emplacement, voir [création ou modification d’une stratégie d’emplacement dans Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="24ab4-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-view-information-about-a-location-policy"></a><span data-ttu-id="24ab4-111">Pour afficher des informations sur une stratégie d’emplacement</span><span class="sxs-lookup"><span data-stu-id="24ab4-111">To view information about a location policy</span></span>

1.  <span data-ttu-id="24ab4-112">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="24ab4-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="24ab4-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="24ab4-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="24ab4-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="24ab4-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="24ab4-115">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **stratégie d’emplacement**.</span><span class="sxs-lookup"><span data-stu-id="24ab4-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="24ab4-116">Dans la page de **stratégie d’emplacement** , sélectionnez la stratégie d’emplacement que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="24ab4-116">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="24ab4-117">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="24ab4-117">On the **Edit** menu, click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="24ab4-118">Vous pouvez uniquement afficher des informations sur une stratégie d’emplacement à la fois.</span><span class="sxs-lookup"><span data-stu-id="24ab4-118">You can only view information about one location policy at a time.</span></span>

    
    </div>

<span data-ttu-id="24ab4-119">Une stratégie unique, appelée global, existe par défaut et ne peut pas être supprimée ou renommée.</span><span class="sxs-lookup"><span data-stu-id="24ab4-119">A single policy, called Global, exists by default and cannot be deleted or renamed.</span></span> <span data-ttu-id="24ab4-120">Toutefois, vous pouvez modifier la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="24ab4-120">However, you can modify the Global policy.</span></span> <span data-ttu-id="24ab4-121">Ce paramètre s’applique à tous les utilisateurs et contacts, sauf si vous créez des stratégies de site ou des stratégies par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="24ab4-121">This policy will apply to all users and contacts, unless you create site policies or per-user policies.</span></span> <span data-ttu-id="24ab4-122">Les stratégies par utilisateur doivent être appliquées à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="24ab4-122">Per-user policies must be applied to specific users.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="24ab4-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="24ab4-123">See Also</span></span>


[<span data-ttu-id="24ab4-124">Création ou modification d’une stratégie d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24ab4-124">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="24ab4-125">Créer des stratégies d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24ab4-125">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)  
[<span data-ttu-id="24ab4-126">Création ou modification d’un site réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24ab4-126">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)  


[<span data-ttu-id="24ab4-127">Nouveau-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="24ab4-127">New-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[<span data-ttu-id="24ab4-128">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="24ab4-128">Set-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[<span data-ttu-id="24ab4-129">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="24ab4-129">Remove-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[<span data-ttu-id="24ab4-130">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="24ab4-130">Get-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

