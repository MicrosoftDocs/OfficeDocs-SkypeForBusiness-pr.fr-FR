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
ms.openlocfilehash: 2ea7f585e42164c8387853c7525cd0478eeb4db4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="5acd8-102">Suppression d’une stratégie d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5acd8-102">Deleting a location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5acd8-103">_**Dernière modification de la rubrique :** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="5acd8-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="5acd8-104">Dans Lync Server 2013, vous pouvez utiliser la stratégie d’emplacement pour appliquer les paramètres relatifs à la fonctionnalité améliorée 9-1-1 (E9-1-1) et aux paramètres d’emplacement des utilisateurs ou des contacts.</span><span class="sxs-lookup"><span data-stu-id="5acd8-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="5acd8-105">La stratégie d’emplacement détermine si un utilisateur est activé pour E9-1-1 et, si oui, le comportement d’un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="5acd8-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="5acd8-106">Par exemple, vous pouvez utiliser la stratégie d’emplacement pour définir le numéro constituant un appel d’urgence (par exemple, 911 aux États-Unis), si la sécurité d’entreprise doit être automatiquement notifiée et la manière dont l’appel doit être routé.</span><span class="sxs-lookup"><span data-stu-id="5acd8-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="5acd8-107">Vous pouvez configurer des stratégies d’emplacement à partir du groupe de **Configuration réseau** dans Lync Server 2013 Control Panel.</span><span class="sxs-lookup"><span data-stu-id="5acd8-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="5acd8-108">Le panneau de configuration de Lync Server vous permet d’afficher, de créer, de modifier ou de supprimer des stratégies d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="5acd8-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="5acd8-109">Pour supprimer une stratégie d’emplacement, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="5acd8-109">Use the following procedures delete a location policy.</span></span> <span data-ttu-id="5acd8-110">Pour plus d’informations sur la création ou la modification de stratégies d’emplacement, voir [création ou modification d’une stratégie d’emplacement dans Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="5acd8-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-delete-a-location-policy"></a><span data-ttu-id="5acd8-111">Pour supprimer une stratégie d’emplacement</span><span class="sxs-lookup"><span data-stu-id="5acd8-111">To delete a location policy</span></span>

1.  <span data-ttu-id="5acd8-112">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="5acd8-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5acd8-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5acd8-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5acd8-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5acd8-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5acd8-115">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **stratégie d’emplacement**.</span><span class="sxs-lookup"><span data-stu-id="5acd8-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="5acd8-116">Dans la page de **stratégie d’emplacement** , sélectionnez la stratégie d’emplacement que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="5acd8-116">On the **Location Policy** page, select the location policy that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5acd8-117">Vous pouvez supprimer plusieurs stratégies d’emplacement à la fois.</span><span class="sxs-lookup"><span data-stu-id="5acd8-117">You can delete more than one location policy at a time.</span></span> <span data-ttu-id="5acd8-118">Pour cela, appuyez sur CTRL et sélectionnez plusieurs stratégies tout en maintenant la touche CTRL enfoncée.</span><span class="sxs-lookup"><span data-stu-id="5acd8-118">To do this, press CTRL and select multiple policies while holding down the CTRL key.</span></span> <span data-ttu-id="5acd8-119">Vous pouvez sélectionner toutes les <STRONG>stratégies dans le</STRONG> menu <STRONG>Edition</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="5acd8-119">Or, to select all policies, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="5acd8-120">Dans le menu **modifier** , cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="5acd8-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="5acd8-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5acd8-121">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5acd8-122">La stratégie d’emplacement global ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="5acd8-122">You cannot delete the Global location policy.</span></span> <span data-ttu-id="5acd8-123">Si vous tentez de supprimer la stratégie globale, vous recevez un message d’avertissement indiquant que la stratégie sera réinitialisée à ses valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="5acd8-123">If you attempt to delete the Global policy you will receive a warning message and that policy will be reset to its default values.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5acd8-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5acd8-124">See Also</span></span>


[<span data-ttu-id="5acd8-125">Création ou modification d’une stratégie d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5acd8-125">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="5acd8-126">Affichage des informations de stratégie d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5acd8-126">Viewing location policy information in Lync Server 2013</span></span>](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

