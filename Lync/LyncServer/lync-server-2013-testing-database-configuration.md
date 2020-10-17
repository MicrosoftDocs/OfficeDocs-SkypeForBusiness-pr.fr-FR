---
title: 'Lync Server 2013 : test de la configuration de base de données'
description: 'Lync Server 2013 : test de la configuration de la base de données.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b9f88eee99c4a2d523cc84df401dcc1d7b9fe59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560680"
---
# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="b5d12-103">Test de la configuration de la base de données dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5d12-103">Testing database configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5d12-104">_**Dernière modification de la rubrique :** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="b5d12-104">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5d12-105">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="b5d12-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b5d12-106">Journalière</span><span class="sxs-lookup"><span data-stu-id="b5d12-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d12-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="b5d12-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b5d12-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5d12-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d12-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="b5d12-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b5d12-110">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins et disposer de privilèges d’administrateur sur le serveur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b5d12-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="b5d12-111">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-applet csdatabase</strong> .</span><span class="sxs-lookup"><span data-stu-id="b5d12-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="b5d12-112">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="b5d12-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b5d12-113">Description</span><span class="sxs-lookup"><span data-stu-id="b5d12-113">Description</span></span>

<span data-ttu-id="b5d12-114">L’applet de commande **test-applet csdatabase** vérifie la connectivité avec une ou plusieurs bases de données Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5d12-114">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="b5d12-115">Lorsqu’elle est exécutée, l’applet de commande **test-applet csdatabase** lit la topologie Lync Server, tente de se connecter aux bases de données appropriées, puis signale la réussite ou l’échec de chaque tentative.</span><span class="sxs-lookup"><span data-stu-id="b5d12-115">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="b5d12-116">Si une connexion peut être établie, l’applet de commande fournit également des informations telles que le nom de la base de données, les informations de version SQL Server et l’emplacement des éventuelles bases de données miroir installées.</span><span class="sxs-lookup"><span data-stu-id="b5d12-116">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b5d12-117">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="b5d12-117">Running the test</span></span>

<span data-ttu-id="b5d12-118">La commande de l’exemple 1 vérifie la configuration de la base de données Central Management.</span><span class="sxs-lookup"><span data-stu-id="b5d12-118">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="b5d12-119">L’exemple 2 vérifie toutes les bases de données Lync Server installées sur l’ordinateur atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b5d12-119">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="b5d12-p103">Dans l’exemple 3, la vérification est exécutée uniquement pour la base de données Archiving installée sur l’ordinateur atl-sql-001.litwareinc.com. Notez que l’inclusion du paramètre SqlInstanceName permet de spécifier l’instance SQL Server (Archinst) où se trouve la base de données Archiving.</span><span class="sxs-lookup"><span data-stu-id="b5d12-p103">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com. Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="b5d12-122">La commande illustrée à l’exemple 4 vérifie les bases de données installées l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="b5d12-122">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b5d12-123">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="b5d12-123">Determining success or failure</span></span>

<span data-ttu-id="b5d12-124">Si la connectivité de la base de données est correctement configurée, vous recevrez un résultat similaire à celui-ci, avec la propriété réussite marquée **true**:</span><span class="sxs-lookup"><span data-stu-id="b5d12-124">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="b5d12-125">SqlServerFqdn : atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b5d12-125">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="b5d12-126">SqlInstanceName : RTC</span><span class="sxs-lookup"><span data-stu-id="b5d12-126">SqlInstanceName : rtc</span></span>

<span data-ttu-id="b5d12-127">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="b5d12-127">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="b5d12-128">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="b5d12-128">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="b5d12-129">DatabaseName : XDS</span><span class="sxs-lookup"><span data-stu-id="b5d12-129">DatabaseName : xds</span></span>

<span data-ttu-id="b5d12-130">Source</span><span class="sxs-lookup"><span data-stu-id="b5d12-130">DataSource :</span></span>

<span data-ttu-id="b5d12-131">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="b5d12-131">SQLServerVersion :</span></span>

<span data-ttu-id="b5d12-132">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="b5d12-132">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="b5d12-133">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="b5d12-133">InstalledVersion :</span></span>

<span data-ttu-id="b5d12-134">Réussite : true</span><span class="sxs-lookup"><span data-stu-id="b5d12-134">Succeed : True</span></span>

<span data-ttu-id="b5d12-135">SqlServerFqdn : atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b5d12-135">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="b5d12-136">SqlInstanceName : RTC</span><span class="sxs-lookup"><span data-stu-id="b5d12-136">SqlInstanceName : rtc</span></span>

<span data-ttu-id="b5d12-137">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="b5d12-137">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="b5d12-138">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="b5d12-138">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="b5d12-139">DatabaseName : lis</span><span class="sxs-lookup"><span data-stu-id="b5d12-139">DatabaseName : lis</span></span>

<span data-ttu-id="b5d12-140">Source</span><span class="sxs-lookup"><span data-stu-id="b5d12-140">DataSource :</span></span>

