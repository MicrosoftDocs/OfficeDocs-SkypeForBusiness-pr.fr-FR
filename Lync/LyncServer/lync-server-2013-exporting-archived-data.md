---
title: Exportation des données archivées dans Lync Server 2013
TOCTitle: Exportation des données archivées dans Lync Server 2013
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204657(v=OCS.15)
ms:contentKeyID: 49296184
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exportation des données archivées dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-23_

Il n’est pas possible de faire des recherches dans les données archivées dans les bases de données d’archivage ou bien ces données ne sont pas dans un format lisible. Cependant, vous pouvez utiliser l’applet de commande Export-CsArchivingData pour les extraire et les enregistrer en tant que fichier EML (Outlook Electronic Mail). Pour plus d’informations sur l’exportation des données archivées, voir [Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData) dans la documentation des opérations.

Si vous activez l’intégration Microsoft Exchange, les données sont archivées dans des magasins Exchange 2013. Il est possible de faire des recherches dans les données archivées dans Exchange 2013 et ces données sont détectables. Pour plus d’informations sur la prise en charge des communications intégrées pour Exchange 2013 et Lync Server 2013, voir [Prise en charge de l’intégration d’Exchange Server et de SharePoint dans Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) dans la documentation de prise en charge. Pour plus d’informations sur l’accès aux données qui sont archivées dans Exchange, consultez la documentation d’Exchange 2013.

## Exportation des données d’archivage à l’aide des applets de commande Lync Server Management Shell

L’applet de commande Export-CSArchivingData permet d’exporter les données d’archivage. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

**Exportation des données d’archivage**

  - Cette commande exporte toutes les données d’archivage enregistrées dans la base de données d’archivage atl-sql-001.litwareinc.com depuis le 1er juin 2012. Le fichier de résultats obtenu sera enregistré dans le dossier C:\\ArchivingExports.
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**Exportation des données d’archivage pour un seul utilisateur**

  - La commande suivante exporte les données d’archivage pour un seul utilisateur : kenmyer@litwareinc.com. Pour cela, il suffit d’inclure le paramètre UserUri suivi de l’adresse SIP de l’utilisateur. Par exemple :
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

Pour plus d’information, voir d’aide relative à l’applet de commande [Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData).

## Voir aussi

#### Concepts

[Prise en charge de l’intégration d’Exchange Server et de SharePoint dans Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md)  

#### Autres ressources

[Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData)  
[Gestion de l’archivage Lync Server 2013](lync-server-2013-managing-archiving.md)

