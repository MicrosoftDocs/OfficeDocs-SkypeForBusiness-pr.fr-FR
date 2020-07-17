---
title: Déplacer plusieurs utilisateurs vers le pool pilote
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c663566605529b25d9890bb31cba462364c813
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="ec244-102">Déplacer plusieurs utilisateurs vers le pool pilote</span><span class="sxs-lookup"><span data-stu-id="ec244-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec244-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ec244-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ec244-104">Vous pouvez déplacer plusieurs utilisateurs de votre pool Office Communications Server 2007 R2 vers votre pool de pilote Lync Server 2013 à l’aide du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ec244-104">You can move multiple users from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="ec244-105">Pour déplacer plusieurs utilisateurs à l’aide du panneau de configuration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec244-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="ec244-106">Ouvrez le **Panneau de configuration Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ec244-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="ec244-107">Sous l’onglet **Recherche d’un utilisateur**, cliquez sur le bouton **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="ec244-107">From the **User Search** tab, click the **Search** button.</span></span>

3.  <span data-ttu-id="ec244-108">Cliquez ensuite sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="ec244-108">Next, click **Add Filter**.</span></span>

4.  <span data-ttu-id="ec244-109">Créez un filtre pour lequel **Utilisateur Office Communications Server** a la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="ec244-109">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

5.  <span data-ttu-id="ec244-110">Cliquez sur **Rechercher** pour rechercher les utilisateurs hérités d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ec244-110">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>

6.  <span data-ttu-id="ec244-111">Sélectionnez deux utilisateurs que vous souhaitez déplacer vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ec244-111">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="ec244-112">Dans cet exemple, nous allons déplacer les utilisateurs Chen Yang et Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="ec244-112">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="ec244-113">![Liste des utilisateurs affichée à partir de la recherche d’utilisateurs OCS](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "Liste des utilisateurs affichée à partir de la recherche d’utilisateurs OCS")</span><span class="sxs-lookup"><span data-stu-id="ec244-113">![User list displayed from searching for OCS users](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "User list displayed from searching for OCS users")</span></span>  

7.  <span data-ttu-id="ec244-114">Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="ec244-114">From the **Action** menu, select **Move selected users to pool**.</span></span>

8.  <span data-ttu-id="ec244-115">Dans la liste déroulante, sélectionnez le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ec244-115">From the drop-down list, select the Lync Server 2013 pool.</span></span>

9.  <span data-ttu-id="ec244-116">Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="ec244-116">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="ec244-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ec244-117">Click OK.</span></span>
    
    <span data-ttu-id="ec244-118">![Boîte de dialogue déplacer des utilisateurs, pool de serveurs d’inscriptions de destination](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Boîte de dialogue déplacer des utilisateurs, pool de serveurs d’inscriptions de destination")</span><span class="sxs-lookup"><span data-stu-id="ec244-118">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

10. <span data-ttu-id="ec244-119">Vérifiez que la colonne pool de serveurs d' **inscriptions** des utilisateurs contient désormais le pool Lync Server 2013, ce qui indique que les utilisateurs ont été déplacés avec succès.</span><span class="sxs-lookup"><span data-stu-id="ec244-119">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="ec244-120">Pour déplacer plusieurs utilisateurs à l’aide de Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="ec244-120">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="ec244-121">Ouvrez Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ec244-121">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="ec244-122">Sur la ligne de commande, tapez ce qui suit et remplacez **utilisateur1** et **utilisateur2** par des noms d’utilisateur spécifiques que vous souhaitez déplacer et remplacer le nom de \*\* \_ domaine complet du pool\*\* par le nom du pool de destination.</span><span class="sxs-lookup"><span data-stu-id="ec244-122">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="ec244-123">Dans cet exemple, nous allons déplacer les utilisateurs Hao Chen et Katie Jordan.</span><span class="sxs-lookup"><span data-stu-id="ec244-123">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="ec244-124">![Exemple de cmdlet pour déplacer un utilisateur hérité](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Exemple de cmdlet pour déplacer un utilisateur hérité")</span><span class="sxs-lookup"><span data-stu-id="ec244-124">![Example cmdlet to move a legacy user](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Example cmdlet to move a legacy user")</span></span>  

3.  <span data-ttu-id="ec244-125">Sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="ec244-125">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="ec244-126">L’identité du pool de serveurs d' **inscriptions** doit désormais pointer vers le pool que vous avez spécifié comme **nom de \_ domaine complet du pool** à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="ec244-126">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="ec244-127">La présence de cette identité confirme que l’utilisateur a été déplacé avec succès.</span><span class="sxs-lookup"><span data-stu-id="ec244-127">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="ec244-128">Répétez cette étape pour vérifier que **User2** a été déplacé.</span><span class="sxs-lookup"><span data-stu-id="ec244-128">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="ec244-129">![Sortie de l’applet de commande PowerShell Get-UsUser-Identity](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Sortie de l’applet de commande PowerShell Get-UsUser-Identity")</span><span class="sxs-lookup"><span data-stu-id="ec244-129">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="ec244-130">Pour déplacer tous les utilisateurs en même temps à l’aide de Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="ec244-130">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="ec244-131">Dans cet exemple, tous les utilisateurs ont été renvoyés au pool Office Communications Server 2007 R2 (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="ec244-131">In this example, all users have been returned to the Office Communications Server 2007 R2 pool (pool01.contoso.net).</span></span> <span data-ttu-id="ec244-132">À l’aide de Lync Server 2013 Management Shell, nous allons déplacer tous les utilisateurs en même temps vers le pool Lync Server 2013 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="ec244-132">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="ec244-133">Ouvrez **Lync Server 2013 Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ec244-133">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="ec244-134">Dans la ligne de commande, tapez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="ec244-134">At the command line, type the following:</span></span>
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="ec244-135">![Exemple de cmdlet permettant de déplacer tous les utilisateurs hérités dans un pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Exemple de cmdlet permettant de déplacer tous les utilisateurs hérités dans un pool")</span><span class="sxs-lookup"><span data-stu-id="ec244-135">![Example cmdlet to move all legacy users in a pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Example cmdlet to move all legacy users in a pool")</span></span>  

3.  <span data-ttu-id="ec244-136">Exécutez ensuite **Get-CsUser** pour l’un des utilisateurs pilotes.</span><span class="sxs-lookup"><span data-stu-id="ec244-136">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="ec244-137">L’identité du pool de serveurs d' **inscriptions** pour chaque utilisateur pointe désormais vers le pool que vous avez spécifié en tant que « \_ nom de domaine complet du pool » à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="ec244-137">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="ec244-138">Le présence de cette identité confirme que l’utilisateur a été déplacé avec succès.</span><span class="sxs-lookup"><span data-stu-id="ec244-138">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="ec244-139">De plus, nous pouvons afficher la liste des utilisateurs dans le panneau de configuration Lync Server 2013 et vérifier que la valeur de pool de serveurs d’inscriptions pointe désormais vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ec244-139">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="ec244-140">![Liste des utilisateurs de Lync Server 2013 panneau de configuration](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Liste des utilisateurs de Lync Server 2013 panneau de configuration")</span><span class="sxs-lookup"><span data-stu-id="ec244-140">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

