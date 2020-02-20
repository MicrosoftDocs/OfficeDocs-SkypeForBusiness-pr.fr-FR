---
title: 'Lync Server 2013 : définition de la configuration requise pour la surveillance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organizations's requirements for monitoring
ms:assetid: d587ff04-9af6-4ac1-ad42-076e7a40ac75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205284(v=OCS.15)
ms:contentKeyID: 48185491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1e2464eef960f91ecd8e7d8fc8fb71da7ab3a73
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-monitoring-in-lync-server-2013"></a>Définition de la configuration requise pour la surveillance dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-05_

La rationalisation du déploiement et de l’installation de la surveillance dans Microsoft Lync Server 2013 a également rationalisé les processus impliqués dans la définition des exigences de votre organisation en matière de surveillance. Néanmoins, il existe toujours plusieurs problèmes clés à résoudre avant de commencer à installer et configurer Lync Server 2013 :

**Quels types de données voulez-vous surveiller ?** Lync Server 2013 vous permet de surveiller deux types de données : les données d’enregistrement des détails des appels (CDR) et les données de qualité de l’expérience (QoE). L’enregistrement des détails des appels vous permet d’effectuer le suivi de l’utilisation des fonctionnalités de Lync Server, telles que les appels téléphoniques VoIP (Voice over IP); messagerie instantanée (IM); transferts de fichiers ; conférence audio/vidéo (A/V); et les sessions de partage d’application. Ces informations vous permettent de savoir quelles fonctionnalités Lync Server sont utilisées (et celles qui ne le sont pas) et fournit également des informations sur l’utilisation de ces fonctionnalités. Les données QoE vous permettent de conserver un enregistrement de la qualité des appels audio et vidéo passés dans votre organisation, tout en vous informant sur le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets).

Si vous choisissez d’activer la surveillance dans Lync Server 2013, vous pouvez activer à la fois la surveillance du CD-r et la surveillance QoE, ou vous pouvez choisir d’activer un type de surveillance tout en laissant l’autre type désactivé. Par exemple, supposons que vos utilisateurs se servent uniquement de la messagerie instantanée et du transfert de fichier, et ne passent pas d’appels audio ou vidéo. Dans ce cas, l’activation de la surveillance QoE s’avère superflue. De même, Lync Server facilite l’activation et la désactivation de la surveillance après le déploiement de la surveillance. Par exemple, il est possible que vous choisissiez de déployer la surveillance tout en laissant la surveillance QoE désactivée dans un premier temps. Si vos utilisateurs commencent à rencontrer des problèmes avec les appels audio et vidéo, vous pouvez alors activer la surveillance QoE et utiliser ces données pour vous aider à dépanner et résoudre ces problèmes.

Il n’existe aucun avantage particulier (ou inconvénient) à installer la surveillance en même temps que Lync Server et l’installation de la surveillance après l’installation de Lync Server. Pour garder à l’esprit, avant d’installer la surveillance, vous devez sélectionner un ordinateur qui hébergera le magasin de surveillance principal, et une version prise en charge de SQL Server doit être installée et configurée sur cet ordinateur avant que cet ordinateur puisse être utilisé pour la surveillance. . Si vous avez déjà installé SQL Server sur un ordinateur et que cet ordinateur est prêt à être utilisé, vous pouvez installer la surveillance en même temps que Lync Server. Si vous ne disposez pas d’un ordinateur principal, vous pouvez procéder à l’installation de Lync Server seul, puis installer la surveillance dès que l’ordinateur principal est prêt à être utilisé.

**Quand souhaitez-vous installer la surveillance ?** La surveillance peut être installée et configurée en même temps que l’installation et la configuration de Lync Server 2013 ; l’Assistant Déploiement de Lync Server vous offre la possibilité d’associer vos pools frontaux à une base de données de surveillance lors de l’installation. Vous pouvez également installer la surveillance une fois que Lync Server lui-même a été installé ; pour ce faire, vous pouvez utiliser le générateur de topologie pour associer vos pools frontaux et serveurs à une base de données de surveillance, puis publier la topologie révisée.

