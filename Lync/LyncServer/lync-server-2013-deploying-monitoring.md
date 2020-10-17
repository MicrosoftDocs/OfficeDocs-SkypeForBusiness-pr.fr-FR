---
title: 'Lync Server 2013 : déploiement de la surveillance'
description: 'Lync Server 2013 : déploiement de la surveillance.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1821198ddd0b4164f6932122aa9cf00ac34aada
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561540"
---
# <a name="deploying-monitoring-in-lync-server-2013"></a>Déploiement de la surveillance dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-12-17_

Des modifications majeures ont été apportées à l’infrastructure de surveillance de Microsoft Lync Server 2013, en commençant par le fait que le rôle serveur de surveillance a été déconseillé. À la place des rôles Serveur de surveillance distincts (qui nécessitaient généralement que les organisations configurent des ordinateurs dédiés agissant comme serveurs de surveillance), les services de surveillance sont maintenant colocalisés sur chaque serveur frontal. Cette modification permet, entre autres, d’effectuer les opérations suivantes :

  - Réduisez le nombre de rôles serveur requis lors de l’implémentation de Lync Server 2013. Dans ce cas, la réduction du nombre de rôles serveur Serveur de surveillance permet également de diminuer les coûts en rendant inutile la gestion de serveurs dédiés à la surveillance ;

  - Réduisez la complexité de l’installation et de l’administration de Lync Server. En colocalisant automatiquement les services de surveillance sur chaque serveur frontal, vous n’avez plus besoin d’installer, de configurer ni de gérer le rôle Serveur de surveillance.

<div>


> [!NOTE]  
> Le rôle de serveur d’archivage a également été déconseillé dans Lync Server 2013. À l’instar des services de surveillance, les services d’archivage Lync Server 2013 sont colocalisés sur chaque serveur frontal. Il est important de le noter, car la surveillance et l’archivage partagent souvent la même instance de base de données SQL Server.



</div>

Comme vous pouvez vous y attendre, ces modifications ont un impact majeur sur l’installation et la gestion des services de surveillance. Par exemple, étant donné que le rôle serveur de surveillance n’existe plus, le nœud du serveur de surveillance a été supprimé du générateur de topologie Lync Server ; Cela signifie que vous ne pouvez plus utiliser l’Assistant Nouveau serveur de surveillance du générateur de topologie pour ajouter un nouveau serveur de surveillance à votre topologie. (Cet Assistant n’existe plus.) Au lieu de cela, vous implémenterez généralement des services de surveillance dans votre topologie en procédant comme suit :

1.  Activation de l’analyse en même temps vous configurez un nouveau pool Lync Server. (Dans Lync Server 2013, la surveillance est activée ou désactivée sur un pool par pool.) Notez que vous pouvez activer la surveillance pour un pool sans collecter réellement les données de surveillance, un processus expliqué dans la section Configuration de l’enregistrement des détails des appels et de la qualité de l’expérience de cette documentation.

2.  Association d’un magasin d’analyse (c’est-à-dire une base de données de surveillance) au nouveau pool. Notez qu’un seul magasin d’analyse peut être associé à plusieurs pools. Selon le nombre d’utilisateurs hébergés sur vos pools de serveurs d’inscriptions, cela signifie que vous n’avez pas besoin de configurer une base de données de surveillance distincte pour chacun de vos pools. Un seul magasin d’analyse peut être utilisé par plusieurs pools.

Bien qu’il soit souvent plus simple d’activer la surveillance en même temps que vous créez un nouveau pool, il est également possible de créer un nouveau pool en désactivant la surveillance. Dans ce cas, vous pouvez ultérieurement utiliser le Générateur de topologie pour activer le service : le Générateur de topologie permet d’activer ou de désactiver la surveillance pour un pool ou d’associer un pool à un magasin d’analyse différent. N’oubliez pas que même si le rôle Serveur de surveillance n’existe plus, vous devez toujours créer un ou plusieurs magasins d’analyse : des bases de données principales utilisées pour stocker les données collectées par le service de surveillance. Ces bases de données principales peuvent être créées avec Microsoft SQL Server 2008 R2 ou Microsoft SQL Server 2012.

<div>


> [!NOTE]  
> Si la surveillance a été activée pour un pool, vous pouvez désactiver le processus de collecte des données de surveillance sans avoir à modifier votre topologie : Lync Server Management Shell vous permet de désactiver (puis réactiver ultérieurement) la collecte de données d’enregistrement des détails des appels (CDR) ou de qualité de l’expérience (QoE). Pour plus d’informations, voir la section Configuration de l’enregistrement des détails des appels et de la qualité de l’expérience de ce document.



</div>

Une autre amélioration importante de la surveillance dans Lync Server 2013 est le fait que les rapports de surveillance de Lync Server prennent désormais en charge IPv6 : les rapports qui utilisent le champ adresse IP affichent des adresses IPv4 ou IPv6 en fonction de : 1) requête SQL utilisée ; et, 2) où l’adresse IPv6 est stockée dans la base de données de surveillance.

<div>


> [!NOTE]  
> Assurez-vous que le type de démarrage du service SQL Server Agent est automatique et que le service de l’agent SQL Server est en cours d’exécution pour l’instance SQL qui contient les bases de données de surveillance, afin que les travaux de maintenance SQL Server par défaut puissent s’exécuter sur leur base planifiée sous le contrôle du service SQL Server Agent.



</div>

Cette documentation vous guide tout au long du processus d’installation et de configuration des rapports de surveillance et de surveillance pour Lync Server 2013. La documentation donne des instructions détaillées qui vous aideront à effectuer les opérations suivantes :

  - activer la surveillance dans votre topologie et associer un magasin d’analyse à un pool frontal ;

  - Installez SQL Server Reporting Services et les rapports de surveillance Lync Server. Les rapports de surveillance sont des rapports préconfigurés qui permettent de visualiser différemment les informations stockées dans une base de données de surveillance ;

  - configurer la collecte des données de l’enregistrement des détails des appels ou de la qualité de l’expérience (QoE) de données. L’enregistrement des détails des appels vous permet d’effectuer le suivi de l’utilisation des fonctionnalités de Lync Server, telles que les appels téléphoniques VoIP (Voice over IP); messagerie instantanée (IM); transferts de fichiers ; conférence audio/vidéo (A/V); et les sessions de partage d’application. Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et la « gigue » (différences de retard des paquets) ;

  - vider manuellement les enregistrements des détails des appels et/ou QoE de la base de données de surveillance.

</div>

<span> </span>

</div>

</div>

</div>

