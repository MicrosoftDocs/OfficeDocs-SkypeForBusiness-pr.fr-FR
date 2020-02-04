---
title: 'Lync Server 2013 : configuration de la prise en charge des réunions de grande envergure'
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
ms.openlocfilehash: 0e8331c28d5bd06e6a3f7d9dab2fba7db334cd00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a>Configuration de la prise en charge des réunions de grande envergure dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-12_

La prise en charge de grandes réunions d’un maximum de 1000 utilisateurs nécessite la création d’une topologie appropriée, la mise en œuvre de matériels et de logiciels requis et la configuration de l’environnement de manière appropriée.

<div>

## <a name="topology-requirements"></a>Conditions requises pour la topologie

Une grande réunion nécessite au moins un serveur frontal et un serveur principal. Toutefois, pour garantir une haute disponibilité, nous vous recommandons de disposer d’un pool de serveurs frontal à deux serveurs dorsaux en miroir.

Le compte d’utilisateur de l’utilisateur qui héberge les grandes réunions doit être hébergé dans ce pool. Cependant, nous ne recommandons d’héberger d’autres comptes d’utilisateur dans ce pool. Utilisez-le uniquement pour les grandes réunions. Il est recommandé de créer un compte d’utilisateur spécial dans ce pool, qui ne sera utilisé que pour héberger les grandes réunions. Étant donné que le paramètre des grandes réunions est optimisé pour les performances, son utilisation en tant qu’utilisateur normal peut entraîner des problèmes, comme une incapacité à promouvoir une session P2P dans une réunion lorsqu’un point de terminaison RTC est impliqué.

