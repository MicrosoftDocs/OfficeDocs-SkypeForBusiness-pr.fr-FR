---
title: 'Lync Server 2013 : configuration de la prise en charge pour les grandes réunions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 589bb15213e6ec895121d81e60852d183801cee9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a>Configuration de la prise en charge des grandes réunions dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-12_

La prise en charge de grandes réunions (jusqu’à 1 000 utilisateurs) nécessite une topologie appropriée, du matériel et des logiciels adéquats et la configuration d’un environnement spécifique.

<div>

## <a name="topology-requirements"></a>Conditions requises pour la topologie

Une seule réunion de grande taille nécessite au moins un serveur frontal et un serveur principal. Toutefois, pour assurer une haute disponibilité, nous vous recommandons d’utiliser un pool de serveurs frontaux avec des serveurs principaux en miroir.

Le compte de l’utilisateur qui héberge les grandes réunions doit être hébergé dans ce pool. Cependant, nous ne recommandons pas que vous hébergiez d’autres comptes d’utilisateur dans ce pool. Utilisez-le uniquement pour les grandes réunions. La meilleure pratique consiste à créer un compte d’utilisateur spécial dans ce pool qui sera utilisé pour héberger les grandes réunions. Étant donné que le paramètre de réunion de grande taille est optimisé pour les performances, son utilisation en tant qu’utilisateur normal pourrait avoir des problèmes tels que l’impossibilité de promouvoir une session P2P pour une réunion lorsqu’un point de terminaison PSTN est impliqué.

