---
title: 'Lync Server 2013 : exportation de données archivées'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting archived data
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48183347
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5758d5e28610906b743888d25197385ef542717
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a>Exportation de données archivées à partir de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Il n’est pas possible de faire des recherches dans les données archivées dans les bases de données d’archivage ou bien ces données ne sont pas dans un format lisible. Cependant, vous pouvez utiliser l’applet de commande Export-CsArchivingData pour les extraire et les enregistrer en tant que fichier EML (Outlook Electronic Mail). Pour plus d’informations sur l’exportation de données archivées, voir [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) dans la documentation sur les opérations.

Si vous activez l’intégration de Microsoft Exchange, les données sont archivées dans les magasins Exchange 2013. Les données archivées dans Exchange 2013 sont consultables et détectable. Pour plus d’informations sur la prise en charge des communications intégrées pour Exchange 2013 et Lync Server 2013, voir [prise en charge de l’intégration d’Exchange Server et de SharePoint dans Lync server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) dans la documentation relative à la prise en charge. Pour plus d’informations sur l’accès aux données archivées dans Exchange, voir la documentation Exchange 2013.

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportation des données d’archivage à l’aide d’applets de cmdlet Windows PowerShell

Les données d’archivage peuvent être exportées à l’aide de l’applet de passe Export-CSArchivingData. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

**Pour exporter les données d’archivage**

  - Cette commande exporte toutes les données d’archivage écrites dans la base de données d’archivage atl-sql-001.litwareinc.com depuis le 1er juin 2012. Le fichier de sortie obtenu sera stocké dans le dossier C\\: ArchivingExports.
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**Pour exporter les données d’archivage d’un utilisateur unique**

  - La commande suivante exporte les données d’archivage d’un utilisateur unique : kenmyer@litwareinc.com. Pour cela, il suffit d’inclure le paramètre UserUri suivi de l’adresse SIP de l’utilisateur. Par exemple :
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Prise en charge de l’intégration d’Exchange Server et de SharePoint dans Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[Gestion de l’archivage Lync Server 2013](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

