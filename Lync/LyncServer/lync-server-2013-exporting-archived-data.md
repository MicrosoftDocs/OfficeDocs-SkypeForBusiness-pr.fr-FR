---
title: 'Lync Server 2013 : exportation des données archivées'
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
ms.openlocfilehash: cc93d529c5f93ad020634d631c94c09e0a94df1a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a>Exportation de données archivées à partir de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Les données archivées dans les bases de données d’archivage ne peuvent pas faire l’objet d’une recherche ou d’un format lisible, mais vous pouvez utiliser l’applet de commande Export-applet csarchivingdata pour extraire des enregistrements de la base de données et les enregistrer en tant que fichier. EML (Outlook Electronic Mail). Pour plus d’informations sur l’exportation des données archivées, voir [Export-applet csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) dans la documentation des opérations.

Si vous activez l’intégration de Microsoft Exchange, les données sont archivées dans les magasins Exchange 2013. Les données archivées dans Exchange 2013 sont consultables et détectables. Pour plus d’informations sur la prise en charge des communications intégrées pour Exchange 2013 et Lync Server 2013, consultez la rubrique [prise en charge de l’intégration d’Exchange Server et de SharePoint dans Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) dans la documentation de prise en charge. Pour plus d’informations sur l’accès aux données archivées dans Exchange, reportez-vous à la documentation Exchange 2013.

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportation des données d’archivage à l’aide des applets de commande Windows PowerShell

L’applet de commande Export-CSArchivingData permet d’exporter les données d’archivage. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

**Pour exporter les données d’archivage**

  - Cette commande exporte toutes les données d’archivage enregistrées dans la base de données d’archivage atl-sql-001.litwareinc.com depuis le 1er juin 2012. Le fichier de sortie obtenu sera stocké dans le dossier C\\: ArchivingExports.
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**Pour exporter les données d’archivage pour un seul utilisateur**

  - La commande suivante exporte les données d’archivage pour un seul utilisateur : kenmyer@litwareinc.com. Pour cela, il suffit d’inclure le paramètre UserUri suivi de l’adresse SIP de l’utilisateur. Par exemple :
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Export-applet csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Prise en charge de l’intégration d’Exchange Server et de SharePoint dans Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[Export-applet csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[Gestion de l’archivage Lync Server 2013](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