**De combien de bases de données de surveillance principales avez-vous besoin ?** Une base de données de surveillance unique peut prendre en charge des dizaines de milliers d’utilisateurs (pour Microsoft Lync Server 2010, il a été estimé qu’une base de données colocalisée pour la surveillance et l’archivage pouvaient prendre en charge 240 000 utilisateurs). De plus, une seule base de données de surveillance peut être utilisée par plusieurs pools frontaux ; Si vous avez trois pools frontaux dans votre organisation, vous pouvez associer ces trois pools au même magasin principal.

Cela signifie simplement que pour de nombreuses organisations, la capacité de base de données ne sera pas un facteur décisif pour la détermination du nombre de bases de données de surveillance principales requises. Il semblerait plutôt que la vitesse du réseau soit un point important. Supposons que vous possédez trois pools frontaux, mais qu’un de ses pools est situé sur une connexion réseau lente. Dans ce cas, il est probable que vous voudrez utiliser deux bases de données de surveillance : une pour les deux pools dotés d’une bonne connexion réseau et une pour le pool situé sur la connexion réseau lente.

Lors de la planification de votre infrastructure de surveillance, vous devez également prendre en compte que Lync Server 2013 prend en charge l’utilisation de bases de données miroir. La « mise en miroir de base de données » permet de conserver simultanément deux copies d’une base de données, résidant chacune sur un serveur différent. À chaque fois que des données sont écrites sur la base de données primaire, elles sont également écrites sur la base de données miroir. Si la base de données principale doit échouer ou si elle n’est plus disponible, vous pouvez basculer vers la base de données miroir à l’aide d’une simple commande Lync Server PowerShell. Par exemple :

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

Ceci est important pour la planification, car la mise en miroir nécessite de doubler le nombre requis de bases de données : en plus de chaque base de données primaire vous aurez besoin d’une deuxième base de données pour servir de miroir.

**Vos sites Lync Server ont-ils besoin d’une configuration d’analyse personnalisée ?** Lors de l’installation de Lync Server 2013, vous installez également des collections globales de paramètres de configuration CDR et QoE ; ces collections globales vous permettent d’appliquer les mêmes paramètres CDR et QoE à l’ensemble de votre organisation. Dans bien des cas, cela suffira : souvent, vous souhaiterez activer la surveillance CDR pour tous vos utilisateurs.

Cependant, il peut aussi arriver que vous souhaitiez appliquer différents paramètres à différents sites. Par exemple, vous pouvez vouloir utiliser les surveillances CDR et QoE pour votre site de Redmond, mais seulement la surveillance CDR pour votre site de Dublin. De même, vous pouvez avoir besoin de conserver les données de surveillance pendant 60 jours pour le site de Redmond, mais seulement pendant 30 jours pour le site de Dublin. Lync Server 2013 permet de créer des collections distinctes de paramètres de configuration CDR et QoE au niveau de l’étendue site ; Cela vous permet de gérer chaque site différemment. Ceci vous permet de gérer différemment chaque site (cela inclut l’activation et la désactivation de la surveillance, ainsi que la configuration des paramètres de gestion tels que la durée de conservation des données.)

Remarquez que vous pouvez prendre cette décision avant de déployer la surveillance ou après. Par exemple, vous pouvez déployer la surveillance puis gérer l’intégralité de l’organisation en utilisant les paramètres globaux. Si vous changez d’avis, vous pouvez créer une collection distincte de paramètres pour le site de Redmond, puis utiliser ces paramètres pour gérer la surveillance pour Redmond (les paramètres appliqués sur l’étendue Site sont toujours prioritaires sur les paramètres appliqués sur l’étendue Global). Si vous changez encore d’avis, vous pouvez simplement supprimer les paramètres de configuration appliqués au site de Redmond. Lorsqu’une collection de paramètres de site est supprimée, la collection de paramètres globale sera automatiquement appliquée à ce site.

</div>

<span> </span>

</div>

</div>

</div>

