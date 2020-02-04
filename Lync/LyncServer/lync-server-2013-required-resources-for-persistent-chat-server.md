---
title: 'Lync Server 2013 : Ressources requises pour le serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31683641e50a3e3bc898841b0cf4b0911e046262
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a>Ressources requises pour le serveur de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-02-05_

Une haute disponibilité et une reprise après sinistre pour le serveur de chat permanent nécessitent des ressources supplémentaires en plus de ce qui est en général requis pour une opération complète. Avant de configurer le serveur de chat permanent pour une haute disponibilité et une reprise après sinistre, assurez-vous que vous disposez des ressources suivantes en plus de ce qui est requis pour l’opération de serveur de chat permanent standard. Pour plus d’informations sur la configuration, voir [configuration du serveur de chat permanent dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).

  - Une instance de base de données dédiée située dans le même centre de données physiques dans lequel se trouve le serveur frontal principal du service de chat permanent. Cette base de données fera office de miroir SQL Server pour la base de données de chat permanent principale. Vous pouvez également désigner un serveur SQL Server supplémentaire comme témoin de mise en miroir si vous voulez un basculement automatisé vers la base de données miroir.

  - Une instance dédiée de la base de données, située dans l’autre centre de données physique. Cette base de données sera utilisée en tant que base de données secondaire pour l’envoi du journal SQL Server de la base de données dans le centre de données principal.

  - Une instance de base de données dédiée à faire office de miroir SQL Server pour la base de données secondaire. Vous pouvez éventuellement désigner un serveur SQL Server supplémentaire comme témoin de mise en miroir. Elles doivent toutes deux se situer dans le même centre de données physique que la base de données secondaire.

  - Si la conformité de serveur Chat permanent est activée, il est nécessaire d’avoir trois instances de base de données spécialisées supplémentaires. La distribution de la base de données de chat persiste est identique à celle présentée précédemment. S’il est possible que la base de données de conformité partage la même instance SQL Server que la base de données de chat persistante, nous recommandons des instances autonomes pour une haute disponibilité et une reprise après sinistre.

  - Un partage de fichiers doit être créé et désigné pour les journaux de transactions d’envoi du journal SQL Server. Tous les serveurs SQL dans les centres de données exécutant des bases de données de chat permanent doivent disposer d’un accès en lecture/écriture à ce partage de fichiers. Celui-ci n’est pas défini avec un rôle FileStore.

  - Un partage de fichiers sur le serveur de base de données secondaire servant de dossier de destination pour les journaux de transactions SQL Server copiés à partir du partage de fichiers du serveur principal.

<div>


> [!NOTE]  
> Les serveurs de chat permanent actifs dans un pool de serveurs de chat permanent doivent résider dans le même fuseau horaire que le pool Lync de saut suivant défini dans la topologie.



</div>

Les illustrations suivantes fournissent des exemples sur la façon dont l’intégralité du pool de serveurs de chat permanent peut être configuré dans les deux topologies de pool étiré différentes :

  - Pool de serveurs de chat permanent étiré lorsque les centres de données sont géospatiales avec une bande passante élevée et une latence faible.

  - Pool de serveurs de chat permanent étiré lorsque les centres de données sont géospatiales avec une bande passante faible et une latence élevée.

La figure ci-après illustre une topologie de pool de serveurs de chat permanent étirée dans laquelle les centres de données sont géospatiales avec une bande passante élevée et une latence faible.

**Pool de serveurs de chat permanent étiré lorsque les centres de données sont géospatiales avec une bande passante élevée et une latence faible.**

![Examen permanent de configuration du pool de serveurs de conversation HBW](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Examen permanent de configuration du pool de serveurs de conversation HBW")

La figure suivante illustre une topologie de pool de serveurs de chat permanent étirée dans laquelle les centres de données sont géospatiales avec une bande passante faible et une latence élevée.

**Pool de serveurs de chat permanent étiré lorsque les centres de données sont géospatiales avec une bande passante faible et une latence élevée.**

![Examen permanent de configuration du pool de serveurs de conversation LBW](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Examen permanent de configuration du pool de serveurs de conversation LBW")

</div>

<span> </span>

</div>

</div>

</div>

