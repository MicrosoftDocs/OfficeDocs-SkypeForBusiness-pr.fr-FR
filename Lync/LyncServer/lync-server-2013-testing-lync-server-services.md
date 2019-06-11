---
title: 'Lync Server 2013: test des services Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b193473ad5941c647c572fae1b7cb5e7ece7f95d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a><span data-ttu-id="7293e-102">Test des services serveur Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7293e-102">Testing Lync Server services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7293e-103">_**Dernière modification de la rubrique:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="7293e-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7293e-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="7293e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7293e-105">Jour</span><span class="sxs-lookup"><span data-stu-id="7293e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7293e-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="7293e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7293e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7293e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7293e-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="7293e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7293e-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7293e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7293e-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="7293e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsComputer cmdlet.</span></span> <span data-ttu-id="7293e-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7293e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7293e-112">Description</span><span class="sxs-lookup"><span data-stu-id="7293e-112">Description</span></span>

<span data-ttu-id="7293e-113">Test-CsComputer vérifie l’état de tous les services Lync Server 2013 en cours d’exécution sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="7293e-113">Test-CsComputer verifies the status of all the Lync Server 2013 services that are running on the local computer.</span></span> <span data-ttu-id="7293e-114">(Test-CsComputer peut uniquement être exécuté localement, il ne peut pas être exécuté à partir d’une instance distante de Windows PowerShell.) L’applet de contrôle vérifie également si les ports de pare-feu appropriés sont ouverts sur l’ordinateur et détermine si les groupes Active Directory créés lors de l’installation de Lync Server 2013 ont été ajoutés aux groupes locaux correspondants.</span><span class="sxs-lookup"><span data-stu-id="7293e-114">(Test-CsComputer can only be run locally, it cannot be run from a remote instance of Windows PowerShell.) The cmdlet also checks whether the appropriate firewall ports are opened on the computer, and determines whether the Active Directory groups that were created when you installed Lync Server 2013 were added to the corresponding local groups.</span></span> <span data-ttu-id="7293e-115">Par exemple, test-CsComputer vérifie que le groupe Active Directory RTCUniversalUserAdmins a été ajouté au groupe administrateurs.</span><span class="sxs-lookup"><span data-stu-id="7293e-115">For example, Test-CsComputer will verify that the Active Directory group RTCUniversalUserAdmins was added to the Administrators group.</span></span>

<span data-ttu-id="7293e-116">Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .</span><span class="sxs-lookup"><span data-stu-id="7293e-116">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7293e-117">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="7293e-117">Running the test</span></span>

<span data-ttu-id="7293e-118">L’applet de commande test-CsComputer ne peut être exécutée que sur l’ordinateur local, vous ne pouvez pas appeler test-CsComputer à partir d’une instance distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7293e-118">The Test-CsComputer cmdlet can only be run on the local computer, you can't call Test-CsComputer from a remote instance of Windows PowerShell.</span></span> <span data-ttu-id="7293e-119">Par défaut, test-CsComputer affiche un faible niveau de sortie à l’écran, alors que les informations renvoyées par l’applet de contrôle sont écrites dans un fichier HTML.</span><span class="sxs-lookup"><span data-stu-id="7293e-119">By default, Test-CsComputer displays very little output on-screen, instead information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="7293e-120">Pour cette raison, nous vous recommandons d’inclure le paramètre Verbose et le paramètre de rapport chaque fois que vous exécutez test-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="7293e-120">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsComputer.</span></span> <span data-ttu-id="7293e-121">Le paramètre Verbose fournit un affichage à l’écran détaillé légèrement plus détaillé lors de l’exécution de la cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7293e-121">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="7293e-122">Le paramètre rapport vous permet de spécifier un chemin d’accès et un nom de fichier pour le fichier HTML généré par test-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="7293e-122">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsComputer.</span></span> <span data-ttu-id="7293e-123">Si vous n’incluez pas le paramètre de rapport, le fichier HTML sera automatiquement enregistré dans votre dossier utilisateurs et sera doté du nom semblable à ce qui suit: ce84964a-c4da-4622-ad34-c54ff3ed361f. html.</span><span class="sxs-lookup"><span data-stu-id="7293e-123">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="7293e-124">L’exemple de commande suivant exécute test-CsComputer et enregistre la sortie dans un fichier nommé C:\\logs\\ComputerTest. html:</span><span class="sxs-lookup"><span data-stu-id="7293e-124">The following sample command runs Test-CsComputer and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="7293e-125">Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .</span><span class="sxs-lookup"><span data-stu-id="7293e-125">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7293e-126">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="7293e-126">Determining success or failure</span></span>

