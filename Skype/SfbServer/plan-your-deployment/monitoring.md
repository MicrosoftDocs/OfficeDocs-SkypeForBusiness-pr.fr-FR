---
title: Planifier la surveillance dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
description: 'Résumé : Examinez cette rubrique lors de la planification du service de surveillance dans Skype Entreprise Server.'
ms.openlocfilehash: 0a0b1c80498819a6fffc78d02f603950a9169779
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60744120"
---
# <a name="plan-for-monitoring-in-skype-for-business-server"></a>Planifier la surveillance dans Skype Entreprise Server

**Résumé :** Examinez cette rubrique lors de la planification du service de surveillance dans Skype Entreprise Server.

Le service de surveillance dans Skype Entreprise Server permet aux administrateurs de collecter des données d’utilisation et de qualité pour les sessions de communication qui ont lieu dans leur organisation, ce qui leur permet d’identifier les tendances et les problèmes. La surveillance continue de votre déploiement vous permet d’éviter les problèmes au plus tôt et de maintenir les utilisateurs de votre organisation satisfaits.

La surveillance dans Skype Entreprise Server ne nécessite pas de rôle serveur distinct (comme c’était le cas dans les versions antérieures de Lync) ; au lieu de cela, le service de surveillance est intégré à chaque serveur frontal. La surveillance n’est pas activée par défaut dans Skype Entreprise Server. Cet article vous aidera à déterminer s’il faut activer la surveillance pendant ou après votre configuration initiale Skype Entreprise Server et les ressources SQL dont vous aurez besoin pour prendre en charge les activités de surveillance. Si vous ne savez pas exactement ce qui est surveillé ou non et comment la surveillance peut être utile, allez aux informations de base [sur la surveillance.](monitoring.md#Basics) Pour commencer votre processus de planification, allez à [Définir vos besoins en matière de surveillance.](monitoring.md#requirements) Pour plus d’informations sur les SQL requises pour la surveillance, voir [SQL requises pour la surveillance.](monitoring.md#topologies)

## <a name="basics-about-monitoring"></a>Informations de base sur la surveillance
<a name="Basics"> </a>

Une session est un terme générique pour la connexion d’un utilisateur à un :

- Programme

- Outil de conférence tel que l’audio/vidéo ou le partage d’application

- Un autre utilisateur via une conversation d’égal à égal telle que la messagerie instantanée ou un appel audio

> [!NOTE]
> Skype Entreprise Server suit les informations sur chaque session : qui a appelé qui ; les points de terminaison utilisés dans la session ; durée de la session ; la qualité perçue de la session ; et ainsi de suite. Skype Entreprise Server’enregistre pas et ne stocke pas l’appel proprement dit. Cela inclut les sessions de messagerie instantanée : bien que Skype Entreprise Server enregistre les informations sur les sessions de messagerie instantanée, il ne conserve pas d’enregistrement de chaque message instantané envoyé au cours de la session.

Les informations de base sur les détails des appels collectées par Skype Entreprise Server pour chaque session peuvent être utilisées pour :

- **Analyse du retour sur investissement (ROI).** Les administrateurs peuvent comparer les données d’utilisation à des données similaires collectées pour leur système téléphonique précédent afin d’afficher les économies réalisées et de justifier le déploiement de Skype Entreprise Server.

- **Gestion de l’inventaire des appareils.** Les informations de gestion des biens permettent aux administrateurs d’identifier les anciens appareils en cours d’utilisation qui doivent être remplacés et d’identifier les appareils coûteux qui ne sont pas utilisés ou sous-utilisés.

- **Support technique**. Les données de dépannage aident les ingénieurs du support technique à déterminer pourquoi l’appel d’un utilisateur a échoué, sans avoir à collecter les journaux côté serveur ou client. Ces informations sont facilement accessibles et comprises par le personnel de support technique qui n’a pas une connaissance technique approfondie du client Skype Entreprise et du Skype Entreprise Server.

- **Résolution des problèmes du système.** Permet aux administrateurs de détecter les problèmes majeurs qui peuvent empêcher les utilisateurs finaux d’effectuer des tâches de base, telles que rejoindre une conférence, établir un appel ou envoyer un message instantané.

La surveillance fournit également un mécanisme qui permet aux points de terminaison SIP (tels que Skype Entreprise) de fournir des informations de dépannage que l’administrateur n’aurait pas accès autrement :

- **Mesures multimédias qui ont un impact sur la qualité**. Ces mesures traitent de la transmission réelle de l’appel lui-même ; Ils fournissent une sorte de voyage à mesure que l’appel se déplace sur le réseau. Ces mesures (notamment la perte de paquets, la gigue et les durées d’aller-retour) fournissent des informations sur ce qui est arrivé à l’appel depuis le moment où il a quitté le point de terminaison d’une personne jusqu’à son arrivée au point de terminaison de l’autre personne.

- **Problèmes signalés à l’utilisateur final.** Ces mesures incluent des notifications de qualité médiocre que Skype Entreprise présente aux utilisateurs finaux dans les cas où ils sont trop loin d’un microphone, parlent trop faiblement, ont une connexion réseau médiocre ou rencontrent une mauvaise qualité parce qu’un autre programme sur l’ordinateur consomme les ressources disponibles.

- **Informations sur l’environnement.** Ces mesures détaillent les facteurs de qualité des appels, tels que le type de microphone et les haut-parleurs utilisés, si l’utilisateur est connecté via une connexion VPN et s’il est connecté sans fil.

À la fin de chaque appel, les points de terminaison conformes SIP transmettent ces informations au serveur frontal qui a facilité l’appel. Vous n’avez rien à faire pour obtenir des points de terminaison pour transmettre ces informations . ce comportement est intégré au protocole SIP. Toutefois, si vous souhaitez collecter et stocker ces informations, vous devez installer et activer la surveillance. Si vous installez et activez la surveillance, les informations d’appel sont recueillies par les agents en cours d’exécution sur le serveur frontal et relayées vers deux bases de données SQL Server données. Le service de surveillance (sous la forme d'« agents de collecte de données unifiés ») est coqueté sur tous les serveurs frontaux.

## <a name="define-your-requirements-for-monitoring"></a>Définir les conditions requises pour la surveillance
<a name="requirements"> </a>

Plusieurs problèmes clés doivent encore être résolus avant de commencer à installer et configurer la surveillance avec Skype Entreprise Server :

 **Quand souhaitez-vous installer la surveillance ?** La surveillance peut être installée et configurée en même temps que vous installez et configurez Skype Entreprise Server ; L Skype Entreprise Server de déploiement de base de données vous permet d’associer vos pools frontux à une base de données de surveillance pendant l’installation. Vous pouvez également installer la surveillance une fois Skype Entreprise Server lui-même installé ; Pour ce faire, utilisez le Générateur de topologie pour associer vos pools et serveurs frontux à une base de données de surveillance, puis publiez la topologie révisée.

N’oubliez pas SQL Server devez être installé et configuré avant de déployer et de configurer la surveillance. Toutefois, il vous suffit de déployer SQL Server lui-même ; les bases de données de surveillance sont créées pour vous lorsque vous publiez votre topologie Skype Entreprise Server de surveillance.

 **Quel type de données voulez-vous surveiller ?** Skype Entreprise Server vous permet de surveiller deux types généraux de données : les données d’enregistrement des détails des appels et les données de qualité de l’expérience (QoE). L’enregistrement des détails des appels vous permet de suivre l’utilisation de fonctionnalités Skype Entreprise Server telles que les appels téléphoniques VoIP ( Voice over IP). messagerie instantanée ; transferts de fichiers ; conférence audio/vidéo (A/V) ; et sessions de partage d’application. Ces informations vous aident à savoir quelles fonctionnalités Skype Entreprise Server sont utilisées (et celles qui ne le sont pas) et fournissent également des informations sur le moment où ces fonctionnalités sont utilisées. Les données QoE vous permettent de conserver un enregistrement de la qualité des appels audio et vidéo passés dans votre organisation, tout en vous informant sur le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets).

Si vous choisissez d’activer la surveillance dans Skype Entreprise Server vous pouvez activer la surveillance cdr et la surveillance QoE, ou vous pouvez activer un type de surveillance tout en laissant l’autre type désactivé. Par exemple, supposons que vos utilisateurs se servent uniquement de la messagerie instantanée et du transfert de fichier, et ne passent pas d’appels audio ou vidéo. Dans ce cas, l’activation de la surveillance QoE s’avère superflue. De même, Skype Entreprise Server permet d’activer et de désactiver facilement la surveillance après le déploiement de la surveillance. Par exemple, il est possible que vous choisissiez de déployer la surveillance tout en laissant la surveillance QoE désactivée dans un premier temps. Si vos utilisateurs commencent à rencontrer des problèmes avec les appels audio et vidéo, vous pouvez alors activer la surveillance QoE et utiliser ces données pour vous aider à dépanner et résoudre ces problèmes.

Il n’existe aucun avantage (ou inconvénient) particulier à installer la surveillance en même temps que vous installez la Skype Entreprise Server et l’installation de la surveillance une fois Skype Entreprise Server installé. Le point à garder à l’esprit est que, avant d’installer la surveillance, vous devez sélectionner un ordinateur pour héberger le magasin d’analyse back-end, et une version prise en charge de SQL Server doit être installée et configurée sur cet ordinateur pour que cet ordinateur puisse être utilisé pour la surveillance. Si vous avez déjà installé SQL Server sur un ordinateur et que cet ordinateur est prêt à être utilisé, vous pouvez installer la surveillance en même temps que vous installez Skype Entreprise Server. Si vous n’avez pas d’ordinateur back-end prêt, vous pouvez installer Skype Entreprise Server seul, puis installer la surveillance chaque fois que l’ordinateur back-end est prêt à être utilisé.

 **De combien de bases de données de surveillance principale avez-vous besoin ?** Il a été estimé qu’une base de données cocquée pour la surveillance et l’archivage peut prendre en charge 240 000 Skype Entreprise Server utilisateurs). En outre, une base de données de surveillance unique peut être utilisée par plusieurs pools frontux ; Si vous avez trois pools frontux dans votre organisation, vous pouvez associer ces trois pools au même magasin principal.

