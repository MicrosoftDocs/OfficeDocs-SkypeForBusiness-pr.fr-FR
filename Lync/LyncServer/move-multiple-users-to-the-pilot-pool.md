---
title: Déplacer plusieurs utilisateurs vers le pool de pilotes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc3104566841cc70eeee489a4b8812a6b8039a31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="a921c-102">Déplacer plusieurs utilisateurs vers le pool de pilotes</span><span class="sxs-lookup"><span data-stu-id="a921c-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a921c-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a921c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a921c-104">Vous pouvez déplacer plusieurs utilisateurs de votre pool Lync Server 2010 vers votre pool de pilotes Lync Server 2013 à l’aide de Lync Server 2013 panneau de configuration ou de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a921c-104">You can move multiple users from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="a921c-105">Pour déplacer plusieurs utilisateurs à l’aide du panneau de configuration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a921c-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="a921c-106">Ouvrez le **Paneau de configuration Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a921c-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="a921c-107">Cliquez successivement sur **Utilisateurs**, Rechercher, puis sur **Trouver**.</span><span class="sxs-lookup"><span data-stu-id="a921c-107">Click **Users**, click Search, and then click **Find**.</span></span>

3.  <span data-ttu-id="a921c-108">Sélectionnez deux utilisateurs que vous voulez déplacer vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a921c-108">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="a921c-109">Dans cet exemple, nous allons déménager les utilisateurs Chen Yang et Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="a921c-109">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="a921c-110">![Déplacer des utilisateurs vers un pool de Registre spécifique] (images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Déplacer des utilisateurs vers un pool de Registre spécifique")</span><span class="sxs-lookup"><span data-stu-id="a921c-110">![Move users to specific register pool](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Move users to specific register pool")</span></span>  

4.  <span data-ttu-id="a921c-111">Dans le menu **action** , sélectionnez **déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="a921c-111">From the **Action** menu, select **Move selected users to pool**.</span></span>

5.  <span data-ttu-id="a921c-112">Dans la liste déroulante, sélectionnez le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a921c-112">From the drop-down list, select the Lync Server 2013 pool.</span></span>

6.  <span data-ttu-id="a921c-113">Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="a921c-113">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="a921c-114">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a921c-114">Click OK.</span></span>
    
    <span data-ttu-id="a921c-115">![Déplacer des utilisateurs, boîte de dialogue pool d’inscriptions de destination] (images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Déplacer des utilisateurs, boîte de dialogue pool d’inscriptions de destination")</span><span class="sxs-lookup"><span data-stu-id="a921c-115">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

7.  <span data-ttu-id="a921c-116">Vérifiez que la colonne **pool d’inscriptions** pour les utilisateurs contient désormais le pool Lync Server 2013, qui indique que les utilisateurs ont été déplacés correctement.</span><span class="sxs-lookup"><span data-stu-id="a921c-116">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="a921c-117">Pour déplacer plusieurs utilisateurs à l’aide de Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="a921c-117">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="a921c-118">Ouvrez Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a921c-118">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="a921c-119">Dans la ligne de commande, tapez les informations suivantes et remplacez **User1** et **utilisateur2** par des noms d’utilisateur spécifiques que vous voulez déplacer, puis remplacez **FQDN du pool\_** par le nom du pool de destination.</span><span class="sxs-lookup"><span data-stu-id="a921c-119">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="a921c-120">Dans cet exemple, nous allons déplacer les utilisateurs de Hao Chen et Katie Jordanie.</span><span class="sxs-lookup"><span data-stu-id="a921c-120">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="a921c-121">![Exemple d’applet de passe PowerShell Get-Csuser] (images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Exemple d’applet de passe PowerShell Get-Csuser")</span><span class="sxs-lookup"><span data-stu-id="a921c-121">![Example of PowerShell Get-CsUser cmdlet](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Example of PowerShell Get-CsUser cmdlet")</span></span>  

3.  <span data-ttu-id="a921c-122">Dans la ligne de commande, tapez ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="a921c-122">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="a921c-123">L’identité du **pool d’inscriptions** doit maintenant pointer sur le pool que vous avez spécifié comme **nom de domaine complet du pool\_** à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="a921c-123">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="a921c-124">La présence de cette identité confirme que l’utilisateur a bien été déplacé.</span><span class="sxs-lookup"><span data-stu-id="a921c-124">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="a921c-125">Répétez l’étape pour vérifier que l' **utilisateur2** a été déplacé.</span><span class="sxs-lookup"><span data-stu-id="a921c-125">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="a921c-126">![Sortie de l’applet de passe PowerShell Get-UsUser-Identity] (images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Sortie de l’applet de passe PowerShell Get-UsUser-Identity")</span><span class="sxs-lookup"><span data-stu-id="a921c-126">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="a921c-127">Pour déplacer tous les utilisateurs en même temps à l’aide de Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="a921c-127">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="a921c-128">Dans cet exemple, tous les utilisateurs ont été retournés au pool Lync Server 2010 (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="a921c-128">In this example, all users have been returned to the Lync Server 2010 pool (pool01.contoso.net).</span></span> <span data-ttu-id="a921c-129">À l’aide de Lync Server 2013 Management Shell, tous les utilisateurs sont déplacés en même temps que le pool Lync Server 2013 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="a921c-129">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="a921c-130">Ouvrez **Lync Server 2013 Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a921c-130">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="a921c-131">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="a921c-131">At the command line, type the following:</span></span>
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="a921c-132">![Applet de requête PowerShell et résultats dans Management Shell] (images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "Applet de requête PowerShell et résultats dans Management Shell")</span><span class="sxs-lookup"><span data-stu-id="a921c-132">![PowerShell cmdlet and results in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet and results in Management Shell")</span></span>  

3.  <span data-ttu-id="a921c-133">Exécutez ensuite **Get-Csuser** pour l’un des utilisateurs pilote.</span><span class="sxs-lookup"><span data-stu-id="a921c-133">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="a921c-134">L’identité du **pool d’inscriptions** pour chaque utilisateur pointe désormais sur le pool que vous avez\_spécifié comme «nom de domaine complet du pool» à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="a921c-134">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="a921c-135">La présence de cette identité confirme que l’utilisateur a bien été déplacé.</span><span class="sxs-lookup"><span data-stu-id="a921c-135">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="a921c-136">Par ailleurs, nous pouvons afficher la liste des utilisateurs dans le panneau de configuration de Lync Server 2013 et vérifier que la valeur du pool d’inscriptions pointe désormais vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a921c-136">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="a921c-137">![Liste des utilisateurs de Lync Server 2013 Control Panel] (images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Liste des utilisateurs de Lync Server 2013 Control Panel")</span><span class="sxs-lookup"><span data-stu-id="a921c-137">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

