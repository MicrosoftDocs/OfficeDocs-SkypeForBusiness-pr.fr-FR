---
title: 'Lync Server 2013: Association de rapports d’analyse à une base de données miroir'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19ff2455d473c83855320555cdffdc2e33001d0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a>Association de rapports d’analyse à une base de données miroir dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-02-07_

Si vous configurez une instance miroir pour votre base de données de surveillance, cette base de données miroir prendra la relève en tant que base de données principale en cas de basculement. Toutefois, si vous utilisez les rapports de surveillance de Lync Server et un basculement, il est possible que vos rapports d’analyse ne se connectent pas à la base de données miroir. Et ce, car, lorsque vous installez des rapports de surveillance, vous spécifiez seulement l’emplacement de la base de données principale ; vous devez aussi spécifier l’emplacement de la base de données miroir.

Pour que les rapports basculent automatiquement sur la base de données miroir, vous devez ajouter la base de données miroir comme « partenaire de basculement » pour les deux bases de données utilisées par les rapports de surveillance (l’une pour les données d’enregistrement des détails des appels, et l’autre pour les données de la qualité de l’expérience (QoE)). (Notez que cette étape doit être effectuée après l’installation des rapports de surveillance.) Vous pouvez ajouter les informations du partenaire de basculement en modifiant manuellement les valeurs des chaînes de connexion utilisées par ces deux bases de données. Pour cela, procédez comme suit :

1.  Utilisez Internet Explorer pour ouvrir la page d’accueil de **SQL Server Reporting Services**. L’URL de cette page d’accueil comprend ce qui suit :
    
      - Le préfixe **http:**.
    
      - Le nom de domaine complet (FQDN) de l’ordinateur sur lequel les services de surveillance sont installés (par exemple, **atl-sql-001.litwareinc.com**).
    
      - La chaîne de **caractères\_/Reports**.
    
      - Le nom de l’instance de la base de données où les rapports de surveillance sont installés (par exemple, **archinst**).
    
    Par exemple, si SQL Server Reporting Services a été installé sur l’ordinateur atl-sql-001.litwareinc.com et que les rapports de surveillance utilisent l’instance de base de données archinst, l’URL de la page d’accueil doit ressembler à ceci :
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  Après avoir consulté la page d’accueil de Reporting Services, cliquez sur **LyncServerReports**, puis cliquez sur **signaler\_le contenu**. Vous serez ainsi dirigé vers la page de **contenu du rapport\_** pour les rapports de surveillance de Lync Server.

3.  Dans la page de **contenu du rapport\_** , cliquez sur la source de données **CDRDB** .

4.  Sur la page **CDRDB**, sous l’onglet **Propriétés**, recherchez le texte intitulé **Chaîne de connexion**. La chaîne de connexion actuelle a un format similaire à celui-ci :
    
    **Source de données = (local\\) archinst; catalogue initial = LcsCDR**

5.  Modifiez la chaîne de connexion façon à y inclure le nom du serveur et l’instance de base de données pour la base de données miroir. Par exemple, si le serveur est nommé atl-miroir-001 et que la base de données miroir est dans l’instance archinst, vous devez en plus spécifier la base de données miroir en utilisant cette syntaxe :
    
    **Partenaire de basculement = ATL-miroir\\-001 archinst**
    
    Votre chaîne de connexion modifiée ressemblera à ceci :
    
    **Source de données = (local\\) archinst; Partenaire de basculement = ATL-Mirror\\-001 archinst; initial catalog = LcsCDR**

6.  Après avoir mis à jour la chaîne de connexion, cliquez sur **Appliquer**.

7.  Dans la page **CDRDB** , cliquez sur le lien **rapports\_** sur le contenu. Cliquez sur la source de données **QMSDB**, puis modifiez la chaîne de connexion pour la base de données QoE. Par exemple :
    
    **Source de données = (local\\) archinst; Partenaire de basculement = ATL-Mirror\\-001 archinst; initial catalog = QoEMetrics**

8.  Cliquez sur **Appliquer**.

<div>

## <a name="see-also"></a>Voir aussi


[Installation des rapports d’analyse Lync Server 2013](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[Utilisation de rapports d’analyse dans Lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