Pour de nombreuses organisations, la capacité des bases de données ne sera pas le facteur déterminant lors de la détermination du nombre de bases de données de surveillance principale qui seront requises. Il semblerait plutôt que la vitesse du réseau soit un point important. Supposons que vous possédez trois pools frontaux, mais qu’un de ses pools est situé sur une connexion réseau lente. Dans ce cas, il est probable que vous voudrez utiliser deux bases de données de surveillance : une pour les deux pools dotés d’une bonne connexion réseau et une pour le pool situé sur la connexion réseau lente.

Vous devez également tenir compte du fait que Skype Entreprise Server prend en charge l’utilisation de bases de données miroir. La « mise en miroir de base de données » permet de conserver simultanément deux copies d’une base de données, résidant chacune sur un serveur différent. À chaque fois que des données sont écrites sur la base de données primaire, elles sont également écrites sur la base de données miroir. Si la base de données primaire doit échouer ou devenir indisponible, vous pouvez « faire échouer » la base de données miroir à l’aide d’une commande PowerShell Skype Entreprise Server simple. Par exemple :

```PowerShell
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

Ceci est important pour la planification, car la mise en miroir nécessite de doubler le nombre requis de bases de données : en plus de chaque base de données primaire vous aurez besoin d’une deuxième base de données pour servir de miroir.

 **Vos sites Skype Entreprise Server ont-ils besoin de leurs propres configurations d’analyse personnalisées ?** Lorsque vous installez Skype Entreprise Server vous installez également des collections globales de paramètres de configuration CDR et QoE ; Ces collections globales vous donnent la possibilité d’appliquer les mêmes paramètres CDR et QoE à l’ensemble de votre organisation. Dans bien des cas, cela suffira : souvent, vous souhaiterez activer la surveillance CDR pour tous vos utilisateurs.

Cependant, il peut aussi arriver que vous souhaitiez appliquer différents paramètres à différents sites. Par exemple, vous pouvez vouloir utiliser les surveillances CDR et QoE pour votre site de Redmond, mais seulement la surveillance CDR pour votre site de Dublin. De même, vous pouvez avoir besoin de conserver les données de surveillance pendant 60 jours pour le site de Redmond, mais seulement pendant 30 jours pour le site de Dublin. Skype Entreprise Server vous permet de créer des collections distinctes de paramètres de configuration CDR et QoE au niveau de l’étendue Site ; qui vous permet de gérer chaque site différemment. Ceci vous permet de gérer différemment chaque site (cela inclut l’activation et la désactivation de la surveillance, ainsi que la configuration des paramètres de gestion tels que la durée de conservation des données.)

Remarquez que vous pouvez prendre cette décision avant de déployer la surveillance ou après. Par exemple, vous pouvez déployer la surveillance puis gérer l’intégralité de l’organisation en utilisant les paramètres globaux. Si vous changez d’avis, vous pouvez créer une collection distincte de paramètres pour le site de Redmond, puis utiliser ces paramètres pour gérer la surveillance pour Redmond (les paramètres appliqués sur l’étendue Site sont toujours prioritaires sur les paramètres appliqués sur l’étendue Global). Si vous changez encore d’avis, vous pouvez simplement supprimer les paramètres de configuration appliqués au site de Redmond. Lorsqu’une collection de paramètres de site est supprimée, la collection de paramètres globale sera automatiquement appliquée à ce site.

## <a name="sql-requirements-for-monitoring"></a>SQL requises pour la surveillance
<a name="topologies"> </a>

Les agents de collecte de données unifiés sont automatiquement installés et activés sur chaque serveur frontal lorsque vous activez la surveillance. Pour les versions de SQL Server et d’autres détails pris en charge, voir [Server requirements for Skype Entreprise Server 2015](requirements-for-your-environment/server-requirements.md)

Les données de surveillance peuvent partager une instance SQL Server avec d’autres types de données. En règle générale, la base de données d’enregistrement des détails des appels (LcsCdr) et la base de données de qualité de l’expérience (QoEMetrics) partagent la même instance SQL’appel ; Il est également courant que les deux bases de données de surveillance se trouve dans la même instance SQL que la base de données d’archivage (LcsLog). La seule condition réelle avec les instances SQL Server est qu’une instance de SQL Server est limitée à ce qui suit :

- Une instance de la base Skype Entreprise Server base de données principale 2015. (En règle générale, il n’est pas recommandé que votre base de données de surveillance soit coquetée dans la même instance SQL, ou même sur le même ordinateur, que la base de données principale. Bien que techniquement possible, vous risquez que la base de données de surveillance utilise l’espace disque requis par la base de données principale.)

- Une instance de la base de données d’enregistrement des détails des appels.

- Une instance de la base de données de qualité de l’expérience.

- Une instance de la base de données d’archivage.

En d’autres termes, vous ne pouvez pas avoir deux instances de la base de données LcsCdr dans la même instance de SQL Server. Si vous avez besoin de plusieurs instances de la base de données LcsCdr, vous devez configurer plusieurs instances de SQL Server.

## <a name="see-also"></a>Voir aussi


[Déploiement du serveur de surveillance](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)