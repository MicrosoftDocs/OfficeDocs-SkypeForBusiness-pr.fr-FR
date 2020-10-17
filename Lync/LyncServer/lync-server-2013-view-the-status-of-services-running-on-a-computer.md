---
title: 'Lync Server 2013 : affichage de l’état des services exécutés sur un ordinateur'
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
ms.openlocfilehash: 95c633079e45eba40bd59c7666c752c2ef68b498
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518391"
---
# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a><span data-ttu-id="106f2-102">Affichage de l’état des services exécutés sur un ordinateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="106f2-102">View the status of services running on a computer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="106f2-103">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="106f2-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="106f2-104">Vous pouvez utiliser le panneau de configuration Lync Server 2013 pour afficher tous les services en cours d’exécution sur un ordinateur spécifique dans votre topologie Lync Server et voir l’état de chaque service.</span><span class="sxs-lookup"><span data-stu-id="106f2-104">You can use Lync Server 2013 Control Panel to view all the services that are running on a specific computer in your Lync Server topology and see the status of each service.</span></span>

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="106f2-105">Pour afficher l’état des services exécutés sur un ordinateur</span><span class="sxs-lookup"><span data-stu-id="106f2-105">To view the status of services running on a computer</span></span>

1.  <span data-ttu-id="106f2-106">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="106f2-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="106f2-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="106f2-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="106f2-108">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="106f2-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="106f2-109">Dans la barre de navigation de gauche, cliquez sur **topologie**.</span><span class="sxs-lookup"><span data-stu-id="106f2-109">In the left navigation bar, click **Topology**.</span></span>

4.  <span data-ttu-id="106f2-110">Sur la page **État** , triez ou recherchez la liste, selon vos besoins, pour trouver l’ordinateur qui vous intéresse, puis cliquez sur le nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="106f2-110">On the **Status** page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>

5.  <span data-ttu-id="106f2-111">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="106f2-111">Do any of the following:</span></span>
    
      - <span data-ttu-id="106f2-112">Pour afficher le dernier état des services en cours d’exécution sur l’ordinateur, cliquez sur **obtenir le statut du service**.</span><span class="sxs-lookup"><span data-stu-id="106f2-112">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    
      - <span data-ttu-id="106f2-113">Pour afficher la liste des services spécifiques en cours d’exécution sur l’ordinateur et l’état de chaque service, cliquez sur **Propriétés**, puis sur **Fermer** pour revenir à la liste.</span><span class="sxs-lookup"><span data-stu-id="106f2-113">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="106f2-114">Affichage de l’état du service à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="106f2-114">Viewing Service Status by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="106f2-115">Vous pouvez également afficher l’état du service à l’aide de Windows PowerShell et de la cmdlet **Get-CsWindowsService** .</span><span class="sxs-lookup"><span data-stu-id="106f2-115">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="106f2-116">Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="106f2-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="106f2-117">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="106f2-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-service-status"></a><span data-ttu-id="106f2-118">Pour afficher l’état du service</span><span class="sxs-lookup"><span data-stu-id="106f2-118">To view service status</span></span>

  - <span data-ttu-id="106f2-119">Pour afficher l’état du service sur un ordinateur, tapez une commande semblable à la suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="106f2-119">To view service status on a computer, type a command similar to the following in the Lync Server Management Shell and then press Enter:</span></span>
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    <span data-ttu-id="106f2-120">Cette commande renvoie des informations comme celles-ci :</span><span class="sxs-lookup"><span data-stu-id="106f2-120">This command returns information similar to the following:</span></span>
    
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

<span data-ttu-id="106f2-121">Pour plus d’informations, consultez la rubrique [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span><span class="sxs-lookup"><span data-stu-id="106f2-121">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="106f2-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="106f2-122">See Also</span></span>


[<span data-ttu-id="106f2-123">Gestion des appareils, des téléphones et des applications clientes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="106f2-123">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

