---
title: 'Lync Server 2013 : test de l’activation de service et des autorisations de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38bc988ec1fdfeb0c4fd5714f31342902fe45821
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a><span data-ttu-id="0c7d0-102">Test de l’activation de service et des autorisations de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c7d0-102">Testing service activation and group permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c7d0-103">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="0c7d0-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c7d0-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="0c7d0-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0c7d0-105">Tous les jours</span><span class="sxs-lookup"><span data-stu-id="0c7d0-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c7d0-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="0c7d0-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0c7d0-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c7d0-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c7d0-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="0c7d0-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0c7d0-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0c7d0-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0c7d0-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="0c7d0-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTopology cmdlet.</span></span> <span data-ttu-id="0c7d0-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="0c7d0-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0c7d0-112">Description</span><span class="sxs-lookup"><span data-stu-id="0c7d0-112">Description</span></span>

<span data-ttu-id="0c7d0-113">L’applet de commande test-CsTopology vous permet de vérifier que Lync Server 2013 fonctionne correctement dans une étendue globale.</span><span class="sxs-lookup"><span data-stu-id="0c7d0-113">The Test-CsTopology cmdlet enables you to verify that Lync Server 2013 is functioning correctly at a global scope.</span></span> <span data-ttu-id="0c7d0-114">Par défaut, l’applet de commande vérifie l’ensemble de votre infrastructure Lync Server, en vérifiant que les services requis sont en cours d’exécution et que les autorisations appropriées sont définies pour ces services et pour les groupes de sécurité universels créés lors de l’installation de Lync Server .</span><span class="sxs-lookup"><span data-stu-id="0c7d0-114">By default, the cmdlet checks your whole Lync Server infrastructure, verifying that the required services are running and that the appropriate permissions are set for these services and for the universal security groups that are created when you install Lync Server.</span></span>

<span data-ttu-id="0c7d0-115">En plus de vérifier la validité de l’installation de Lync Server, test-CsTopology vous permet également de vérifier la validité d’un service spécifique.</span><span class="sxs-lookup"><span data-stu-id="0c7d0-115">In addition to verifying the validity of the Lync Server installation, Test-CsTopology also lets you check the validity of a specific service.</span></span> <span data-ttu-id="0c7d0-116">Par exemple, cette commande vérifie l’état du serveur de conférence A/V sur le pool atl-cs-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="0c7d0-116">For example, this command checks the state of the A/V Conferencing Server on the pool atl-cs-001.litwareinc.com:</span></span>

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0c7d0-117">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="0c7d0-117">Running the test</span></span>

<span data-ttu-id="0c7d0-118">Par défaut, test-CsTopology affiche une très petite sortie à l’écran.</span><span class="sxs-lookup"><span data-stu-id="0c7d0-118">By default, Test-CsTopology displays very little output on-screen.</span></span> <span data-ttu-id="0c7d0-119">Au lieu de cela, les informations renvoyées par l’applet de commande sont écrites dans un fichier HTML.</span><span class="sxs-lookup"><span data-stu-id="0c7d0-119">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="0c7d0-120">Le paramètre Report vous permet de spécifier un chemin d’accès et un nom de fichier pour le fichier HTML généré par test-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="0c7d0-120">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsTopology.</span></span> <span data-ttu-id="0c7d0-121">Si vous n’incluez pas le paramètre Report, le fichier HTML est automatiquement enregistré dans votre dossier Users et reçoit un nom semblable à celui-ci : ce84964a-c4da-4622-ad34-c54ff3ed361f. html.</span><span class="sxs-lookup"><span data-stu-id="0c7d0-121">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="0c7d0-122">L’exemple de commande suivant exécute test-CsTopology et enregistre la sortie dans un fichier nommé C :\\logs\\ComputerTest. html :</span><span class="sxs-lookup"><span data-stu-id="0c7d0-122">The following sample command runs Test-CsTopology and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="0c7d0-123">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) .</span><span class="sxs-lookup"><span data-stu-id="0c7d0-123">For more information, see the Help documentation for the [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0c7d0-124">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="0c7d0-124">Determining success or failure</span></span>

<span data-ttu-id="0c7d0-125">Contrairement à la plupart des applets de commande de test, test-CsTopology renvoie la réussite ou l’échec.</span><span class="sxs-lookup"><span data-stu-id="0c7d0-125">Unlike most of the test cmdlets, Test-CsTopology does report back Success or Failure.</span></span> <span data-ttu-id="0c7d0-126">En partie, cela est dû à un grand nombre de contrôles de vérification que l’applet de commande doit effectuer chaque fois qu’elle est exécutée.</span><span class="sxs-lookup"><span data-stu-id="0c7d0-126">In part, that’s due to the large number of verification checks that the cmdlet must make every time that it runs.</span></span> <span data-ttu-id="0c7d0-127">Au lieu de cela, les données sont enregistrées dans un rapport HTML qui peut être affiché à l’aide d’Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="0c7d0-127">Instead, data is saved to an HTML report that can then be viewed by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0c7d0-128">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="0c7d0-128">Reasons why the test might have failed</span></span>

<span data-ttu-id="0c7d0-129">Voici quelques-unes des causes courantes de l’échec de test-CsTopology :</span><span class="sxs-lookup"><span data-stu-id="0c7d0-129">Here are some common reasons why Test-CsTopology might fail:</span></span>

  - <span data-ttu-id="0c7d0-130">La réplication n’est peut-être pas à jour sur l’ordinateur de test.</span><span class="sxs-lookup"><span data-stu-id="0c7d0-130">Replication might not be up-to-date on the test computer.</span></span> <span data-ttu-id="0c7d0-131">Vous pouvez vérifier l’état de réplication actuel d’un ordinateur en exécutant la cmdlet Get-CsManagementStoreReplicationStatus :</span><span class="sxs-lookup"><span data-stu-id="0c7d0-131">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="0c7d0-132">Si l’état de la réplication n’est pas à jour, vous pouvez forcer manuellement la réplication à l’aide d’une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="0c7d0-132">If the replication status is not up-to-date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="0c7d0-133">Il se peut que vous deviez activer la topologie.</span><span class="sxs-lookup"><span data-stu-id="0c7d0-133">The topology might have to be enabled.</span></span> <span data-ttu-id="0c7d0-134">Si vous modifiez la topologie Lync Server (modifications susceptibles d’affecter l’ordinateur local), vous devez activer la nouvelle topologie.</span><span class="sxs-lookup"><span data-stu-id="0c7d0-134">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="0c7d0-135">Vous pouvez activer la topologie à tout moment en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="0c7d0-135">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