La gestion d’un pool avec deux serveurs frontaux nécessite une attention particulière. Pour plus d’informations, voir [topologies et composants pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

En outre, si vous souhaitez éventuellement fournir une sauvegarde et un basculement de récupération d’urgence pour le pool utilisé pour les grandes réunions, vous pouvez l’associer à un pool dédié configuré de la même manière dans un autre centre de données. Pour plus d’informations, reportez-vous à la rubrique [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

![Configuration de pool de réunions de grande taille](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Configuration de pool de réunions de grande taille")

Autres éléments pour la topologie :

  - Un partage de fichiers est requis pour le stockage du contenu de la réunion et, si le serveur d’archivage est déployé et activé, pour le stockage des fichiers d’archivage. Le partage de fichiers peut être dédié au pool ou peut être le même que celui utilisé par un autre pool du site dans lequel le pool est déployé. Pour plus d’informations sur la configuration du partage de fichiers, voir [configurer le stockage de fichiers pour Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).

  - Un serveur Office Web Apps Server est nécessaire pour activer la fonctionnalité de présentation PowerPoint dans les grandes réunions. Le serveur Office Web Apps Server peut être dédié au vaste pool de réunions ou il peut s’agir du même serveur Office Web Apps Server utilisé par d’autres pools au niveau du site dans lequel le pool dédié est déployé.

  - L’équilibrage de charge des serveurs frontaux nécessite l’équilibrage de la charge matérielle pour le trafic HTTP (par exemple, le téléchargement de contenu de réunion). L’équilibrage de charge DNS est recommandé pour le trafic SIP. Pour plus d’informations, voir [Load Balancing Requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Si vous souhaitez utiliser le serveur de surveillance pour le pool dédié aux grandes réunions, nous vous recommandons d’utiliser le serveur de surveillance et sa base de données qui sont partagés sur tous les pools de serveurs frontaux dans votre déploiement Lync Server.

</div>

<div>

## <a name="hardware-and-software-requirements"></a>Configuration matérielle et logicielle requise

La configuration matérielle requise pour les serveurs d’un pool dédié de grands rendez-vous est identique à celle de vos autres serveurs Lync Server 2013. Pour plus d’informations sur la configuration matérielle requise, voir «[plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Les serveurs d’un pool de grandes réunions dédié doivent satisfaire à toutes les configurations logicielles de Lync Server 2013. Pour plus d’informations sur la configuration logicielle requise, voir la documentation suivante :

  - [Serveur et outils pris en charge par le système d’exploitation dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Prise en charge du logiciel de base de données dans Lync Server 2013](lync-server-2013-database-software-support.md)

  - [Configuration logicielle requise supplémentaire pour Lync Server 2013](lync-server-2013-additional-software-requirements.md)

En outre, Lync Server 2013 et tous les clients Lync Server 2013 doivent disposer des dernières mises à jour.

</div>

<div>

## <a name="configuration-requirements"></a>Exigences de configuration

Nous recommandons de créer une nouvelle stratégie de conférence spécifique aux grandes réunions, puis d’affecter cette stratégie aux utilisateurs hébergés sur le pool dédié aux grandes réunions. Configurez la stratégie de conférence avec les paramètres suivants :

  - Définissez l’option **MaxMeetingSize** à **1 000**. (La valeur par défaut est **250**.)

  - Définissez l’option **AllowLargeMeetings** à **True**.

  - Définissez l’option **EnableAppDesktopSharing** à **Aucun**.

  - Définissez l’option **AllowUserToScheduleMeetingsWithAppSharing** à **False**.

  - Définissez l’option **AllowSharedNotes** à **False**.

  - Définissez l’option **AllowAnnotations** à **False**.

  - Définissez l’option **DisablePowerPointAnnotations** à **True**.

  - Définissez l’option **AllowMultiview** à **False**.

  - Définissez l’option **EnableMultiviewJoin** à **False**.

<div>


> [!NOTE]  
> La prise en charge des grandes réunions utilisateur 1000 dans Lync Server 2013 nécessite que le paramètre <STRONG>AllowLargeMeetings</STRONG> de la stratégie de conférence soit défini sur true pour le planificateur de réunions. Lorsque ce paramètre est défini sur true, l’expérience Lync est optimisée pour les réunions de grande taille lorsque les utilisateurs rejoignent cette réunion. Plus précisément, dans une grande réunion, Lync n’affiche pas la liste des participants complets à la réunion, qui est un goulot d’étranglement au niveau des performances pour le client et Lync Server 2013. Au lieu de cela, Lync affiche uniquement les informations sur l’utilisateur et la liste des présentateurs de la réunion. Lync continuera à afficher correctement le nombre total de participants disponibles dans les grandes réunions.



</div>

À l’exception du paramètre **Taille maximale de la réunion**, tous les autres paramètres de stratégie de conférence spécifiés ici sont requis afin de désactiver les fonctionnalités de conférence qui ne sont pas nécessaires pour les grandes réunions.

De plus, vous devez configurer le pool dédié de grandes réunions de manière à ce que chaque utilisateur Lync Server 2013 hébergé sur le pool et responsable de la gestion de la planification de la réunion dispose des autorisations appropriées. Pour ce faire, procédez ainsi :

  - Définissez l’option **Désigné comme présentateur** à **Aucun**. En règle générale, un ou quelques utilisateurs parmi tous les participants sont des présentateurs, et les participants ne doivent pas être automatiquement admis dans des grandes réunions en tant que présentateurs. Les présentateurs doivent être explicitement désignés au moment de la planification de la réunion ou promus explicitement au cours de la réunion.

  - Assurez-vous que la case à cocher **Type de conférence affecté par défaut** n’est pas sélectionnée. Ce paramètre contrôle si le complément de réunion en ligne pour Lync 2013 planifie toujours des conférences à l’aide de la Conférence affectée de l’organisateur, ce qui signifie que les réunions planifiées possèdent la même URL et les mêmes informations audio. Dans des scénarios de collaboration de petit groupe, l’utilisation de ce type de conférence est pratique, car tout le monde a sa conférence assignée individuelle et l’URL pour participer ainsi que les informations audio constantes permettent de rejoindre facilement la réunion. Cependant, dans des scénarios de grande réunion, l’équipe de support planifie les grandes réunions avec un ensemble d’informations d’identification d’utilisateur et fournit les URL et les informations audio aux demandeurs de la réunion. Dans ce cas, l’utilisation d’une URL différente pour rejoindre chaque réunion est préférable.

  - Vérifiez que la case à cocher **Admettre les utilisateurs anonymes par défaut** n’est pas sélectionnée, sauf si elle est nécessaire. Ce paramètre affecte le type d’accès à la réunion par défaut planifié par le complément de réunion en ligne pour Lync 2013 lorsque vous n’utilisez pas une conférence affectée. L’option appropriée pour ce paramètre dépend des besoins de votre organisation. Si les grandes réunions de votre organisation sont des réunions internes, ne sélectionnez pas cette option. Si la plupart des grandes réunions nécessitent la participation d’utilisateurs externes, sélectionnez cette option.

</div>

</div>

<span> </span>

</div>

</div>

</div>

