---
title: 'Lync Server 2013: exportation de données archivées'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exporting archived data
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48183347
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4974971912b0b64652aa939368f0a86e2e2484a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a><span data-ttu-id="10340-102">Exportation de données archivées à partir de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10340-102">Exporting archived data from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10340-103">_**Dernière modification de la rubrique:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="10340-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="10340-104">Il n’est pas possible de faire des recherches dans les données archivées dans les bases de données d’archivage ou bien ces données ne sont pas dans un format lisible. Cependant, vous pouvez utiliser l’applet de commande Export-CsArchivingData pour les extraire et les enregistrer en tant que fichier EML (Outlook Electronic Mail).</span><span class="sxs-lookup"><span data-stu-id="10340-104">Data archived in Archiving databases is not searchable or in a readable format, but you can use the Export-CsArchivingData cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span> <span data-ttu-id="10340-105">Pour plus d’informations sur l’exportation de données archivées, voir [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) dans la documentation sur les opérations.</span><span class="sxs-lookup"><span data-stu-id="10340-105">For details about exporting archived data, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) in the Operations documentation.</span></span>

<span data-ttu-id="10340-106">Si vous activez l’intégration de Microsoft Exchange, les données sont archivées dans les magasins Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="10340-106">If you enable Microsoft Exchange integration, data is archived in Exchange 2013 stores.</span></span> <span data-ttu-id="10340-107">Les données archivées dans Exchange 2013 sont consultables et détectable.</span><span class="sxs-lookup"><span data-stu-id="10340-107">Data archived in Exchange 2013 is searchable and discoverable.</span></span> <span data-ttu-id="10340-108">Pour plus d’informations sur la prise en charge des communications intégrées pour Exchange 2013 et Lync Server 2013, voir [prise en charge de l’intégration d’Exchange Server et de SharePoint dans Lync server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) dans la documentation relative à la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="10340-108">For details about support for integrated communications for Exchange 2013 and Lync Server 2013, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="10340-109">Pour plus d’informations sur l’accès aux données archivées dans Exchange, voir la documentation Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="10340-109">For details about accessing data that is archived in Exchange, see the Exchange 2013 documentation.</span></span>

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="10340-110">Exportation des données d’archivage à l’aide d’applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="10340-110">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="10340-111">Les données d’archivage peuvent être exportées à l’aide de l’applet de passe Export-CSArchivingData.</span><span class="sxs-lookup"><span data-stu-id="10340-111">Archiving data can be exported by using the Export-CSArchivingData cmdlet.</span></span> <span data-ttu-id="10340-112">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10340-112">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="10340-113">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="10340-113">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="10340-114">**Pour exporter les données d’archivage**</span><span class="sxs-lookup"><span data-stu-id="10340-114">**To export archiving data**</span></span>

  - <span data-ttu-id="10340-115">Cette commande exporte toutes les données d’archivage écrites dans la base de données d’archivage atl-sql-001.litwareinc.com depuis le 1er juin 2012.</span><span class="sxs-lookup"><span data-stu-id="10340-115">This command exports all the archiving data written to the archiving database atl-sql-001.litwareinc.com since June 1, 2012.</span></span> <span data-ttu-id="10340-116">Le fichier de sortie obtenu sera stocké dans le dossier C\\: ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="10340-116">The resulting output file will be stored in the folder C:\\ArchivingExports.</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

<span data-ttu-id="10340-117">**Pour exporter les données d’archivage d’un utilisateur unique**</span><span class="sxs-lookup"><span data-stu-id="10340-117">**To export archiving data for a single user**</span></span>

  - <span data-ttu-id="10340-118">La commande suivante exporte les données d’archivage d’un utilisateur unique: kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="10340-118">The following command exports archiving data for a single user: kenmyer@litwareinc.com.</span></span> <span data-ttu-id="10340-119">Pour cela, il suffit d’inclure le paramètre UserUri suivi de l’adresse SIP de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="10340-119">This is done by including the UserUri parameter followed by the user’s SIP address.</span></span> <span data-ttu-id="10340-120">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="10340-120">For example:</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="10340-121">Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) .</span><span class="sxs-lookup"><span data-stu-id="10340-121">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="10340-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="10340-122">See Also</span></span>


[<span data-ttu-id="10340-123">Prise en charge de l’intégration d’Exchange Server et de SharePoint dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10340-123">Exchange Server and SharePoint integration support in Lync Server 2013</span></span>](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[<span data-ttu-id="10340-124">Export-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="10340-124">Export-CsArchivingData</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[<span data-ttu-id="10340-125">Gestion de l’archivage Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10340-125">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

