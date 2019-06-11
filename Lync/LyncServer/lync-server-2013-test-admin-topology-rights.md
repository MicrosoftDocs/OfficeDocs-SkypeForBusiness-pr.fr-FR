---
title: 'Lync Server 2013: tester les droits du topologie d’administrateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 365c879678ff3fd51dcaaf89d4b2593eccf645f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a><span data-ttu-id="17a65-102">Test de droits de topologie d’administrateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17a65-102">Test admin topology rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17a65-103">_**Dernière modification de la rubrique:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="17a65-103">_**Topic Last Modified:** 2016-12-08_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17a65-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="17a65-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="17a65-105">Après le déploiement initial de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="17a65-105">After initial Lync Server deployment.</span></span> <span data-ttu-id="17a65-106">Le cas échéant, en cas de problèmes liés aux autorisations.</span><span class="sxs-lookup"><span data-stu-id="17a65-106">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17a65-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="17a65-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="17a65-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="17a65-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17a65-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="17a65-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="17a65-110">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="17a65-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="17a65-111">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="17a65-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="17a65-112">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="17a65-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="17a65-113">Description</span><span class="sxs-lookup"><span data-stu-id="17a65-113">Description</span></span>

<span data-ttu-id="17a65-114">Par défaut, seuls les administrateurs de domaine peuvent activer une topologie de serveur Lync et apporter des modifications importantes à l’infrastructure du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="17a65-114">By default, only domain administrators can enable a Lync Server topology and make large changes to the Lync Server infrastructure.</span></span> <span data-ttu-id="17a65-115">Ce n’est pas un problème tant que les administrateurs de domaine et les administrateurs de votre serveur Lync sont les mêmes. Dans de nombreuses organisations, les administrateurs serveur Lync ne disposent pas des droits d’administration sur l’ensemble du domaine.</span><span class="sxs-lookup"><span data-stu-id="17a65-115">This won't be a problem as long as your domain administrators and your Lync Server administrators are one and the same.In many organizations Lync Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="17a65-116">Par défaut, cela signifie que ces administrateurs (définis en tant que membres du groupe RTCUniversalServerAdmins) ne peuvent pas apporter de modifications à la topologie Lync Server.</span><span class="sxs-lookup"><span data-stu-id="17a65-116">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Lync Server topology changes.</span></span> <span data-ttu-id="17a65-117">Pour donner aux membres du groupe RTCUniversalServerAdmins l’autorisation de modifier la topologie, vous devez affecter les autorisations Active Directory requises à l’aide de l’applet de contrôle [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="17a65-117">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>

<span data-ttu-id="17a65-118">L’applet de contrôle test-CsSetupPermission vérifie que les autorisations requises pour installer Lync Server ou l’un de ses composants sont configurées sur le conteneur Active Directory spécifié.</span><span class="sxs-lookup"><span data-stu-id="17a65-118">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Lync Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="17a65-119">Si les autorisations ne sont pas affectées, vous pouvez ensuite exécuter l’applet de passe Grant-CsSetupPermission pour donner aux membres du groupe RTCUniversalServerAdmins le droit d’installer et d’activer Lync Server.</span><span class="sxs-lookup"><span data-stu-id="17a65-119">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17a65-120">Pour obtenir la liste détaillée des autorisations attribuées par Grant-CsSetupPermission, reportez-vous à la rubrique Grant- <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">CsSetupPermission and Grant-CsOUPermission</A>du billet de blog.</span><span class="sxs-lookup"><span data-stu-id="17a65-120">For a detailed list of permissions assigned by Grant-CsSetupPermission, see the blog post <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission and Grant-CsOUPermission</A>.</span></span>



</div>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="17a65-121">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="17a65-121">Running the test</span></span>

<span data-ttu-id="17a65-122">Pour déterminer si des autorisations de configuration sont affectées pour un conteneur Active Directory, appelez l’applet de contrôle test-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="17a65-122">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="17a65-123">Spécifiez le nom unique du conteneur à vérifier.</span><span class="sxs-lookup"><span data-stu-id="17a65-123">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="17a65-124">Par exemple, cette commande vérifie les autorisations de configuration sur le conteneur ou = CsServers, DC = litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="17a65-124">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

<span data-ttu-id="17a65-125">Pour plus d’informations, consultez la rubrique d’aide de l’applet de [contrôle test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="17a65-125">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="17a65-126">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="17a65-126">Determining success or failure</span></span>

<span data-ttu-id="17a65-127">Si test-CsSetupPermission détermine que les autorisations requises ont déjà été définies sur un conteneur Active Directory, l’applet de contrôle renverra la valeur true:</span><span class="sxs-lookup"><span data-stu-id="17a65-127">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="17a65-128">True</span><span class="sxs-lookup"><span data-stu-id="17a65-128">True</span></span>

<span data-ttu-id="17a65-129">Si les autorisations ne sont pas définies, testez-CsSetupPermission renverra la valeur false.</span><span class="sxs-lookup"><span data-stu-id="17a65-129">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="17a65-130">Notez que cette valeur est généralement incluse dans de nombreux messages d’avertissement.</span><span class="sxs-lookup"><span data-stu-id="17a65-130">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="17a65-131">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="17a65-131">For example:</span></span>

<span data-ttu-id="17a65-132">AVERTISSEMENT: entrée de contrôle d’accès (ACE) ATL-cs\\-001 RTCUniversalServerAdmins; Verte ExtendedRight; Néant Néant 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="17a65-132">WARNING: Access control entry (ACE) atl-cs-001\\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span>

<span data-ttu-id="17a65-133">AVERTISSEMENT: les entrées de contrôle d’accès (ACE) sur l’objet «CN = ordinateurs, DC = litwareinc, DC = com» ne sont pas prêtes.</span><span class="sxs-lookup"><span data-stu-id="17a65-133">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="17a65-134">False</span><span class="sxs-lookup"><span data-stu-id="17a65-134">False</span></span>

<span data-ttu-id="17a65-135">AVERTISSEMENT: le traitement des «tests-CsSetupPermission» s’est terminé avec des avertissements.</span><span class="sxs-lookup"><span data-stu-id="17a65-135">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="17a65-136">des avertissements "2" ont été enregistrés lors de cette exécution.</span><span class="sxs-lookup"><span data-stu-id="17a65-136">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="17a65-137">AVERTISSEMENT: des résultats détaillés sont disponibles à l’adresse\\suivante\\:\\«\\C\\:\\Users admin AppData Local Temp test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118. html».</span><span class="sxs-lookup"><span data-stu-id="17a65-137">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="17a65-138">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="17a65-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="17a65-139">Même s’il existe des exceptions rares, en cas de test-CsSetupPermission, cela signifie que les autorisations de configuration ne sont pas affectées pour le conteneur Active Directory spécifié.</span><span class="sxs-lookup"><span data-stu-id="17a65-139">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="17a65-140">Ces autorisations peuvent être affectées à l’aide de l’applet de passe Grant-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="17a65-140">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="17a65-141">Par exemple, cette commande accorde des autorisations de configuration au conteneur ordinateurs dans le domaine litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="17a65-141">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

<span data-ttu-id="17a65-142">Pour plus d’informations, consultez la rubrique d’aide de l’applet de [contrôle test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="17a65-142">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

