---
title: Déplacer plusieurs utilisateurs vers le pool de pilotes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ffc3e01df30f4a8e1b9c9b9aeca2b2013003980
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="c7843-102">Déplacer plusieurs utilisateurs vers le pool de pilotes</span><span class="sxs-lookup"><span data-stu-id="c7843-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7843-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c7843-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c7843-104">Vous pouvez déplacer plusieurs utilisateurs à partir de votre pool Office Communications Server 2007 R2 vers votre pool de pilotes Lync Server 2013 à l’aide de Lync Server 2013 panneau de configuration ou de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c7843-104">You can move multiple users from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="c7843-105">Pour déplacer plusieurs utilisateurs à l’aide du panneau de configuration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7843-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="c7843-106">Ouvrez le **Paneau de configuration Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c7843-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="c7843-107">Dans l’onglet **recherche** , cliquez sur le bouton **Rechercher** .</span><span class="sxs-lookup"><span data-stu-id="c7843-107">From the **User Search** tab, click the **Search** button.</span></span>

3.  <span data-ttu-id="c7843-108">Cliquez ensuite sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="c7843-108">Next, click **Add Filter**.</span></span>

4.  <span data-ttu-id="c7843-109">Créer un filtre dans lequel l' **utilisateur d’Office Communications Server** est égal à **vrai**.</span><span class="sxs-lookup"><span data-stu-id="c7843-109">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

5.  <span data-ttu-id="c7843-110">Cliquez sur **Rechercher** pour rechercher les anciens utilisateurs d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c7843-110">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>

6.  <span data-ttu-id="c7843-111">Sélectionnez deux utilisateurs que vous voulez déplacer vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c7843-111">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="c7843-112">Dans cet exemple, nous allons déménager les utilisateurs Chen Yang et Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="c7843-112">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="c7843-113">![Liste d’utilisateurs affichée lors de la recherche d’utilisateurs OCS] (images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "Liste d’utilisateurs affichée lors de la recherche d’utilisateurs OCS")</span><span class="sxs-lookup"><span data-stu-id="c7843-113">![User list displayed from searching for OCS users](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "User list displayed from searching for OCS users")</span></span>  

7.  <span data-ttu-id="c7843-114">Dans le menu **action** , sélectionnez **déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="c7843-114">From the **Action** menu, select **Move selected users to pool**.</span></span>

8.  <span data-ttu-id="c7843-115">Dans la liste déroulante, sélectionnez le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c7843-115">From the drop-down list, select the Lync Server 2013 pool.</span></span>

9.  <span data-ttu-id="c7843-116">Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="c7843-116">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="c7843-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c7843-117">Click OK.</span></span>
    
    <span data-ttu-id="c7843-118">![Déplacer des utilisateurs, boîte de dialogue pool d’inscriptions de destination] (images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Déplacer des utilisateurs, boîte de dialogue pool d’inscriptions de destination")</span><span class="sxs-lookup"><span data-stu-id="c7843-118">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

10. <span data-ttu-id="c7843-119">Vérifiez que la colonne **pool d’inscriptions** pour les utilisateurs contient désormais le pool Lync Server 2013, qui indique que les utilisateurs ont été déplacés correctement.</span><span class="sxs-lookup"><span data-stu-id="c7843-119">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="c7843-120">Pour déplacer plusieurs utilisateurs à l’aide de Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="c7843-120">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="c7843-121">Ouvrez Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c7843-121">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="c7843-122">Dans la ligne de commande, tapez les informations suivantes et remplacez **User1** et **utilisateur2** par des noms d’utilisateur spécifiques que vous voulez déplacer, puis remplacez **FQDN du pool\_** par le nom du pool de destination.</span><span class="sxs-lookup"><span data-stu-id="c7843-122">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="c7843-123">Dans cet exemple, nous allons déplacer les utilisateurs de Hao Chen et Katie Jordanie.</span><span class="sxs-lookup"><span data-stu-id="c7843-123">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="c7843-124">![Exemple de cmdlet pour déplacer un utilisateur hérité] (images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Exemple de cmdlet pour déplacer un utilisateur hérité")</span><span class="sxs-lookup"><span data-stu-id="c7843-124">![Example cmdlet to move a legacy user](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Example cmdlet to move a legacy user")</span></span>  

3.  <span data-ttu-id="c7843-125">Dans la ligne de commande, tapez ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="c7843-125">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="c7843-126">L’identité du **pool d’inscriptions** doit maintenant pointer sur le pool que vous avez spécifié comme **nom de domaine complet du pool\_** à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="c7843-126">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="c7843-127">La présence de cette identité confirme que l’utilisateur a bien été déplacé.</span><span class="sxs-lookup"><span data-stu-id="c7843-127">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="c7843-128">Répétez l’étape pour vérifier que l' **utilisateur2** a été déplacé.</span><span class="sxs-lookup"><span data-stu-id="c7843-128">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="c7843-129">![Sortie de l’applet de passe PowerShell Get-UsUser-Identity] (images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Sortie de l’applet de passe PowerShell Get-UsUser-Identity")</span><span class="sxs-lookup"><span data-stu-id="c7843-129">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="c7843-130">Pour déplacer tous les utilisateurs en même temps à l’aide de Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="c7843-130">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="c7843-131">Dans cet exemple, tous les utilisateurs ont été retournés au pool Office Communications Server 2007 R2 (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="c7843-131">In this example, all users have been returned to the Office Communications Server 2007 R2 pool (pool01.contoso.net).</span></span> <span data-ttu-id="c7843-132">À l’aide de Lync Server 2013 Management Shell, tous les utilisateurs sont déplacés en même temps que le pool Lync Server 2013 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="c7843-132">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="c7843-133">Ouvrez **Lync Server 2013 Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c7843-133">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="c7843-134">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c7843-134">At the command line, type the following:</span></span>
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="c7843-135">![Exemple de cmdlet pour déplacer tous les anciens utilisateurs d’un pool] (images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Exemple de cmdlet pour déplacer tous les anciens utilisateurs d’un pool")</span><span class="sxs-lookup"><span data-stu-id="c7843-135">![Example cmdlet to move all legacy users in a pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Example cmdlet to move all legacy users in a pool")</span></span>  

3.  <span data-ttu-id="c7843-136">Exécutez ensuite **Get-Csuser** pour l’un des utilisateurs pilote.</span><span class="sxs-lookup"><span data-stu-id="c7843-136">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="c7843-137">L’identité du **pool d’inscriptions** pour chaque utilisateur pointe désormais sur le pool que vous avez\_spécifié comme «nom de domaine complet du pool» à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="c7843-137">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="c7843-138">La présence de cette identité confirme que l’utilisateur a bien été déplacé.</span><span class="sxs-lookup"><span data-stu-id="c7843-138">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="c7843-139">Par ailleurs, nous pouvons afficher la liste des utilisateurs dans le panneau de configuration de Lync Server 2013 et vérifier que la valeur du pool d’inscriptions pointe désormais vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c7843-139">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="c7843-140">![Liste des utilisateurs de Lync Server 2013 Control Panel] (images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Liste des utilisateurs de Lync Server 2013 Control Panel")</span><span class="sxs-lookup"><span data-stu-id="c7843-140">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