<span data-ttu-id="b5d12-141">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="b5d12-141">SQLServerVersion :</span></span>

<span data-ttu-id="b5d12-142">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="b5d12-142">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="b5d12-143">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="b5d12-143">InstalledVersion :</span></span>

<span data-ttu-id="b5d12-144">Réussite : true</span><span class="sxs-lookup"><span data-stu-id="b5d12-144">Succeed : True</span></span>

<span data-ttu-id="b5d12-145">Si la base de données est correctement configurée mais toujours disponible, le champ réussite affiche **false**et des avertissements et informations supplémentaires sont fournis :</span><span class="sxs-lookup"><span data-stu-id="b5d12-145">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="b5d12-146">SqlServerFqdn : atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b5d12-146">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="b5d12-147">SqlInstanceName : RTC</span><span class="sxs-lookup"><span data-stu-id="b5d12-147">SqlInstanceName : rtc</span></span>

<span data-ttu-id="b5d12-148">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="b5d12-148">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="b5d12-149">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="b5d12-149">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="b5d12-150">DatabaseName : XDS</span><span class="sxs-lookup"><span data-stu-id="b5d12-150">DatabaseName : xds</span></span>

<span data-ttu-id="b5d12-151">Source</span><span class="sxs-lookup"><span data-stu-id="b5d12-151">DataSource :</span></span>

<span data-ttu-id="b5d12-152">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="b5d12-152">SQLServerVersion :</span></span>

<span data-ttu-id="b5d12-153">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="b5d12-153">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="b5d12-154">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="b5d12-154">InstalledVersion :</span></span>

<span data-ttu-id="b5d12-155">Réussite : false</span><span class="sxs-lookup"><span data-stu-id="b5d12-155">Succeed : False</span></span>

<span data-ttu-id="b5d12-156">SqlServerFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b5d12-156">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b5d12-157">SqlInstanceName : RTC</span><span class="sxs-lookup"><span data-stu-id="b5d12-157">SqlInstanceName : rtc</span></span>

<span data-ttu-id="b5d12-158">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="b5d12-158">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="b5d12-159">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="b5d12-159">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="b5d12-160">DatabaseName : lis</span><span class="sxs-lookup"><span data-stu-id="b5d12-160">DatabaseName : lis</span></span>

<span data-ttu-id="b5d12-161">Source</span><span class="sxs-lookup"><span data-stu-id="b5d12-161">DataSource :</span></span>

<span data-ttu-id="b5d12-162">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="b5d12-162">SQLServerVersion :</span></span>

<span data-ttu-id="b5d12-163">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="b5d12-163">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="b5d12-164">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="b5d12-164">InstalledVersion :</span></span>

<span data-ttu-id="b5d12-165">Réussite : false</span><span class="sxs-lookup"><span data-stu-id="b5d12-165">Succeed : False</span></span>

<span data-ttu-id="b5d12-166">AVERTISSEMENT : Test-CsDatabase rencontré des erreurs.</span><span class="sxs-lookup"><span data-stu-id="b5d12-166">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="b5d12-167">Consulter le fichier journal pour un</span><span class="sxs-lookup"><span data-stu-id="b5d12-167">Consult the log file for a</span></span>

<span data-ttu-id="b5d12-168">analyse détaillée et vérification de la prise en compte de toutes les erreurs (2) et avertissements (0)</span><span class="sxs-lookup"><span data-stu-id="b5d12-168">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="b5d12-169">avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="b5d12-169">before continuing.</span></span>

<span data-ttu-id="b5d12-170">AVERTISSEMENT : les résultats détaillés sont disponibles à l’adresse</span><span class="sxs-lookup"><span data-stu-id="b5d12-170">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="b5d12-171">"C : \\ Users \\ testing \\ AppData \\ local \\ temp \\ 2 \\ test-applet csdatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="b5d12-171">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="b5d12-172">04d593cce8e6.html».</span><span class="sxs-lookup"><span data-stu-id="b5d12-172">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b5d12-173">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="b5d12-173">Reasons why the test might have failed</span></span>

<span data-ttu-id="b5d12-174">Voici quelques-unes des causes courantes de l’échec **de test-applet csdatabase** :</span><span class="sxs-lookup"><span data-stu-id="b5d12-174">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="b5d12-175">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="b5d12-175">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="b5d12-176">Si ce paramètre est utilisé, les paramètres facultatifs doivent être configurés correctement ou le test échoue.</span><span class="sxs-lookup"><span data-stu-id="b5d12-176">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="b5d12-177">Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.</span><span class="sxs-lookup"><span data-stu-id="b5d12-177">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="b5d12-178">Cette commande échoue si la base de données n’est pas configurée correctement ou n’est pas encore déployée.</span><span class="sxs-lookup"><span data-stu-id="b5d12-178">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b5d12-179">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b5d12-179">See Also</span></span>


[<span data-ttu-id="b5d12-180">Get-CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="b5d12-180">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="b5d12-181">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="b5d12-181">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="b5d12-182">Get-CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="b5d12-182">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

