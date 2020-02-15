---
title: 'Lync Server 2013 : test des services Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd9f2924d2f66e27e3893ccca0502915ee8a3e97
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a><span data-ttu-id="b2a61-102">Test des services Lync Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2a61-102">Testing Lync Server services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2a61-103">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="b2a61-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2a61-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="b2a61-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b2a61-105">Tous les jours</span><span class="sxs-lookup"><span data-stu-id="b2a61-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2a61-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="b2a61-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b2a61-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2a61-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2a61-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="b2a61-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b2a61-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b2a61-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b2a61-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="b2a61-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsComputer cmdlet.</span></span> <span data-ttu-id="b2a61-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="b2a61-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b2a61-112">Description</span><span class="sxs-lookup"><span data-stu-id="b2a61-112">Description</span></span>

<span data-ttu-id="b2a61-113">Test-CsComputer vérifie l’état de tous les services Lync Server 2013 en cours d’exécution sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="b2a61-113">Test-CsComputer verifies the status of all the Lync Server 2013 services that are running on the local computer.</span></span> <span data-ttu-id="b2a61-114">(Test-CsComputer peut uniquement être exécuté localement, il ne peut pas être exécuté à partir d’une instance distante de Windows PowerShell.) L’applet de commande vérifie également si les ports de pare-feu appropriés sont ouverts sur l’ordinateur et détermine si les groupes Active Directory créés lors de l’installation de Lync Server 2013 ont été ajoutés aux groupes locaux correspondants.</span><span class="sxs-lookup"><span data-stu-id="b2a61-114">(Test-CsComputer can only be run locally, it cannot be run from a remote instance of Windows PowerShell.) The cmdlet also checks whether the appropriate firewall ports are opened on the computer, and determines whether the Active Directory groups that were created when you installed Lync Server 2013 were added to the corresponding local groups.</span></span> <span data-ttu-id="b2a61-115">Par exemple, test-CsComputer vérifiera que le groupe Active Directory RTCUniversalUserAdmins a été ajouté au groupe administrateurs.</span><span class="sxs-lookup"><span data-stu-id="b2a61-115">For example, Test-CsComputer will verify that the Active Directory group RTCUniversalUserAdmins was added to the Administrators group.</span></span>

<span data-ttu-id="b2a61-116">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .</span><span class="sxs-lookup"><span data-stu-id="b2a61-116">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b2a61-117">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="b2a61-117">Running the test</span></span>

<span data-ttu-id="b2a61-118">La cmdlet Test-CsComputer ne peut être exécutée que sur l’ordinateur local, vous ne pouvez pas appeler test-CsComputer à partir d’une instance distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2a61-118">The Test-CsComputer cmdlet can only be run on the local computer, you can't call Test-CsComputer from a remote instance of Windows PowerShell.</span></span> <span data-ttu-id="b2a61-119">Par défaut, test-CsComputer affiche très peu de sortie à l’écran, et les informations renvoyées par l’applet de commande sont écrites dans un fichier HTML.</span><span class="sxs-lookup"><span data-stu-id="b2a61-119">By default, Test-CsComputer displays very little output on-screen, instead information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="b2a61-120">Pour cette raison, nous vous recommandons d’inclure le paramètre Verbose et le paramètre report à chaque fois que vous exécutez la commande test-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="b2a61-120">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsComputer.</span></span> <span data-ttu-id="b2a61-121">Le paramètre Verbose fournira une sortie plus détaillée à l’écran pendant l’exécution de l’applet de commande.</span><span class="sxs-lookup"><span data-stu-id="b2a61-121">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="b2a61-122">Le paramètre Report vous permet de spécifier un chemin d’accès et un nom de fichier pour le fichier HTML généré par test-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="b2a61-122">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsComputer.</span></span> <span data-ttu-id="b2a61-123">Si vous n’incluez pas le paramètre Report, le fichier HTML est automatiquement enregistré dans votre dossier Users et reçoit un nom semblable à celui-ci : ce84964a-c4da-4622-ad34-c54ff3ed361f. html.</span><span class="sxs-lookup"><span data-stu-id="b2a61-123">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="b2a61-124">L’exemple de commande suivant exécute test-CsComputer et enregistre la sortie dans un fichier nommé C :\\logs\\ComputerTest. html :</span><span class="sxs-lookup"><span data-stu-id="b2a61-124">The following sample command runs Test-CsComputer and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="b2a61-125">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .</span><span class="sxs-lookup"><span data-stu-id="b2a61-125">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b2a61-126">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="b2a61-126">Determining success or failure</span></span>

<span data-ttu-id="b2a61-127">En raison du nombre de vérifications de vérification effectuées, test-CsComputer n’indique pas de simple **Oui, le test a réussi** ou **non, le test a échoué**.</span><span class="sxs-lookup"><span data-stu-id="b2a61-127">Because of the number of verification checks that it performs, Test-CsComputer does not report back a simple **Yes, the test succeeded** or **No, the test failed**.</span></span> <span data-ttu-id="b2a61-128">Au lieu de cela, vous devez afficher le fichier HTML généré à l’aide d’Internet Explorer pour déterminer la réussite ou l’échec de chaque test.</span><span class="sxs-lookup"><span data-stu-id="b2a61-128">Instead, you have to view the generated HTML file by using Internet Explorer to determine the success or failure of each test.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b2a61-129">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="b2a61-129">Reasons why the test might have failed</span></span>

<span data-ttu-id="b2a61-130">Voici quelques-unes des causes courantes de l’échec de test-CsComputer :</span><span class="sxs-lookup"><span data-stu-id="b2a61-130">Here are some common reasons why Test-CsComputer might fail:</span></span>

  - <span data-ttu-id="b2a61-131">L’ordinateur de test n’est peut-être pas activé pour une utilisation avec Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b2a61-131">The test computer might not be enabled for use with Lync Server.</span></span> <span data-ttu-id="b2a61-132">Cela peut se produire si les services ou les rôles serveur Lync Server sur l’ordinateur ont changé et que la cmdlet Enable-CsComputer n’a pas été exécutée.</span><span class="sxs-lookup"><span data-stu-id="b2a61-132">This can occur if the Lync Server services or server roles on the computer have changed and the Enable-CsComputer cmdlet was not run.</span></span> <span data-ttu-id="b2a61-133">Pour résoudre ce problème, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b2a61-133">To resolve this issue, run the following command:</span></span>
    
        Enable-CsComputer

  - <span data-ttu-id="b2a61-134">La réplication n’est peut-être pas à jour sur l’ordinateur de test.</span><span class="sxs-lookup"><span data-stu-id="b2a61-134">Replication might not be up to date on the test computer.</span></span> <span data-ttu-id="b2a61-135">Vous pouvez vérifier l’état de réplication actuel d’un ordinateur en exécutant la cmdlet Get-CsManagementStoreReplicationStatus :</span><span class="sxs-lookup"><span data-stu-id="b2a61-135">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="b2a61-136">Si le statut de la réplication n’est pas à jour, vous pouvez forcer manuellement la réplication à l’aide d’une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="b2a61-136">If the replication status is not up to date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="b2a61-137">Il se peut que vous deviez activer la topologie.</span><span class="sxs-lookup"><span data-stu-id="b2a61-137">The topology might have to be enabled.</span></span> <span data-ttu-id="b2a61-138">Si vous modifiez la topologie Lync Server (modifications susceptibles d’affecter l’ordinateur local), vous devez activer la nouvelle topologie.</span><span class="sxs-lookup"><span data-stu-id="b2a61-138">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="b2a61-139">Vous pouvez activer la topologie à tout moment en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b2a61-139">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

