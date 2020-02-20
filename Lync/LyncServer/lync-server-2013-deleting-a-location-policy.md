---
title: 'Lync Server 2013 : suppression d’une stratégie d’emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be70f56f2a33ef92769a129e8fd9f84fe467c93e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="fcb30-102">Suppression d’une stratégie d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fcb30-102">Deleting a location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcb30-103">_**Dernière modification de la rubrique :** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="fcb30-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="fcb30-104">Dans Lync Server 2013, vous pouvez utiliser la stratégie d’emplacement pour appliquer les paramètres liés à la fonctionnalité Enhanced 9-1-1 (E9-1-1) et aux paramètres de localisation pour les utilisateurs ou les contacts.</span><span class="sxs-lookup"><span data-stu-id="fcb30-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="fcb30-105">La stratégie d’emplacement détermine si un utilisateur peut avoir recours au système E9-1-1 et, le cas échéant, le comportement d’un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="fcb30-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="fcb30-106">Par exemple, la stratégie d’emplacement permet de définir le numéro d’appel d’urgence (par exemple 911 aux États-Unis, 15 en France), de déterminer si le service de sécurité de l’entreprise doit être automatiquement averti et comment l’appel doit être acheminé.</span><span class="sxs-lookup"><span data-stu-id="fcb30-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="fcb30-107">Vous pouvez configurer des stratégies d’emplacement à partir du groupe **Configuration réseau** dans le panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fcb30-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="fcb30-108">Dans le panneau de configuration Lync Server, vous pouvez afficher, créer, modifier ou supprimer des stratégies d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="fcb30-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="fcb30-109">Utilisez les procédures suivantes pour supprimer une stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="fcb30-109">Use the following procedures delete a location policy.</span></span> <span data-ttu-id="fcb30-110">Pour plus d’informations sur la création ou la modification de stratégies d’emplacement, reportez-vous à [la rubrique création ou modification d’une stratégie d’emplacement dans Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="fcb30-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-delete-a-location-policy"></a><span data-ttu-id="fcb30-111">Pour supprimer une stratégie d’emplacement</span><span class="sxs-lookup"><span data-stu-id="fcb30-111">To delete a location policy</span></span>

1.  <span data-ttu-id="fcb30-112">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="fcb30-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fcb30-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fcb30-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fcb30-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fcb30-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fcb30-115">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie d’emplacement**.</span><span class="sxs-lookup"><span data-stu-id="fcb30-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="fcb30-116">Dans la page **Stratégie d’emplacement**, sélectionnez la stratégie d’emplacement que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="fcb30-116">On the **Location Policy** page, select the location policy that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fcb30-p104">Vous pouvez supprimer plusieurs stratégies d’emplacement à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs stratégies. Ou, pour sélectionner toutes les stratégies, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fcb30-p104">You can delete more than one location policy at a time. To do this, press CTRL and select multiple policies while holding down the CTRL key. Or, to select all policies, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="fcb30-120">Dans le menu **Edition**, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="fcb30-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="fcb30-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fcb30-121">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fcb30-p105">Vous ne pouvez pas supprimer la stratégie d’emplacement globale. Si vous tentez de supprimer cette stratégie vous obtiendrez un message d’erreur et les valeurs par défaut de cette stratégie seront rétablies.</span><span class="sxs-lookup"><span data-stu-id="fcb30-p105">You cannot delete the Global location policy. If you attempt to delete the Global policy you will receive a warning message and that policy will be reset to its default values.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fcb30-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fcb30-124">See Also</span></span>


[<span data-ttu-id="fcb30-125">Création ou modification d’une stratégie d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fcb30-125">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="fcb30-126">Affichage des informations de stratégie d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fcb30-126">Viewing location policy information in Lync Server 2013</span></span>](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

