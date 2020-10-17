---
title: 'Lync Server 2013 : autorisations d’administrateur de test'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1653f2287e06db71f6e971a0a4f483b810734f2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519381"
---
# <a name="test-admin-permissions-in-lync-server-2013"></a><span data-ttu-id="43944-102">Tester les autorisations d’administration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43944-102">Test admin permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43944-103">_**Dernière modification de la rubrique :** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="43944-103">_**Topic Last Modified:** 2014-08-18_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43944-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="43944-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="43944-105">Après le déploiement initial de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43944-105">After initial Lync Server deployment.</span></span> <span data-ttu-id="43944-106">Le cas échéant, si des problèmes liés aux autorisations se produisent.</span><span class="sxs-lookup"><span data-stu-id="43944-106">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43944-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="43944-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="43944-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="43944-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43944-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="43944-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="43944-110">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="43944-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="43944-111">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="43944-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="43944-112">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="43944-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="43944-113">Description</span><span class="sxs-lookup"><span data-stu-id="43944-113">Description</span></span>

<span data-ttu-id="43944-114">Lorsque vous installez Lync Server 2013 1 des tâches effectuées par le programme d’installation donne au groupe RTCUniversalUserAdmins les autorisations Active Directory nécessaires pour gérer les utilisateurs, les ordinateurs, les contacts, les contacts d’application et les personnes InetOrg.</span><span class="sxs-lookup"><span data-stu-id="43944-114">When you install Lync Server 2013 one of the tasks that were performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="43944-115">Si vous avez désactivé l’héritage des autorisations dans le programme d’installation d’Active Directory, vous ne pourrez pas attribuer ces autorisations.</span><span class="sxs-lookup"><span data-stu-id="43944-115">If you have disabled permission inheritance in Active Directory setup won't be able to assign those permissions.</span></span> <span data-ttu-id="43944-116">Par conséquent, les membres du groupe RTCUniversalUserAdmins ne pourront pas gérer les entités Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43944-116">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Lync Server entities.</span></span> <span data-ttu-id="43944-117">Ces privilèges de gestion ne seront accessibles qu’aux administrateurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="43944-117">Those management privileges will only be available to domain administrators.</span></span>

<span data-ttu-id="43944-118">L’applet de commande Test-CsOUPermission vérifie que les autorisations requises pour gérer les utilisateurs, les ordinateurs et les autres objets sont définies sur un conteneur Active Directory.</span><span class="sxs-lookup"><span data-stu-id="43944-118">The Test-CsOUPermission cmdlet verifies that the required permissions that are needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="43944-119">Si ces autorisations ne sont pas définies, vous pouvez résoudre ce problème en exécutant l’applet de commande [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) .</span><span class="sxs-lookup"><span data-stu-id="43944-119">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet.</span></span>

<span data-ttu-id="43944-120">Notez que les Grant-CsOUPermission peuvent uniquement attribuer des autorisations aux membres du groupe RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="43944-120">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="43944-121">Vous ne pouvez pas utiliser cette applet de commande pour accorder des autorisations à un utilisateur ou un groupe arbitraire.</span><span class="sxs-lookup"><span data-stu-id="43944-121">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="43944-122">Si vous souhaitez qu’un autre utilisateur ou groupe dispose des autorisations de gestion des utilisateurs, vous devez ajouter cet utilisateur (ou ce groupe) au groupe RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="43944-122">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span>

