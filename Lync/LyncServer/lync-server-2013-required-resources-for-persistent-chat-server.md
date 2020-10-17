---
title: 'Lync Server 2013 : ressources requises pour le serveur de conversation permanente'
description: 'Lync Server 2013 : ressources requises pour le serveur de conversation permanente.'
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
ms.openlocfilehash: 18c81f0017428e4305e46fbcf5580a83af38accf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542550"
---
# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a>Ressources requises pour le serveur de conversation permanente dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-02-05_

La haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente nécessitent des ressources supplémentaires au-delà de ce qui est généralement nécessaire pour une exploitation complète. Avant de configurer le serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence, vérifiez que vous disposez des ressources suivantes en plus des éléments requis pour le fonctionnement du serveur de conversation permanente standard. Pour plus d’informations sur la configuration, reportez-vous à la rubrique [Configuring persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).

  - Une instance de base de données dédiée située dans le centre de données physique dans lequel se trouve le serveur frontal du service de conversation permanente. Cette base de données servira de miroir SQL Server pour la base de données de conversation permanente principale. Vous pouvez également désigner un serveur SQL Server supplémentaire comme témoin de mise en miroir si vous souhaitez un basculement automatisé vers la base de données miroir.

  - Une instance dédiée de la base de données, située dans l’autre centre de données physique. Cette base de données servira de base de données secondaire de copie des journaux de transaction SQL Server pour la base de données dans le centre de données principal.

  - Une instance de base de données dédiée servant de miroir SQL Server pour la base de données secondaire. Si vous le souhaitez, désignez un serveur SQL Server supplémentaire comme témoin de mise en miroir. Elles doivent toutes deux se situer dans le même centre de données physique que la base de données secondaire.

  - Si la conformité du serveur de conversation permanente est activée, trois instances de base de données dédiées supplémentaires sont requises. Leur distribution est identique à celles précédemment décrites pour la base de données de conversation permanente. Bien qu’il soit possible pour la base de données de conformité de partager la même instance SQL Server que la base de données de conversation permanente, nous vous recommandons des instances autonomes pour la haute disponibilité et la récupération d’urgence.

  - Un partage de fichiers doit être créé et désigné pour les journaux de transactions de la copie des journaux de transaction SQL Server. Tous les serveurs SQL dans les deux centres de données qui exécutent des bases de données de conversation permanente doivent disposer d’un accès en lecture/écriture à ce partage de fichiers. Il n’est pas défini avec un rôle FileStore.

  - Un partage de fichiers sur le serveur de base de données secondaire servant de dossier de destination pour les journaux de transaction SQL Server qui sont copiés à partir du partage de fichiers du serveur principal.

<div>


> [!NOTE]  
> Les serveurs de conversation permanente actifs dans un pool de serveurs de conversation permanente doivent résider dans le même fuseau horaire que le pool Lync de tronçon suivant défini dans la topologie.



</div>

Les figures suivantes fournissent des exemples sur la façon dont l’intégralité du pool de serveurs de conversation permanente peut être configurée dans les deux topologies de pools étirées différentes :

  - Pool de serveurs de conversation permanente étiré quand les centres de données sont localisés géographiquement et font état d’une bande passante élevée/faible latence.

  - Pool de serveurs de conversation permanente étiré quand les centres de données sont localisés géographiquement avec une bande passante réduite/latence élevée.

La figure suivante illustre une topologie de pool de serveurs de conversation permanente étirée où les centres de données sont localisés géographiquement avec une bande passante élevée/faible latence.

**Pool de serveurs de conversation permanente étiré quand les centres de données sont localisés géographiquement et font état d’une bande passante élevée/faible latence.**

![Examen de configuration du pool de serveurs de conversation permanente HBW](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Examen de configuration du pool de serveurs de conversation permanente HBW")

La figure suivante illustre une topologie de pool de serveurs de conversation permanente étirée où les centres de données sont localisés géographiquement avec une faible bande passante/latence élevée.

**Pool de serveurs de conversation permanente étiré quand les centres de données sont localisés géographiquement avec une bande passante réduite/latence élevée.**

![Examen de configuration du pool de serveurs de conversation permanente LBW](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Examen de configuration du pool de serveurs de conversation permanente LBW")

</div>

<span> </span>

</div>

</div>

</div>