<span data-ttu-id="7293e-127">Dans la mesure où le nombre de vérification vérifie qu’il effectue une opération, test-CsComputer n’indique pas une simple **valeur Oui, le test a réussi** ou **non**.</span><span class="sxs-lookup"><span data-stu-id="7293e-127">Because of the number of verification checks that it performs, Test-CsComputer does not report back a simple **Yes, the test succeeded** or **No, the test failed**.</span></span> <span data-ttu-id="7293e-128">Au lieu de cela, vous devez afficher le fichier HTML généré à l’aide d’Internet Explorer pour déterminer la réussite ou l’échec de chaque test.</span><span class="sxs-lookup"><span data-stu-id="7293e-128">Instead, you have to view the generated HTML file by using Internet Explorer to determine the success or failure of each test.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7293e-129">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="7293e-129">Reasons why the test might have failed</span></span>

<span data-ttu-id="7293e-130">Voici quelques raisons courantes pour lesquelles les tests-CsComputer peuvent échouer:</span><span class="sxs-lookup"><span data-stu-id="7293e-130">Here are some common reasons why Test-CsComputer might fail:</span></span>

  - <span data-ttu-id="7293e-131">L’ordinateur de test n’est peut-être pas activé pour une utilisation avec Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7293e-131">The test computer might not be enabled for use with Lync Server.</span></span> <span data-ttu-id="7293e-132">Cela peut se produire si les services serveur de Lync ou les rôles serveur sur l’ordinateur ont changé et que l’applet de CsComputer n’était pas exécutée.</span><span class="sxs-lookup"><span data-stu-id="7293e-132">This can occur if the Lync Server services or server roles on the computer have changed and the Enable-CsComputer cmdlet was not run.</span></span> <span data-ttu-id="7293e-133">Pour résoudre ce problème, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="7293e-133">To resolve this issue, run the following command:</span></span>
    
        Enable-CsComputer

  - <span data-ttu-id="7293e-134">La réplication n’est peut-être pas à jour sur l’ordinateur de test.</span><span class="sxs-lookup"><span data-stu-id="7293e-134">Replication might not be up to date on the test computer.</span></span> <span data-ttu-id="7293e-135">Vous pouvez vérifier l’état de réplication actuel d’un ordinateur en exécutant l’applet de contrôle Get-CsManagementStoreReplicationStatus:</span><span class="sxs-lookup"><span data-stu-id="7293e-135">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="7293e-136">Si l’état de la réplication n’est pas à jour, vous pouvez le faire manuellement en utilisant une commande similaire à celle-ci:</span><span class="sxs-lookup"><span data-stu-id="7293e-136">If the replication status is not up to date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="7293e-137">La topologie peut être activée.</span><span class="sxs-lookup"><span data-stu-id="7293e-137">The topology might have to be enabled.</span></span> <span data-ttu-id="7293e-138">Si vous modifiez la topologie du serveur Lync (modifications qui peuvent affecter l’ordinateur local), vous devez activer la nouvelle topologie.</span><span class="sxs-lookup"><span data-stu-id="7293e-138">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="7293e-139">Vous pouvez activer la topologie à tout moment en exécutant la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="7293e-139">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

