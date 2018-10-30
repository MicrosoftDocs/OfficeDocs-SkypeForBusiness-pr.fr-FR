---
title: Configuration de la prise en charge pour les grandes réunions
TOCTitle: Configuration de la prise en charge pour les grandes réunions
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205074(v=OCS.15)
ms:contentKeyID: 49298028
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la prise en charge pour les grandes réunions

 

_**Dernière rubrique modifiée :** 2014-05-12_

La prise en charge de grandes réunions (jusqu’à 1 000 utilisateurs) nécessite une topologie appropriée, du matériel et des logiciels adéquats et la configuration d’un environnement spécifique.

## Conditions requises pour la topologie

Une grande réunion nécessite au moins un serveur frontal et un serveur principal. Cependant, pour fournir une haute disponibilité, nous recommandons un pool de deux serveur frontal avec un serveurs principaux en miroir.

Le compte de l’utilisateur qui héberge les grandes réunions doit être hébergé dans ce pool. Cependant, nous ne recommandons pas que vous hébergiez d’autres comptes d’utilisateur dans ce pool. Utilisez-le uniquement pour les grandes réunions. La meilleure pratique consiste à créer un compte d’utilisateur spécial dans ce pool qui sera utilisé uniquement pour héberger les grandes réunions. Étant donné que le paramètre des grandes réunions est optimisé pour les performances, son utilisation en tant qu’utilisateur normal pourrait entraîner des problèmes tels que l’incapacité à promouvoir une session P2P dans une réunion lorsqu’un point de terminaison PSTN est impliqué.