<span data-ttu-id="43944-123">Pour plus d’informations sur les autorisations d’unité d’organisation, voir l’article [héritage des autorisations est désactivé sur les conteneurs ordinateurs, utilisateurs ou InetOrgPerson dans Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span><span class="sxs-lookup"><span data-stu-id="43944-123">For more information on OU permissions, see the article [Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="43944-124">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="43944-124">Running the test</span></span>

<span data-ttu-id="43944-125">Pour vérifier que les autorisations de gestion sont définies sur un conteneur, exécutez l’applet de commande Test-CsOUPermission suivi du nom unique du conteneur et du type d’autorisations que vous vérifiez.</span><span class="sxs-lookup"><span data-stu-id="43944-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="43944-126">Par exemple, cette commande vérifie si les autorisations de l’utilisateur sont définies sur l’unité d’organisation OU = Redmond, DC = litwareinc, DC = com :</span><span class="sxs-lookup"><span data-stu-id="43944-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

<span data-ttu-id="43944-127">Pour vérifier plusieurs autorisations à l’aide d’une seule commande, placez chaque type d’autorisation entre guillemets, puis séparez ces types à l’aide de virgules.</span><span class="sxs-lookup"><span data-stu-id="43944-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="43944-128">Par exemple, cette commande vérifie les autorisations utilisateur, ordinateur et contact :</span><span class="sxs-lookup"><span data-stu-id="43944-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

<span data-ttu-id="43944-129">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .</span><span class="sxs-lookup"><span data-stu-id="43944-129">For more information, see the help topic for the [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="43944-130">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="43944-130">Determining success or failure</span></span>

<span data-ttu-id="43944-131">Si les autorisations requises ont déjà été définies, Test-CsOUPermission renverra une réponse à un mot :</span><span class="sxs-lookup"><span data-stu-id="43944-131">If the required permissions have already been set then Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="43944-132">Vrai</span><span class="sxs-lookup"><span data-stu-id="43944-132">True</span></span>

<span data-ttu-id="43944-133">Si les autorisations requises ne sont pas définies, Test-CsOUPermission renverra la valeur false.</span><span class="sxs-lookup"><span data-stu-id="43944-133">If the required permissions are not set then Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="43944-134">Il se peut que vous deviez rechercher un moment pour trouver cette valeur.</span><span class="sxs-lookup"><span data-stu-id="43944-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="43944-135">Elle est généralement incorporée dans plusieurs avertissements associés.</span><span class="sxs-lookup"><span data-stu-id="43944-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="43944-136">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="43944-136">For example:</span></span>

<span data-ttu-id="43944-137">AVERTISSEMENT : entrée de contrôle d’accès (ACE) ATL-CS-001 \\ RTCUniversalUserReadOnlyGroup ; allow ; Readpropertywriteproperty ContainerInherit; Descendants bf967aba-0de6-11D0-00aa003049e2 ; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="43944-137">WARNING: access control entry (ACE) atl-cs-001\\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span>

<span data-ttu-id="43944-138">AVERTISSEMENT : les entrées de contrôle d’accès (ACE) sur l’objet "OU = AmeriqueduNord, DC = ATL-CS-001 \\ DC = litwareinc, DC = com" ne sont pas prêtes.</span><span class="sxs-lookup"><span data-stu-id="43944-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\\DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="43944-139">False</span><span class="sxs-lookup"><span data-stu-id="43944-139">False</span></span>

<span data-ttu-id="43944-140">AVERTISSEMENT : le traitement de « test-CsOUPermission » s’est terminé avec des avertissements.</span><span class="sxs-lookup"><span data-stu-id="43944-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="43944-141">les avertissements « 2 » ont été enregistrés pendant cette exécution.</span><span class="sxs-lookup"><span data-stu-id="43944-141">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="43944-142">AVERTISSEMENT : vous trouverez des résultats détaillés à la page « C : \\ Users \\ admin \\ AppData \\ local \\ temp \\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html ».</span><span class="sxs-lookup"><span data-stu-id="43944-142">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="43944-143">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="43944-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="43944-144">Si Test-CsOUPermission échoue, cela signifie généralement que l’autorisation spécifiée n’a pas été affectée au groupe RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="43944-144">If Test-CsOUPermission fails that will usually mean that the specified permission has not been assign to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="43944-145">Vous pouvez résoudre ce problème et attribuer les autorisations requises à l’aide de l’applet de commande Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="43944-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="43944-146">Par exemple, cette commande donne des autorisations d’unité d’organisation pour les utilisateurs, contacts et inetOrgPersons au groupe RTCUniversalUserAdmins :</span><span class="sxs-lookup"><span data-stu-id="43944-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

<span data-ttu-id="43944-147">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="43944-147">For more information, see the help topic for the Grant-CsOUPermission cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

