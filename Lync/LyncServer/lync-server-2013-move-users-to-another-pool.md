---
title: 'Lync Server 2013 : déplacer des utilisateurs vers un autre pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1feda518b1a15ce5b4622659b9e5df45044bcefa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a><span data-ttu-id="9179a-102">Déplacer des utilisateurs vers un autre pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9179a-102">Move users to another pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="9179a-103">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="9179a-103">

<span> </span></span></span>

<span data-ttu-id="9179a-104">_**Dernière modification de la rubrique :** 2018-02-09_</span><span class="sxs-lookup"><span data-stu-id="9179a-104">_**Topic Last Modified:** 2018-02-09_</span></span>

<span data-ttu-id="9179a-105">Vous pouvez utiliser le panneau de configuration Lync Server pour affecter des utilisateurs à un serveur ou un pool spécifique.</span><span class="sxs-lookup"><span data-stu-id="9179a-105">You can use Lync Server Control Panel to assign users to a specific server or pool.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="9179a-106">Le fait de transférer tous les utilisateurs existants d’un pool source exécutant Lync Server 2010 ou une version antérieure vers un pool de destination Lync Server 2013 dans un environnement Active Directory complexe peut ralentir la réplication Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9179a-106">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Lync Server 2013 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="9179a-107">Pour éviter cela, vous pouvez utiliser des filtres de recherche pour déplacer des utilisateurs à partir de pools qui exécutent Lync Server 2010 ou une version antérieure séparément, ou vous pouvez utiliser Lync Server Management Shell pour déplacer des utilisateurs avec cmdlets.</span><span class="sxs-lookup"><span data-stu-id="9179a-107">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Lync Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="9179a-108">En outre, la fonctionnalité de filtrage fonctionne avec les utilisateurs de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9179a-108">Also, the filter functionality works with Lync Server 2013 users.</span></span>



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="9179a-109">Pour déplacer les utilisateurs sélectionnés vers un autre serveur ou pool</span><span class="sxs-lookup"><span data-stu-id="9179a-109">To move selected users to a different server or pool</span></span>

1.  <span data-ttu-id="9179a-110">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="9179a-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9179a-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9179a-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9179a-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9179a-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9179a-113">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="9179a-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="9179a-114">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur souhaité, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="9179a-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="9179a-115">Dans le tableau, sélectionnez un ou plusieurs utilisateurs dans la liste.</span><span class="sxs-lookup"><span data-stu-id="9179a-115">In the table, select a specific user or users in the list.</span></span>

6.  <span data-ttu-id="9179a-116">Dans le menu **Action**, cliquez sur **Déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="9179a-116">On the **Action** menu, click **Move selected users to pool**.</span></span>

7.  <span data-ttu-id="9179a-117">Dans **Déplacer des utilisateurs**, sélectionnez dans le champ **Pool de serveurs d’inscriptions de destination** le pool vers lequel vous souhaitez déplacer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="9179a-117">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>

8.  <span data-ttu-id="9179a-118">(Optionnel) Si le serveur ou pool de destination n’est pas disponible, activez la case à cocher **Forcer**.</span><span class="sxs-lookup"><span data-stu-id="9179a-118">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="9179a-119">Si vous sélectionnez <STRONG>forcer</STRONG>, le compte d’utilisateur est déplacé, mais les données utilisateur associées à ces conférences et contacts planifiés ne sont pas déplacées.</span><span class="sxs-lookup"><span data-stu-id="9179a-119">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="9179a-120">Pour déplacer tous les utilisateurs d’un seul serveur ou pool vers un autre serveur ou pool</span><span class="sxs-lookup"><span data-stu-id="9179a-120">To move all users from one server or pool to a different server or pool</span></span>

1.  <span data-ttu-id="9179a-121">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="9179a-121">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9179a-122">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9179a-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9179a-123">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9179a-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9179a-124">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="9179a-124">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="9179a-125">Dans le menu **Action**, cliquez sur **Déplacer tous les utilisateurs vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="9179a-125">On the **Action** menu, click **Move all users to pool**.</span></span>

5.  <span data-ttu-id="9179a-126">Dans **Déplacer des utilisateurs**, sélectionnez le pool contenant les comptes d’utilisateurs que vous souhaitez déplacer à l’aide de l’option **Pool de serveurs d’inscriptions source**.</span><span class="sxs-lookup"><span data-stu-id="9179a-126">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

6.  <span data-ttu-id="9179a-127">Dans **Pool de serveurs d’inscriptions de destination**, sélectionnez le pool vers lequel vous souhaitez déplacer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="9179a-127">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>

7.  <span data-ttu-id="9179a-128">(Optionnel) Si le serveur ou le pool de destination n’est pas disponible, activez la case à cocher **Forcer**.</span><span class="sxs-lookup"><span data-stu-id="9179a-128">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="9179a-129">Si vous sélectionnez <STRONG>forcer</STRONG>, le compte d’utilisateur est déplacé, mais les données utilisateur associées à ces conférences et contacts planifiés ne sont pas déplacées.</span><span class="sxs-lookup"><span data-stu-id="9179a-129">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="9179a-130">Pour déplacer des utilisateurs d’un pool vers un autre pool à l’aide d’un filtre</span><span class="sxs-lookup"><span data-stu-id="9179a-130">To move users from one pool to a different pool by using a filter</span></span>

