---
title: 'Lync Server 2013 : Définition de la configuration requise pour la surveillance'
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
ms.openlocfilehash: 102735e7a8149edcb858b30644197553f5392c1e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-monitoring-in-lync-server-2013"></a>Définition de la configuration requise pour la surveillance dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-05_

La simplification du déploiement et de l’installation de la surveillance dans Microsoft Lync Server 2013 a également rationalisé les processus impliqués dans la définition de la configuration requise pour la surveillance de votre organisation. Néanmoins, il existe toujours plusieurs problèmes clés qui doivent être résolus avant de commencer à installer et configurer Lync Server 2013 :

**Quels types de données voulez-vous contrôler ?** Lync Server 2013 vous permet de surveiller deux types de données : les appels d’information (CDR) et les données de qualité de l’expérimentation. L’enregistrement des détails des appels vous permet d’effectuer le suivi de l’utilisation des fonctionnalités de Lync Server, telles que les appels téléphoniques par voix sur IP (VoIP). messagerie instantanée ; transferts de fichiers ; conférences audio/vidéo (A/V); et des sessions de partage d’application. Ces informations vous aideront à déterminer quelles sont les fonctionnalités de Lync Server utilisées (et celles qui ne le sont pas), ainsi que des informations sur l’utilisation de ces fonctionnalités. Les données QoE vous permettent de conserver un enregistrement de la qualité des appels audio et vidéo passés dans votre organisation, tout en vous informant sur le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets).

Si vous choisissez d’activer l’analyse dans Lync Server 2013, vous pouvez activer le contrôle CDR et la surveillance QoE, ou vous pouvez choisir d’activer un seul type d’analyse tout en laissant le nouveau type désactivé. Par exemple, supposons que vos utilisateurs se servent uniquement de la messagerie instantanée et du transfert de fichier, et ne passent pas d’appels audio ou vidéo. Dans ce cas, l’activation de la surveillance QoE s’avère superflue. De même, Lync Server vous permet d’activer et de désactiver facilement une analyse après le déploiement de l’analyse. Par exemple, il est possible que vous choisissiez de déployer la surveillance tout en laissant la surveillance QoE désactivée dans un premier temps. Si vos utilisateurs commencent à rencontrer des problèmes avec les appels audio et vidéo, vous pouvez alors activer la surveillance QoE et utiliser ces données pour vous aider à identifier et résoudre ces problèmes.

Il n’y a aucun avantage particulier (ou inconvénient) d’installer la surveillance en même temps que Lync Server et de l’installation après l’installation de Lync Server. Pour garder à l’esprit que, avant d’installer la surveillance, vous devez sélectionner un ordinateur pour héberger le magasin principal de surveillance, et une version prise en charge de SQL Server doit être installée et configurée sur cet ordinateur pour que cet ordinateur puisse être utilisé pour l’analyse . Si vous avez déjà installé SQL Server sur un ordinateur et que cet ordinateur est prêt à l’emploi, vous pouvez installer la surveillance en même temps que Lync Server. Si vous ne disposez pas d’un ordinateur principal, vous pouvez procéder à l’installation autonome de Lync Server, puis installer la surveillance chaque fois que l’ordinateur principal est prêt à l’emploi.

**Quand souhaitez-vous installer la surveillance ?** L’analyse peut être installée et configurée en même temps que Lync Server 2013. l’Assistant Déploiement de Lync Server vous permet d’associer votre pool frontal à une base de données de surveillance lors de l’installation. Vous pouvez également installer la surveillance après l’installation de Lync Server. pour cela, vous pouvez utiliser le générateur de topologie pour associer vos pools et serveurs frontaux à une base de données de surveillance, puis publier la topologie révisée.

**Combien de bases de données d’analyse du serveur principal avez-vous besoin ?** Une base de données de surveillance unique peut prendre en charge des dizaines de milliers d’utilisateurs (pour Microsoft Lync Server 2010, il a été estimé qu’une base de données colocalisée pour la surveillance et l’archivage pouvaient prendre en charge les utilisateurs 240 000). De plus, une base de données de surveillance unique peut être utilisée par plusieurs pools front-end. Si vous avez trois pools front-end dans votre organisation, vous pouvez associer ces trois pools au même magasin principal.

En d’autres termes, cela signifie que, pour de nombreuses organisations, la capacité de la base de données ne sera pas le facteur de décision lors de la détermination du nombre de bases de données d’analyse du serveur principal qui seront nécessaires. Il semblerait plutôt que la vitesse du réseau soit un point important. Supposons que vous possédez trois pools frontaux, mais qu’un de ses pools est situé sur une connexion réseau lente. Dans ce cas, vous voudrez probablement utiliser deux bases de données de surveillance : une pour les deux pools dotés d’une bonne connexion réseau et une pour le pool situé sur la connexion réseau lente.

Lors de la planification de votre infrastructure de contrôle, vous devez également tenir compte du serveur Lync Server 2013 prenant en charge l’utilisation de bases de données en miroir. La « mise en miroir de base de données » permet de conserver simultanément deux copies d’une base de données, se trouvant chacune sur un serveur différent. À chaque fois que des données sont écrites sur la base de données primaire, elles sont également écrites sur la base de données miroir. Si la base de données principale doit échouer ou devenir indisponible, vous pouvez « basculer » vers la base de données miroir en utilisant une commande PowerShell simple de Lync Server. Par exemple :

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

Cela est important pour la planification, car la mise en miroir nécessite de doubler le nombre requis de bases de données : en plus de chaque base de données primaire vous aurez besoin d’une deuxième base de données pour servir de miroir.

**Vos sites Lync Server nécessitent-ils leurs propres configurations de surveillance personnalisées ?** Lorsque vous installez Lync Server 2013, vous devez également installer les collections globales des paramètres de configuration CDR et QoE ; ces collections globales vous permettent d’appliquer les mêmes paramètres de CDR et QoE à votre organisation entière. In many cases, this will be sufficient: often-times you will want, say, to have CDR monitoring enabled for all of your users.

Cependant, il peut aussi arriver que vous souhaitiez appliquer différents paramètres à différents sites. Par exemple, vous pouvez vouloir utiliser les surveillances CDR et QoE pour votre site de Redmond, mais seulement la surveillance CDR pour votre site de Dublin. De même, vous pouvez avoir besoin de conserver les données de surveillance pendant 60 jours pour le site de Redmond, mais seulement pendant 30 jours pour le site de Dublin. Lync Server 2013 vous permet de créer des collections distinctes de paramètres de configuration CDR et QoE sur l’étendue du site ; qui vous permet de gérer chaque site différemment. Cela vous permet de gérer différemment chaque site (cela inclut l’activation et la désactivation de la surveillance, ainsi que la configuration des paramètres de gestion tels que la durée de conservation des données.)

Remarquez que vous pouvez prendre cette décision avant de déployer la surveillance ou après. Par exemple, vous pouvez déployer la surveillance puis gérer l’intégralité de l’organisation en utilisant les paramètres globaux. Si vous changez d’avis, vous pouvez créer une collection distincte de paramètres pour le site de Redmond, puis utiliser ces paramètres pour gérer la surveillance pour Redmond (les paramètres appliqués sur l’étendue Site sont toujours prioritaires sur les paramètres appliqués sur l’étendue Global). Si vous changez encore d’avis, vous pouvez simplement supprimer les paramètres de configuration appliqués au site de Redmond. Lorsqu’une collection de paramètres de site est supprimée, la collection de paramètres globale sera automatiquement appliquée à ce site.

</div>

<span> </span>

</div>

</div>

</div>