La gestion d’un pool avec deux serveurs frontaux nécessite une attention particulière. Pour plus d’informations, reportez-vous à la rubrique [topologies et composants pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

De plus, si vous voulez fournir la sauvegarde de récupération d’urgence et le basculement pour le pool utilisé pour les grandes réunions, vous pouvez l’associer à un autre pool dédié configuré de la même façon dans d’autres centres de données. Pour plus d’informations, reportez-vous à [planification d’une haute disponibilité et reprise après sinistre dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

![Configuration de pool de grandes réunions](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Configuration de pool de grandes réunions")

Autres éléments pour la topologie :

  - Un partage de fichiers est nécessaire pour le stockage du contenu de la réunion et, si Archiving Server est déployé et activé, pour le stockage des fichiers d’archive. Le partage de fichiers peut être dédié au pool ou peut être le même que celui utilisé par un autre pool du site dans lequel le pool est déployé. Pour plus d’informations sur la configuration du partage de fichiers, voir [configurer le stockage de fichiers pour Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).

  - Office Web Apps Server est requis pour l’activation de la fonctionnalité présentation PowerPoint dans les réunions de grande envergure. Office Web Apps Server peut être dédié au pool de réunions de grande taille ou il peut s’agir du serveur Office Web Apps utilisé par d’autres pools sur le site dans lequel le pool dédié est déployé.

  - L’équilibrage de charge des serveurs frontaux nécessite l’équilibrage de charge matérielle pour le trafic HTTP (le téléchargement de contenu de la réunion). L’équilibrage de charge DNS est recommandé pour le trafic SIP (Session Initiation Protocol). Pour plus d’informations, voir [exigences d’équilibrage de charge pour Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Si vous souhaitez utiliser la surveillance du serveur pour le pool de réunions importantes, nous vous recommandons d’utiliser le serveur de surveillance et sa base de données partagés sur tous les pools de serveurs frontaux dans le déploiement de Lync Server.

</div>

<div>

## <a name="hardware-and-software-requirements"></a>Configuration matérielle et logicielle requise

La configuration matérielle requise pour les serveurs d’un pool de réunion volumineux dédié est identique à celle de vos autres serveurs Lync Server 2013. Pour plus d’informations sur la configuration matérielle requise, voir «[plateformes matérielles serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Les serveurs d’un pool de réunion dédié volumineux doivent respecter toutes les exigences logicielles de Lync Server 2013. Pour plus d’informations sur la configuration logicielle requise, veuillez consulter la documentation suivante :

  - [Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Prise en charge du logiciel de base de données dans Lync Server 2013](lync-server-2013-database-software-support.md)

  - [Autre configuration logicielle requise pour Lync Server 2013](lync-server-2013-additional-software-requirements.md)

De plus, Lync Server 2013 et tous les clients Lync Server 2013 doivent disposer des dernières mises à jour.

</div>

<div>

## <a name="configuration-requirements"></a>Configuration requise

Nous vous recommandons de créer une nouvelle stratégie de conférence spécifique pour les réunions de grande taille, puis d’affecter la stratégie de conférence aux utilisateurs qui sont hébergés sur le pool de réunion volumineux dédié. Configurez la stratégie de conférence avec les paramètres suivants :

  - Définissez l’option **MaxMeetingSize** sur **1000**. (La valeur par défaut est **250**.)

  - Définissez l’option **AllowLargeMeetings** sur **True**.

  - Définissez l’option **EnableAppDesktopSharing** sur **Aucun**.

  - Définissez l’option **AllowUserToScheduleMeetingsWithAppSharing** sur **False**.

  - Définissez l’option **AllowSharedNotes** sur **False**.

  - Définissez l’option **AllowAnnotations** sur **False**.

  - Définissez l’option **DisablePowerPointAnnotations** sur **True**.

  - Définissez l’option **AllowMultiview** sur **False**.

  - Définissez l’option **EnableMultiviewJoin** sur **False**.

<div>


> [!NOTE]  
> La prise en charge des réunions 1000 de grande envergure dans Lync Server 2013 nécessite le paramètre <STRONG>AllowLargeMeetings</STRONG> de la stratégie de conférence pour le planificateur de conférences sur true. Lorsque ce paramètre est défini sur true, l’expérience Lync sera optimisée pour les réunions de grande envergure lorsque les utilisateurs rejoignent une telle réunion. Plus précisément, dans une grande réunion, Lync n’affichera pas la première ou la mise à jour de la liste des participants à la réunion complète, qui est un goulet d’étranglement des performances pour le client et Lync Server 2013. À la place, Lync affiche uniquement les informations relatives à l’utilisateur et la liste des présentateurs de la réunion. Lync va tout de même afficher le nombre total de participants disponibles lors des réunions de grande envergure.



</div>

À l’exception du paramètre **Taille maximale de la réunion**, tous les autres paramètres de stratégie de conférence spécifiés ici sont nécessaires pour désactiver les fonctions de conférence qui ne sont pas nécessaires pour les grandes réunions.

Par ailleurs, vous devez configurer le pool de réunion dédié de grande taille de sorte que chaque utilisateur de Lync Server 2013 hébergé sur le pool et responsable de la gestion de la planification de la réunion dispose des autorisations appropriées. À cet effet, procédez ainsi :

  - Définissez l’option **Désigné comme présentateur** sur **Aucun**. En général, parmi tous les participants, un ou plusieurs utilisateurs sont des présentateurs. Les participants ne doivent pas être admis automatiquement dans des grandes réunions en tant que présentateurs. Les présentateurs doivent être désignés explicitement lors de la planification de la réunion ou promus explicitement lors de la réunion.

  - Assurez-vous que la case à cocher **Type de conférence affecté par défaut** n’est pas activée. Ce paramètre détermine si le complément réunion en ligne pour Lync 2013 planifie toujours des conférences à l’aide de la Conférence affectée de l’organisateur, ce qui signifie que les réunions planifiées ont la même URL et les mêmes informations audio. Dans des scénarios de collaboration en petit groupe, l’utilisation de ce type de conférence est pratique, car une conférence individuelle est affectée à chacun, et l’URL pour participer, ainsi que les informations audio constantes, permettant de rejoindre facilement la réunion. En revanche, dans des scénarios de grande réunion, l’équipe de support planifie les grandes réunions avec un ensemble d’informations d’identification d’utilisateur et fournit les URL et les informations audio aux demandeurs de la réunion. Dans ce cas, l’utilisation d’une URL différente pour rejoindre chaque réunion est préférable.

  - Vérifiez que la case à cocher **Admettre les utilisateurs anonymes par défaut** n’est pas activée, sauf si elle est nécessaire. Ce paramètre affecte le type d’accès par défaut à la réunion planifié par le complément réunion en ligne pour Lync 2013 quand vous n’utilisez pas de conférence affectée. L’option appropriée pour ce paramètre dépend des besoins de votre organisation. Si les grandes réunions de votre organisation sont des réunions internes, ne sélectionnez pas cette option. Si la plupart des grandes réunions nécessitent la participation d’utilisateurs externes, sélectionnez cette option.

</div>

</div>

<span> </span>

</div>

</div>

</div>

