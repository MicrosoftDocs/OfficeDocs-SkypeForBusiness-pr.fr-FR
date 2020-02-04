---
title: 'Lync Server 2013 : affichage de l’état des services en cours d’exécution sur un ordinateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 984f85fca13704864b3cd47c83e8f6adca575705
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a><span data-ttu-id="4fc0e-102">Afficher l’état des services en cours d’exécution sur un ordinateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fc0e-102">View the status of services running on a computer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fc0e-103">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="4fc0e-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="4fc0e-104">Vous pouvez utiliser le panneau de configuration de Lync Server 2013 pour afficher tous les services en cours d’exécution sur un ordinateur spécifique dans la topologie de votre serveur Lync et afficher l’état de chaque service.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-104">You can use Lync Server 2013 Control Panel to view all the services that are running on a specific computer in your Lync Server topology and see the status of each service.</span></span>

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="4fc0e-105">Pour afficher l’état des services en cours d’exécution sur un ordinateur</span><span class="sxs-lookup"><span data-stu-id="4fc0e-105">To view the status of services running on a computer</span></span>

1.  <span data-ttu-id="4fc0e-106">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4fc0e-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4fc0e-108">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4fc0e-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4fc0e-109">Dans la barre de navigation de gauche, cliquez sur **Topology**.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-109">In the left navigation bar, click **Topology**.</span></span>

4.  <span data-ttu-id="4fc0e-110">Dans la page **État** , triez ou effectuez une recherche dans la liste, si nécessaire, pour trouver l’ordinateur qui vous intéresse, puis cliquez sur le nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-110">On the **Status** page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>

5.  <span data-ttu-id="4fc0e-111">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4fc0e-111">Do any of the following:</span></span>
    
      - <span data-ttu-id="4fc0e-112">Pour afficher le dernier état des services en cours d’exécution sur l’ordinateur, cliquez sur **obtenir l’état du service**.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-112">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    
      - <span data-ttu-id="4fc0e-113">Pour afficher une liste de services spécifiques en cours d’exécution sur l’ordinateur et l’état de chaque service, cliquez sur **Propriétés**, puis sur **Fermer** pour revenir à la liste.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-113">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4fc0e-114">Affichage de l’état du service à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fc0e-114">Viewing Service Status by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4fc0e-115">Vous pouvez également afficher l’état du service à l’aide de Windows PowerShell et de l’applet **de connexion Get-CsWindowsService** .</span><span class="sxs-lookup"><span data-stu-id="4fc0e-115">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="4fc0e-116">Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4fc0e-117">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="4fc0e-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-service-status"></a><span data-ttu-id="4fc0e-118">Pour afficher l’état du service</span><span class="sxs-lookup"><span data-stu-id="4fc0e-118">To view service status</span></span>

  - <span data-ttu-id="4fc0e-119">Pour afficher l’état du service sur un ordinateur, tapez une commande similaire à celle qui suit dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="4fc0e-119">To view service status on a computer, type a command similar to the following in the Lync Server Management Shell and then press Enter:</span></span>
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    <span data-ttu-id="4fc0e-120">Cette commande renvoie le type d’informations suivant :</span><span class="sxs-lookup"><span data-stu-id="4fc0e-120">This command returns information similar to the following:</span></span>
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

</div>

<span data-ttu-id="4fc0e-121">Pour plus d’informations, consultez la rubrique [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span><span class="sxs-lookup"><span data-stu-id="4fc0e-121">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4fc0e-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4fc0e-122">See Also</span></span>


[<span data-ttu-id="4fc0e-123">Gestion des appareils, des téléphones et des applications client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fc0e-123">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

