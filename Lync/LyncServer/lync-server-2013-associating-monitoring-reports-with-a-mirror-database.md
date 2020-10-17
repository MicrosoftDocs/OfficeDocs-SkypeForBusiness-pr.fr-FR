---
title: 'Lync Server 2013 : Association de rapports de surveillance à une base de données miroir'
description: 'Lync Server 2013 : Association de rapports de surveillance à une base de données miroir.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d64b37901e7939b5e904dec73caac2d3483e2d71
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568800"
---
# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a>Association des rapports de surveillance à une base de données miroir dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-07_

Si vous configurez un miroir pour votre base de données de surveillance, cette base de données miroir prend le relais comme base de données principale en cas de basculement. Toutefois, si vous utilisez les rapports de surveillance Lync Server et qu’un basculement se produit, vous pouvez constater que vos rapports de surveillance ne se connectent pas à la base de données miroir. En effet, lorsque vous installez des rapports de surveillance, vous spécifiez uniquement l’emplacement de la base de données principale ; vous ne spécifiez pas l’emplacement de la base de données miroir.

Pour obtenir un basculement automatique des rapports de surveillance vers la base de données miroir, vous devez ajouter la base de données miroir en tant que « partenaire de basculement » aux deux bases de données utilisées par les rapports de surveillance (une base de données pour les données d’enregistrement des détails des appels et l’autre pour les données de qualité de l’expérience (QoE)). (Notez que cette étape doit être effectuée après avoir installé les rapports de surveillance.) Vous pouvez ajouter les informations de partenaire de basculement en modifiant manuellement les valeurs de chaîne de connexion utilisées par ces deux bases de données. Pour ce faire, procédez de la manière suivante :

1.  Utilisez Internet Explorer pour ouvrir la page d’accueil **SQL Server Reporting Services** . L’URL de la page d’accueil de Reporting Services comprend les éléments suivants :
    
      - Le préfixe **http :** .
    
      - Nom de domaine complet (FQDN) de l’ordinateur sur lequel Reporting Services est installé (par exemple, **ATL-SQL-001.litwareinc.com**).
    
      - La chaîne de **caractères \_ /reports**.
    
      - Nom de l’instance de base de données dans laquelle les rapports de surveillance sont installés (par exemple, **archinst**).
    
    Par exemple, si SQL Server Reporting Services a été installé sur l’ordinateur atl-sql-001.litwareinc.com et que les rapports de surveillance utilisent l’instance de base de données archinst, l’URL de la page d’accueil doit ressembler à ceci :
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  Une fois que vous avez accédé à la page d’accueil de Reporting Services, cliquez sur **LyncServerReports**, puis sur **rapports \_ content**. Cela vous permettra d’accéder à la page de ** \_ contenu des rapports** pour les rapports de surveillance Lync Server.

3.  Sur la **page \_ contenu des rapports** , cliquez sur la source de données **CDRDB** .

4.  Sur la page **CDRDB** , sous l’onglet **Propriétés** , recherchez la zone de texte intitulée **chaîne de connexion**. La chaîne de connexion actuelle ressemblera à ceci :
    
    **Source de données = (local) \\ archinst ; catalogue initial = LcsCDR**

5.  Modifiez la chaîne de connexion afin d’inclure le nom du serveur et l’instance de base de données pour la base de données miroir. Par exemple, si le serveur est nommé ATL-Mirror-001 et que la base de données miroir se trouve dans l’instance archinst, vous devrez ajouter pour spécifier la base de données miroir à l’aide de la syntaxe suivante :
    
    **Partenaire de basculement = ATL-miroir-001 \\ archinst**
    
    La chaîne de connexion modifiée se présente comme suit :
    
    **Source de données = (local) \\ archinst ; Partenaire de basculement = ATL-miroir-001 \\ archinst ; initial catalog = LcsCDR**

6.  Après avoir mis à jour la chaîne de connexion, cliquez sur **appliquer**.

7.  Sur la page **CDRDB** , cliquez sur le lien ** \_ contenu des rapports** . Cliquez sur la source de données **QMSDB** , puis modifiez la chaîne de connexion pour la base de données QoE. Par exemple :
    
    **Source de données = (local) \\ archinst ; Partenaire de basculement = ATL-miroir-001 \\ archinst ; initial catalog = QoEMetrics**

8.  Cliquez sur **Appliquer**.

<div>

## <a name="see-also"></a>Voir aussi


[Installation des rapports de surveillance Lync Server 2013](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[Utilisation des rapports de surveillance dans Lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