1.  <span data-ttu-id="9179a-131">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="9179a-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9179a-132">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9179a-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9179a-133">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9179a-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9179a-134">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="9179a-134">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="9179a-135">Dans **recherche d’utilisateur**, cliquez sur **recherche**, puis sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="9179a-135">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>

5.  <span data-ttu-id="9179a-136">Dans les critères de recherche, sélectionnez **Pool de serveurs d’inscriptions**, **Égal à**, **Nom de domaine complet du pool actuel**, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="9179a-136">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>

6.  <span data-ttu-id="9179a-137">Dans le menu **Action**, cliquez sur **Déplacer tous les utilisateurs vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="9179a-137">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9179a-138">Lorsqu’un filtre est appliqué à un ensemble d’utilisateurs existant, l’option <STRONG>déplacer tous les utilisateurs vers le pool</STRONG> est dans le contexte du sous-ensemble filtré des utilisateurs, et non pas de <STRONG><EM>tous</EM></STRONG> les utilisateurs possibles.</span><span class="sxs-lookup"><span data-stu-id="9179a-138">When a filter is applied to an existing set of users, the option <STRONG>Move all users to pool</STRONG> is in the context of the filtered subset of users, not <STRONG><EM>all</EM></STRONG> possible users.</span></span>

    
    </div>

7.  <span data-ttu-id="9179a-139">Dans **Déplacer des utilisateurs**, sélectionnez le pool contenant les comptes d’utilisateur que vous souhaitez déplacer à l’aide de l’option **Pool de serveurs d’inscriptions source**.</span><span class="sxs-lookup"><span data-stu-id="9179a-139">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

8.  <span data-ttu-id="9179a-140">Dans **Pool de serveurs d’inscriptions de destination**, sélectionnez le pool vers lequel vous souhaitez déplacer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="9179a-140">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>

9.  <span data-ttu-id="9179a-141">(Optionnel) Si le serveur ou pool de destination n’est pas disponible, activez la case à cocher **Forcer**.</span><span class="sxs-lookup"><span data-stu-id="9179a-141">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="9179a-142">Si vous sélectionnez <STRONG>forcer</STRONG>, le compte d’utilisateur est déplacé, mais les données utilisateur associées à ces conférences et contacts planifiés ne sont pas déplacées.</span><span class="sxs-lookup"><span data-stu-id="9179a-142">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="9179a-143">Pour déplacer des utilisateurs d’un pool vers un autre à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9179a-143">To move users from one pool to another using Windows PowerShell cmdlets</span></span>

1.  <span data-ttu-id="9179a-144">En fonction de la façon dont vous exécutez les commandes Windows PowerShell (localement ou à distance), vous devez vous connecter en tant que membre des rôles d’administrateur Lync Server 2013 appropriés comme suit :</span><span class="sxs-lookup"><span data-stu-id="9179a-144">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Lync Server 2013 administrative roles as follows:</span></span>
    
    1.  <span data-ttu-id="9179a-145">Si vous exécutez les commandes sur l’ordinateur local (par exemple, vous vous connectez directement à un serveur frontal) : Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9179a-145">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>
    
    2.  <span data-ttu-id="9179a-146">Si vous exécutez les commandes à distance sur un autre ordinateur (par exemple, vous ouvrez une session sur votre ordinateur et exécutez les commandes à distance sur un serveur frontal Standard Edition) : à partir d’un compte d’utilisateur affecté au rôle CsUserAdministrator ou à CsAdministrator , ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="9179a-146">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9179a-147">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9179a-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9179a-148">Pour déplacer des utilisateurs individuels, utilisez la cmdlet Move-CsUser comme suit :</span><span class="sxs-lookup"><span data-stu-id="9179a-148">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    <span data-ttu-id="9179a-149">Où l’utilisateur à déplacer est Pilar Ackerman, lequel sera déplacé depuis le pool d’accueil qui lui est actuellement affecté vers le pool pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="9179a-149">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>

4.  <span data-ttu-id="9179a-150">Pour déplacer un grand nombre d’utilisateurs, utilisez des filtres avec la cmdlet **Get-CsUser** et passez l’ensemble d’utilisateurs obtenu à **Move-CsUser** :</span><span class="sxs-lookup"><span data-stu-id="9179a-150">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    <span data-ttu-id="9179a-151">Les commandes combinées des cmdlets **Get-CsUser** et **Move-CsUser** peuvent donner le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="9179a-151">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9179a-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9179a-152">See Also</span></span>


[<span data-ttu-id="9179a-153">Modification des propriétés d’un compte d’utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9179a-153">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

<span data-ttu-id="9179a-154"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="9179a-154"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

