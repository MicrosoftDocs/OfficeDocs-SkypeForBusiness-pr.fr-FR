---
title: 'Lync Server 2013 : Définition de la configuration requise pour la surveillance'
TOCTitle: Définition de la configuration requise pour la surveillance
ms:assetid: d587ff04-9af6-4ac1-ad42-076e7a40ac75
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205284(v=OCS.15)
ms:contentKeyID: 49891563
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition de la configuration requise pour la surveillance dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-05_

La simplification du déploiement et de l’installation de la surveillance dans Microsoft Lync Server 2013 a aussi simplifié les processus impliqués dans la définition des besoins de votre organisation pour la surveillance. Néanmoins, il reste toujours plusieurs problèmes importants à résoudre avant de commencer à installer et configurer Lync Server 2013 :

**Quels types de données voulez-vous surveiller ?** Lync Server 2013 vous permet de surveiller deux différents types de données : les données d’enregistrement des détails des appels (CDR) et les données de qualité de l’expérience (QoE). Les CDR vous permettent de suivre l’utilisation des fonctionnalités de Lync Server comme les appels téléphoniques VoIP (Voice over Internet Protocol), la messagerie instantanée, les transferts de fichiers, les conférences audio/vidéo et les sessions de partage d’applications. Ces informations vous permettent de savoir quelles fonctionnalités Lync Server sont en cours d’utilisation (et lesquelles ne le sont pas) tout en vous fournissant leurs dates et horaires d’utilisation. Les données QoE vous permettent de conserver un enregistrement de la qualité des appels audio et vidéo passés dans votre organisation, tout en vous informant sur le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets).

Si vous choisissez d’activer la surveillance dans Lync Server 2013, vous pouvez activer la surveillance CDR et QoE, ou seulement l’un des deux types de surveillance. Par exemple, supposons que vos utilisateurs se servent uniquement de la messagerie instantanée et du transfert de fichier, et ne passent pas d’appels audio ou vidéo. Dans ce cas, l’activation de la surveillance QoE s’avère superflue. De même, Lync Server facilite l’activation et la désactivation de la surveillance après son déploiement. Par exemple, il est possible que vous choisissiez de déployer la surveillance tout en laissant la surveillance QoE désactivée dans un premier temps. Si vos utilisateurs commencent à rencontrer des problèmes avec les appels audio et vidéo, vous pouvez alors activer la surveillance QoE et utiliser ces données pour vous aider à identifier et résoudre ces problèmes.

Le fait d’installer la surveillance en même temps que Lync Server ou après Lync Server ne change rien. Ce que vous ne devez pas oublier c’est que, avant d’installer la surveillance, vous devez choisir un ordinateur pour héberger le magasin de surveillance principal. De plus, une version de SQL Server prise en charge doit être installée et configurée sur l’ordinateur avant que ce dernier puisse être utilisé pour la surveillance. Si vous avez déjà installé SQL Server sur un ordinateur et que cet ordinateur est prêt à être utilisé, vous pouvez alors installer la surveillance en même temps que Lync Server. Si votre ordinateur principal n’est pas prêt, alors vous pouvez procéder à l’installation de Lync Server, puis installer la surveillance lorsque votre ordinateur principal sera prêt.

**Quand souhaitez-vous installer la surveillance ?** La surveillance peut être installée et configurée conjointement à l’installation et à la configuration de Lync Server 2013 ; l’Assistant Déploiement de Lync Server vous permettra d’associer vos pools frontaux à une base de données de surveillance durant la configuration. Vous pouvez également installer la surveillance après l’installation de Lync Server ; pour ce faire, utilisez le générateur de topologie pour associer vos pools et vos serveurs frontaux à une base de données de surveillance, puis pour publier la topologie révisée.

**De combien de bases de données de surveillance avez-vous besoin ?** Une seule base de données de surveillance peut prendre en charge des dizaines de milliers d’utilisateurs (pour Microsoft Lync Server 2010, nous estimons qu’une base de données colocalisée pour la surveillance et l’archivage peut prendre en charge 240 000 utilisateurs). De plus, une seule base de données de surveillance peut être utilisée pour plusieurs pools frontaux. Si votre organisation possède trois pools frontaux, vous devriez alors pouvoir associer ces trois pools au même magasin principal.

Cela signifie simplement que pour de nombreuses organisations, la capacité de base de données ne sera pas un facteur décisif pour la détermination du nombre de bases de données de surveillance principales requises. Il semblerait plutôt que la vitesse du réseau soit un point important. Supposons que vous possédez trois pools frontaux, mais qu’un de ses pools est situé sur une connexion réseau lente. Dans ce cas, il est probable que vous voudrez utiliser deux bases de données de surveillance : une pour les deux pools dotés d’une bonne connexion réseau et une pour le pool situé sur la connexion réseau lente.

Durant la planification de votre infrastructure de surveillance, vous devez également prendre en considération le fait que Lync Server 2013 prend en charge l’utilisateur de bases de données miroir. La « mise en miroir de base de données » permet de conserver simultanément deux copies d’une base de données, se trouvant chacune sur un serveur différent. À chaque fois que des données sont écrites sur la base de données primaire, elles sont également écrites sur la base de données miroir. Si la base de données primaire ne fonctionne pas ou n’est plus disponible, vous pouvez « basculer » vers la base de données miroir en utilisant une simple commande Lync Server PowerShell. Par exemple :

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

Cela est important pour la planification, car la mise en miroir nécessite de doubler le nombre requis de bases de données : en plus de chaque base de données primaire vous aurez besoin d’une deuxième base de données pour servir de miroir.

**Vous sites Lync Server ont-ils besoin d’avoir leur propre configuration de surveillance personnalisée ?** Lorsque vous installez Lync Server 2013, vous installez également les collections globales de paramètres de configuration CDR et QoE ; ces collections globales vous permettent d’appliquer les mêmes paramètres CDR et QoE à toute votre organisation. Dans bien des cas, cela suffira : souvent, vous souhaiterez activer la surveillance CDR pour tous vos utilisateurs.

Cependant, il peut aussi arriver que vous souhaitiez appliquer différents paramètres à différents sites. Par exemple, vous pouvez vouloir utiliser les surveillances CDR et QoE pour votre site de Redmond, mais seulement la surveillance CDR pour votre site de Dublin. De même, vous pouvez avoir besoin de conserver les données de surveillance pendant 60 jours pour le site de Redmond, mais seulement pendant 30 jours pour le site de Dublin. Lync Server 2013 vous permet de créer des collections distinctes de paramètres de configuration CDR et QoE sur l’étendue Site. Cela vous permet de gérer différemment chaque site (cela inclut l’activation et la désactivation de la surveillance, ainsi que la configuration des paramètres de gestion tels que la durée de conservation des données.)

Remarquez que vous pouvez prendre cette décision avant de déployer la surveillance ou après. Par exemple, vous pouvez déployer la surveillance puis gérer l’intégralité de l’organisation en utilisant les paramètres globaux. Si vous changez d’avis, vous pouvez créer une collection distincte de paramètres pour le site de Redmond, puis utiliser ces paramètres pour gérer la surveillance pour Redmond (les paramètres appliqués sur l’étendue Site sont toujours prioritaires sur les paramètres appliqués sur l’étendue Global). Si vous changez encore d’avis, vous pouvez simplement supprimer les paramètres de configuration appliqués au site de Redmond. Lorsqu’une collection de paramètres de site est supprimée, la collection de paramètres globale sera automatiquement appliquée à ce site.

