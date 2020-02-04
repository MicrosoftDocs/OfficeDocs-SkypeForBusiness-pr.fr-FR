---
title: 'Lync Server 2013 : déploiement d’une analyse'
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
ms.openlocfilehash: 637897bce0a160a8cc3b199ec6aee3ffd7375852
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a>Déploiement de la surveillance dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-12-17_

Des modifications majeures ont été apportées à l’infrastructure de contrôle Microsoft Lync Server 2013, en commençant par le fait que le rôle du serveur de surveillance est déconseillé. Au lieu de surveiller les rôles de serveurs de surveillance individuels (en général, les organisations nécessaires pour configurer des ordinateurs dédiés comme serveurs d’analyse) sont désormais localisées sur chaque serveur frontal. Vous pouvez également effectuer les opérations suivantes :

  - Réduisez le nombre de rôles de serveur requis lors de l’implémentation de Lync Server 2013. Dans ce cas, le fait de décrémenter le rôle serveur du serveur de surveillance permet également de réduire les coûts en éliminant la nécessité de conserver des serveurs dédiés à des fins de surveillance.

  - Réduisez la complexité de la configuration et de l’administration de Lync Server. Collocating automatiquement les services de surveillance sur chaque serveur frontal, vous n’avez plus besoin d’installer, de configurer et de gérer le rôle du serveur de surveillance.

<div>


> [!NOTE]  
> Le rôle du serveur d’archivage a également été déconseillé dans Lync Server 2013. Comme les services de surveillance, les services d’archivage de Lync Server 2013 sont désormais colocalisés sur chaque serveur frontal. Il est important de noter qu’il est important de partager et d’archiver fréquemment la même instance de base de données SQL Server.



</div>

Comme vous le souhaitez, ces modifications ont un impact important sur la façon dont les services de surveillance sont installés et gérés. Par exemple, dans la mesure où le rôle serveur de surveillance n’existe plus, le nœud du serveur de surveillance a été supprimé du générateur de topologie de Lync Server. en retour, cela signifie que vous n’utilisez plus l’Assistant Nouvelle analyse du serveur topologique pour ajouter un nouveau serveur de surveillance à votre topologie. (Cet Assistant n’existe plus.) Au lieu de cela, vous implémenterez généralement les services de surveillance dans votre topologie en effectuant les deux étapes suivantes :

1.  Activation de l’analyse en même temps que vous configurez un nouveau pool de serveurs Lync. (Dans Lync Server 2013, la surveillance est activée ou désactivée sur une base de pool par pool.) Notez que vous pouvez activer le contrôle pour un pool sans réellement collecter les données de surveillance, processus expliqué dans la section Configuration de l’enregistrement des détails des appels et de la qualité de l’enregistrement de cette documentation.

2.  Association d’un magasin d’analyse (c’est-à-dire une base de données de surveillance) au nouveau pool. Notez qu’un seul magasin d’analyse peut être associé à plusieurs pools. Selon le nombre d’utilisateurs hébergés sur vos pools de serveurs d’inscriptions, cela signifie que vous n’avez pas besoin de configurer une base de données de surveillance distincte pour chacun de vos pools. Un seul magasin d’analyse peut être utilisé par plusieurs pools.

Bien qu’il soit souvent plus simple d’activer la surveillance en même temps que vous créez un nouveau pool, il est également possible de créer un nouveau pool en désactivant la surveillance. Dans ce cas, vous pouvez ultérieurement utiliser le Générateur de topologie pour activer le service : le Générateur de topologie permet d’activer ou de désactiver la surveillance pour un pool ou d’associer un pool à un magasin d’analyse différent. Gardez à l’esprit que bien qu’il n’y ait plus de rôle serveur de surveillance, vous devrez tout de même créer un ou plusieurs magasins de surveillance : bases de données du serveur principal utilisées pour stocker les données collectées par le service de surveillance. Ces bases de données principales peuvent être créées à l’aide de Microsoft SQL Server 2008 R2 ou Microsoft SQL Server 2012.

<div>


> [!NOTE]  
> Si la surveillance a été activée pour un pool, vous pouvez désactiver le processus de collecte des données d’analyse sans avoir à modifier votre topologie : Lync Server Management Shell vous permet de désactiver (puis de réactiver ultérieurement) l’enregistrement des détails des appels (CDR) ou la qualité collecte de données de l’utilisateur. Pour plus d’informations, voir la section Configuration de l’enregistrement des détails des appels et de la qualité de l’expérience de ce document.



</div>

Une autre amélioration importante apportée à l’analyse dans Lync Server 2013 est le fait que les rapports de surveillance de Lync Server prennent désormais en charge le protocole IPv6 : les rapports qui utilisent le champ IP address affichent des adresses IPv4 ou IPv6 en fonction de : 1) la requête SQL utilisée ; et 2) lorsque l’adresse IPv6 est stockée dans la base de données de surveillance.

<div>


> [!NOTE]  
> Assurez-vous que le type de démarrage du service d’agent SQL Server est Automatique et que le service d’agent SQL Server est en cours d’exécution pour l’instance SQL qui contient les bases de données de surveillance, de sorte que les tâches de maintenance de surveillance par défaut de SQL Server peuvent s’exécuter selon leur planification sous le contrôle du service d’agent SQL Server.



</div>

Cette documentation vous guide tout au long du processus d’installation et de configuration de rapports d’analyse et de surveillance de Lync Server 2013. La documentation donne des instructions détaillées qui vous aideront à effectuer les opérations suivantes :

  - activer la surveillance dans votre topologie et associer un magasin d’analyse à un pool frontal ;

  - Installez SQL Server Reporting Services et les rapports de surveillance de Lync Server. Les rapports de surveillance sont des rapports préconfigurés qui permettent de visualiser différemment les informations stockées dans une base de données de surveillance ;

  - Configurez la collecte de données de l’enregistrement des détails des appels et de la qualité de l’appel. L’enregistrement des détails des appels vous permet d’effectuer le suivi de l’utilisation des fonctionnalités du serveur Lync telles que les appels téléphoniques VoIP (Voice over IP). messagerie instantanée ; transferts de fichiers ; conférences audio/vidéo (A/V); et des sessions de partage d’application. Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et la « gigue » (différences de retard des paquets) ;

  - vider manuellement les enregistrements des détails des appels et/ou QoE de la base de données de surveillance.

</div>

<span> </span>

</div>

</div>

</div>