La gestion d’un pool avec deux serveurs frontaux nécessite une attention particulière. Pour plus d’informations, voir [Topologies et composant utilisés pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

De plus, si vous voulez fournir la sauvegarde de récupération d’urgence et le basculement pour le pool utilisé pour les grandes réunions, vous pouvez l’associer à un autre pool dédié configuré de la même façon dans d’autres données, voir [Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

![Configuration de pool de grandes réunions](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Configuration de pool de grandes réunions")

Autres éléments pour la topologie :

  - Un partage de fichiers est requis pour le stockage du contenu de la réunion, et si un serveur d’archivage est déployé et activé, pour le stockage des fichiers d’archive. Le partage de fichiers peut être dédié au pool ou peut être le même que celui utilisé par un autre pool du site dans lequel le pool est déployé. Pour plus d’informations sur la configuration du même partage de fichiers, voir [Configuration du stockage des fichiers pour Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).

  - Office Web Apps Server est requis pour permettre la fonctionnalité de présentation PowerPoint dans les grandes réunions. Office Web Apps Server peut être dédié au pool de grande réunion ou il peut être le même Office Web Apps Server que celui utilisé par les autres pools du site dans lequel le pool dédié est déployé.

  - L’équilibrage de charge des serveurs frontaux nécessite l’équilibrage de charge matérielle pour le trafic HTTP (le téléchargement de contenu de la réunion). L’équilibrage de charge DNS est recommandé pour le trafic SIP. Pour plus d’informations, voir [Configuration requise pour l’équilibrage de charge dans Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Si vous voulez utiliser un serveur de surveillance pour le pool dédié aux grandes réunions, nous recommandons d’utiliser le serveur de surveillance et sa base de données partagés entre tous les pools serveur frontal de votre déploiement Lync Server.

## Configuration matérielle et logicielle requise

La configuration matérielle requise pour les serveurs dans un pool dédié aux grandes réunions est identique à celle des autres serveurs Lync Server 2013. Pour plus d’informations sur la configuration matérielle requise, voir [Plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Les serveurs d’un pool dédié aux grandes réunions doivent répondre à la configuration logicielle de Lync Server 2013. Pour plus d’informations sur la configuration logicielle requise, voir la documentation suivante :

  - [Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Prise en charge du logiciel de base de données dans Lync Server 2013](lync-server-2013-database-software-support.md)

  - [Autre configuration logicielle requise pour Lync Server 2013](lync-server-2013-additional-software-requirements.md)

De plus, Lync Server 2013 et tous les clients Lync Server 2013 doivent disposer des dernières mises à jour.

## Configuration requise

Nous recommandons de créer une nouvelle stratégie de conférence spécifique aux grandes réunions, puis d’affecter cette stratégie aux utilisateurs hébergés sur le pool dédié aux grandes réunions. Configurez la stratégie de conférence avec les paramètres suivants :

  - Définissez l’option **MaxMeetingSize** à **1 000**. (La valeur par défaut est **250**.)

  - Définissez l’option **AllowLargeMeetings** sur **True**.

  - Définissez l’option **EnableAppDesktopSharing** sur **Aucun**.

  - Définissez l’option **AllowUserToScheduleMeetingsWithAppSharing** sur **False**.

  - Définissez l’option **AllowSharedNotes** sur **False**.

  - Définissez l’option **AllowAnnotations** sur **False**.

  - Définissez l’option **DisablePowerPointAnnotations** sur **True**.

  - Définissez l’option **AllowMultiview** sur **False**.

  - Définissez l’option **EnableMultiviewJoin** sur **False**.

> [!NOTE]  
> La prise en charge de grandes réunions de 1 000 utilisateurs dans Lync Server 2013 requiert que le paramètre <strong>AllowLargeMeetings</strong> de la stratégie de conférence pour le planificateur de réunion ait la valeur true. Quand ce paramètre a la valeur true, l’expérience Lync sera optimisée pour les grandes réunions quand les utilisateurs rejoignent la réunion. Dans une grande réunion, Lync n’affiche pas la liste des participants (initiale ou mise à jour), car cela peut représenter un goulot d’étranglement pour le client et Lync Server 2013. À la place, Lync affiche les informations relatives à l’utilisateur et la liste des présentateurs de la réunion. Lync affichera cependant le nombre total de participants disponibles dans les grandes réunions.

À l’exception du paramètre **Taille maximale de la réunion**, tous les autres paramètres de stratégie de conférence spécifiés ici sont requis afin de désactiver les fonctionnalités de conférence qui ne sont pas nécessaires pour les grandes réunions.

De plus, vous devez configurer un pool dédié aux grandes réunions afin que chaque utilisateur Lync Server 2013 hébergé sur le pool et responsable de la gestion de la planification de la réunion dispose des autorisations requises. Pour ce faire, procédez ainsi :

  - Définissez l’option **Désigné comme présentateur** à **Aucun**. En règle générale, un ou quelques utilisateurs parmi tous les participants sont des présentateurs, et les participants ne doivent pas être automatiquement admis dans des grandes réunions en tant que présentateurs. Les présentateurs doivent être explicitement désignés au moment de la planification de la réunion ou promus explicitement au cours de la réunion.

  - Assurez-vous que la case à cocher **Type de conférence affecté par défaut** n’est pas sélectionnée. Ce paramètre contrôle si le complément de réunion en ligne pour Lync 2013 planifie toujours les conférences avec la conférence affectée de l’organisateur, ce qui veut dire que les réunions planifiées ont la même URL et informations audio. Dans des scénarios de collaboration de petit groupe, l’utilisation de ce type de conférence est pratique, car tout le monde a sa conférence affectée individuelle et l’URL pour participer ainsi que les informations audio constantes permettent de rejoindre facilement la réunion. Cependant, dans des scénarios de grande réunion, l’équipe de support planifie les grandes réunions avec un ensemble d’informations d’identification d’utilisateur et fournit les URL et les informations audio aux demandeurs de la réunion. Dans ce cas, l’utilisation d’une URL différente pour rejoindre chaque réunion est préférable.

  - Vérifiez que la case à cocher **Admettre les utilisateurs anonymes par défaut** n’est pas sélectionnée, sauf si elle est nécessaire. Ce paramètre affecte le type d’accès par défaut de la réunion planifié par le complément de réunion en ligne pour Lync 2013 lors d’utilisation de conférence non affectée. L’option appropriée pour ce paramètre dépend des besoins de votre organisation. Si les grandes réunions de votre organisation sont des réunions internes, ne sélectionnez pas cette option. Si la plupart des grandes réunions nécessitent la participation d’utilisateurs externes, sélectionnez cette option.

