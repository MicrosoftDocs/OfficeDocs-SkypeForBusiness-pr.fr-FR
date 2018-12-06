---
title: Déploiement du serveur de surveillance dans Lync Server 2013
TOCTitle: Déploiement du serveur de surveillance dans Lync Server 2013
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398199(v=OCS.15)
ms:contentKeyID: 49296295
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement du serveur de surveillance dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-12-17_

Des modifications importantes ont été apportées à l’infrastructure de surveillance de Microsoft Lync Server 2013, à commencer par la suppression du rôle Serveur de surveillance. À la place des rôles Serveur de surveillance distincts (qui nécessitaient généralement que les organisations configurent des ordinateurs dédiés agissant comme serveurs de surveillance), les services de surveillance sont maintenant colocalisés sur chaque serveur frontal. Cette modification permet, entre autres, d’effectuer les opérations suivantes :

  - réduire le nombre de rôles serveur requis lors de l’implémentation de Lync Server 2013. Dans ce cas, la réduction du nombre de rôles serveur Serveur de surveillance permet également de diminuer les coûts en rendant inutile la gestion de serveurs dédiés à la surveillance ;

  - réduire la complexité de la configuration et de l’administration de Lync Server. En colocalisant automatiquement les services de surveillance sur chaque serveur frontal, vous n’avez plus besoin d’installer, de configurer ni de gérer le rôle Serveur de surveillance.

> [!NOTE]  
> Le rôle Serveur d’archivage a également été supprimé de Lync Server 2013. Tout comme les services de surveillance, les services d’archivage de Lync Server 2013 sont maintenant colocalisés sur chaque serveur frontal. Il est important de le noter, car la surveillance et l’archivage partagent souvent la même instance de base de données SQL Server.

Comme vous pouvez vous y attendre, ces modifications ont un impact majeur sur la façon dont les services de surveillance sont installés et gérés. Par exemple, comme le rôle Serveur de surveillance n’existe plus, le nœud Serveur de surveillance a été supprimé du Générateur de topologie de Lync Server. Cela signifie que vous ne faites plus appel à l’Assistant Nouveau serveur de surveillance du Générateur de topologie pour ajouter un nouveau serveur de surveillance à votre topologie. (Cet Assistant n’existe plus.) Vous implémentez en revanche les services de surveillance au sein de votre topologie en effectuant les deux étapes suivantes :

1.  Activation de la surveillance en même temps que vous configurez un nouveau pool Lync Server. (Dans Lync Server 2013, la surveillance est activée ou désactivée pool par pool.) Notez que vous pouvez activer la surveillance d’un pool sans collecter de données de surveillance. Ce processus est expliqué à la section Configuration de l’enregistrement des détails des appels et de la qualité de l’expérience de cette documentation.

2.  Association d’un magasin d’analyse (c’est-à-dire une base de données de surveillance) au nouveau pool. Notez qu’un seul magasin d’analyse peut être associé à plusieurs pools. Selon le nombre d’utilisateurs hébergés sur vos pools de serveurs d’inscriptions, cela signifie que vous n’avez pas besoin de configurer une base de données de surveillance distincte pour chacun de vos pools. Un seul magasin d’analyse peut être utilisé par plusieurs pools.

Bien qu’il soit souvent plus simple d’activer la surveillance en même temps que vous créez un nouveau pool, il est également possible de créer un nouveau pool en désactivant la surveillance. Dans ce cas, vous pouvez ultérieurement utiliser le Générateur de topologie pour activer le service : le Générateur de topologie permet d’activer ou de désactiver la surveillance pour un pool ou d’associer un pool à un magasin d’analyse différent. N’oubliez pas que même si le rôle Serveur de surveillance n’existe plus, vous devez toujours créer un ou plusieurs magasins d’analyse : des bases de données principales utilisées pour stocker les données collectées par le service de surveillance. Ces bases de données principales peuvent être créées avec Microsoft SQL Server 2008 R2 ou Microsoft SQL Server 2012.

> [!NOTE]  
> Si la surveillance a été activée pour un pool, vous pouvez désactiver le processus de collecte des données de surveillance sans avoir à changer votre topologie : Lync Server Management Shell vous permet de désactiver (puis de réactiver) la collecte des données de l’enregistrement des détails des appels ou de la qualité de l’expérience. Pour plus d’informations, voir la section Configuration de l’enregistrement des détails des appels et de la qualité de l’expérience de ce document.

Autre amélioration importante apportée à la surveillance dans Lync Server 2013 : les rapports de surveillance de Lync Server prennent désormais en charge IPv6. Les rapports qui utilisent le champ Adresse IP afficheront des adresses IPv4 ou IPv6 selon : 1) la requête SQL utilisée ; et, 2) que l’adresse IPv6 est stockée ou non dans la base de données de surveillance.

> [!NOTE]  
> Assurez-vous que le type de démarrage du service d’agent SQL Server est Automatique et que le service d’agent SQL Server est en cours d’exécution pour l’instance SQL qui contient les bases de données de surveillance, de sorte que les tâches de maintenance de surveillance par défaut de SQL Server peuvent s’exécuter selon leur planification sous le contrôle du service d’agent SQL Server.

Cette documentation vous explique comment installer et configurer la surveillance et les rapports de surveillance pour Lync Server 2013. La documentation donne des instructions détaillées qui vous aideront à effectuer les opérations suivantes :

  - activer la surveillance dans votre topologie et associer un magasin d’analyse à un pool frontal ;

  - installer SQL Server Reporting Services et les rapports de surveillance de Lync Server. Les rapports de surveillance sont des rapports préconfigurés qui permettent de visualiser différemment les informations stockées dans une base de données de surveillance ;

  - configurer la collecte des données de l’enregistrement des détails des appels ou de la qualité de l’expérience (QoE) de données. L’enregistrement des détails des appels offre un moyen de suivre l’utilisation des fonctionnalités de Lync Server, telles que les appels téléphoniques VoIP (Voice over Internet Protocol), la messagerie instantanée, les transferts de fichiers, les conférences audio/vidéo et les sessions de partage d’applications. Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et la « gigue » (différences de retard des paquets) ;

  - vider manuellement les enregistrements des détails des appels et/ou QoE de la base de données de surveillance.

