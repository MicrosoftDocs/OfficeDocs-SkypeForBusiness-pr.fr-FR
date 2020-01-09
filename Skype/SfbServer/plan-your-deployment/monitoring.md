---
title: Planifier l’analyse dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
description: 'Résumé : reportez-vous à cette rubrique pour planifier le service de surveillance dans Skype entreprise Server.'
ms.openlocfilehash: ebe94d3088e319a0c210c9d169f35f1c783ad5f5
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991779"
---
# <a name="plan-for-monitoring-in-skype-for-business-server"></a>Planifier l’analyse dans Skype entreprise Server

**Résumé :** Consultez cette rubrique lors de la planification du service de surveillance dans Skype entreprise Server.

Le service de surveillance de Skype entreprise Server offre aux administrateurs la possibilité de recueillir des données d’utilisation et de qualité pour les sessions de communication qui interviennent au sein de leur organisation, ce qui leur permet d’identifier les tendances et les problèmes. Le contrôle permanent de votre déploiement vous permet de détecter les problèmes de manière précoce et de garantir la satisfaction des utilisateurs de votre organisation.

L’analyse dans Skype entreprise Server ne nécessite pas de rôle serveur distinct (comme dans les versions précédentes de Lync); au lieu de cela, le service de surveillance est intégré à chaque serveur frontal. La surveillance n’est pas activée par défaut dans Skype entreprise Server. Cet article vous aide à déterminer si vous souhaitez activer la surveillance pendant ou après la configuration initiale de Skype entreprise Server, et les ressources SQL nécessaires pour prendre en charge les activités de surveillance. Si vous ne savez pas exactement ce qui est surveillé ou non, ou comment la surveillance peut vous aider, rendez-vous sur [Informations de base sur la surveillance](monitoring.md#Basics). Pour commencer votre processus de planification, rendez-vous sur [Définition de la configuration requise pour la surveillance](monitoring.md#requirements). Pour plus de détails sur la configuration SQL requise pour la surveillance, rendez-vous sur [Configuration SQL requise pour la surveillance](monitoring.md#topologies).

## <a name="basics-about-monitoring"></a>Informations de base sur la surveillance
<a name="Basics"> </a>

Une session est un terme générique permettant de se connecter à un utilisateur :

- Une conférence

- Un outil de conférence comme l’audio/vidéo ou le partage d’application

- un autre utilisateur via une conversation P2P (comme la messagerie instantanée ou un appel audio).

> [!NOTE]
> Skype entreprise Server effectue le suivi des informations relatives à chaque session : qui a appelé qui ; Quels points de terminaison utilisés dans la session ; durée de la session, Quelle a été la qualité perçue de la session ; et ainsi de suite. Skype entreprise Server n’enregistre et ne stocke pas l’appel réel. Qui inclut des sessions de messagerie instantanée : bien que Skype entreprise Server enregistre des informations sur les sessions de messagerie instantanée, il ne conserve aucun enregistrement de chaque message instantané envoyé lors de la session.

Les informations de base collectées par Skype entreprise Server pour chaque session peuvent être utilisées pour :

- Analyse **du retour sur investissement** . Les administrateurs peuvent comparer les données d’utilisation à des données similaires collectées pour leur système de téléphonie précédent afin d’afficher une économie de coûts et de justifier le déploiement de Skype entreprise Server.

- 
            La **Gestion des stocks de périphériques**. Les informations de gestion des actifs aident les administrateurs à identifier les anciens périphériques qui sont encore en service et qui ont besoin d’être remplacés, ainsi qu’à identifier les périphériques coûteux qui ne sont pas utilisés ou le sont trop peu.

- **Support technique**. Résolution des problèmes permet aux ingénieurs de déterminer la raison pour laquelle l’appel a échoué, sans avoir à collecter les journaux côté serveur ou client. Il est possible d’accéder à ces informations et de les comprendre par le personnel du support technique qui ne dispose pas de connaissances techniques complètes sur le client Skype entreprise et Skype entreprise Server.

- **Identification et résolution des problèmes du système**. Permet aux administrateurs de détecter les problèmes majeurs qui peuvent empêcher les utilisateurs finaux d’effectuer des tâches de base comme la participation à une conférence, l’émission d’un appel ou l’envoi d’un message instantané.

Le contrôle fournit également un mécanisme permettant aux points de terminaison SIP (par exemple, Skype entreprise) de fournir des informations de résolution des problèmes auxquelles l’administrateur n’a pas accès.

- **Mesures qui affectent la qualité**. Ces mesures traitent de la transmission effective de l’appel lui-même ; elles fournissent une sorte de carnet de voyage qui suit l’acheminement de l’appel sur le réseau. Ces mesures (qui incluent des éléments tels que la perte de paquets, la gigue et les durées d’aller-retour) fournissent des informations sur ce qui est arrivé à l’appel à partir du moment où il a quitté le point de terminaison d’une personne jusqu’à son arrivée au point de terminaison de l’autre personne.

- **Problèmes signalés à l’utilisateur final**. Ces mesures incluent des notifications de bonne qualité que Skype entreprise présente aux utilisateurs finaux dans les cas où ceux-ci sont trop éloignés d’un micro, qui parlent trop de manière floue ou qui ont une mauvaise connexion réseau ou qui ont une qualité médiocre, car un autre programme sur le ordinateur consommant les ressources disponibles.

- **Informations sur l’environnement**. Ces mesures détaillent des facteurs de qualité d’appel, notamment le type de micro et les haut-parleurs utilisés, si l’utilisateur est connecté via une connexion VPN et si l’utilisateur utilise une connexion sans fil.

À la fin de chaque appel, les points de terminaison compatibles avec SIP transmettent ces informations au serveur frontal ayant facilité l’appel. Aucune opération n’est nécessaire pour que les points de terminaison transmettent ces informations ; ce comportement est intégré au protocole SIP. Cependant, si vous souhaitez collecter et stocker ces informations, vous devez installer et activer la surveillance. Si vous installez et activez la surveillance, les informations relatives aux appels sont collectées par des agents exécutés sur le serveur frontal et relayées à une paire de bases de données SQL Server. Le service de surveillance (sous la forme « d’agents de collecte de données unifiée ») est colocalisé dans tous les serveurs frontaux. 

## <a name="define-your-requirements-for-monitoring"></a>Définition de la configuration requise pour la surveillance
<a name="requirements"> </a>

Il existe toujours plusieurs problèmes clés qui doivent être résolus avant de commencer l’installation et la configuration de Skype entreprise Server :

 **Quand souhaitez-vous installer la surveillance ?** Vous pouvez installer et configurer le contrôle en même temps que Skype entreprise Server. l’Assistant Déploiement de Skype entreprise Server vous permet d’associer votre pool frontal à une base de données de surveillance lors de l’installation. Vous pouvez également installer la surveillance après l’installation de Skype entreprise Server. pour cela, vous pouvez utiliser le générateur de topologie pour associer vos pools et serveurs frontaux à une base de données de surveillance, puis publier la topologie révisée.

N’oubliez pas que SQL Server doit être installé et configuré avant que vous ne procédiez au déploiement et à la configuration de la fonctionnalité de surveillance. Toutefois, il vous suffit de déployer SQL Server proprement dit ; les bases de données de surveillance seront créées pour vous lorsque vous publierez votre topologie de Skype entreprise Server.

 **Quels types de données voulez-vous contrôler ?** Skype entreprise Server vous permet de surveiller deux types de données généraux : les appels d’information sur les appels et les données de qualité des appels. L’enregistrement des détails des appels vous permet d’effectuer le suivi de l’utilisation des fonctionnalités de Skype entreprise Server telles que les appels téléphoniques VoIP (voix sur IP). messagerie instantanée ; transferts de fichiers ; conférences audio/vidéo (A/V); et des sessions de partage d’application. Ces informations vous aideront à déterminer quelles sont les fonctionnalités de Skype entreprise Server utilisées (et celles qui ne le sont pas), ainsi que des informations sur l’utilisation de ces fonctionnalités. Les données QoE vous permettent de conserver un enregistrement de la qualité des appels audio et vidéo passés dans votre organisation, tout en vous informant sur le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets).

Si vous choisissez d’activer l’analyse dans Skype entreprise Server, vous pouvez activer le contrôle CDR et la surveillance QoE, ou vous pouvez choisir d’activer un seul type d’analyse tout en laissant le nouveau type désactivé. Par exemple, supposons que vos utilisateurs se servent uniquement de la messagerie instantanée et du transfert de fichier, et ne passent pas d’appels audio ou vidéo. Dans ce cas, l’activation de la surveillance QoE s’avère superflue. De même, Skype entreprise Server vous permet d’activer et de désactiver facilement la surveillance après le déploiement de la surveillance. Par exemple, il est possible que vous choisissiez de déployer la surveillance tout en laissant la surveillance QoE désactivée dans un premier temps. Si vos utilisateurs commencent à rencontrer des problèmes avec les appels audio et vidéo, vous pouvez alors activer la surveillance QoE et utiliser ces données pour vous aider à identifier et résoudre ces problèmes.

Il n’y a aucun avantage particulier (ou inconvénient) d’installer la surveillance en même temps que Skype entreprise Server et de procéder à la surveillance après l’installation de Skype entreprise Server. Pour garder à l’esprit que, avant d’installer la surveillance, vous devez sélectionner un ordinateur pour héberger le magasin principal de surveillance, et une version prise en charge de SQL Server doit être installée et configurée sur cet ordinateur pour que cet ordinateur puisse être utilisé pour l’analyse . Si vous avez déjà installé SQL Server sur un ordinateur et que cet ordinateur est prêt à l’emploi, vous pouvez installer la surveillance en même temps que Skype entreprise Server. Si vous ne disposez pas d’un ordinateur principal, vous pouvez procéder à l’installation de Skype entreprise Server seul, puis installer la surveillance chaque fois que l’ordinateur principal est prêt à l’emploi.

 **Combien de bases de données d’analyse du serveur principal avez-vous besoin ?** Il a été estimé qu’une base de données colocalisée pour la surveillance et l’archivage pouvait prendre en charge des utilisateurs de 240 000 Skype entreprise Server. De plus, une base de données de surveillance unique peut être utilisée par plusieurs pools front-end. Si vous avez trois pools front-end dans votre organisation, vous pouvez associer ces trois pools au même magasin principal.

Pour de nombreuses organisations, la capacité de base de données ne sera pas un facteur décisif pour la détermination du nombre de bases de données de surveillance principales requises. Il semblerait plutôt que la vitesse du réseau soit un point important. Supposons que vous possédez trois pools frontaux, mais qu’un de ses pools est situé sur une connexion réseau lente. Dans ce cas, vous voudrez probablement utiliser deux bases de données de surveillance : une pour les deux pools dotés d’une bonne connexion réseau et une pour le pool situé sur la connexion réseau lente.

Vous devez également tenir compte du serveur Skype entreprise Server qui prend en charge l’utilisation de bases de données en miroir. La « mise en miroir de base de données » permet de conserver simultanément deux copies d’une base de données, se trouvant chacune sur un serveur différent. À chaque fois que des données sont écrites sur la base de données primaire, elles sont également écrites sur la base de données miroir. Si la base de données principale doit échouer ou devenir indisponible, vous pouvez basculer vers la base de données miroir en utilisant une commande PowerShell unique de Skype entreprise Server. Par exemple :

```PowerShell
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

Cela est important pour la planification, car la mise en miroir nécessite de doubler le nombre requis de bases de données : en plus de chaque base de données primaire vous aurez besoin d’une deuxième base de données pour servir de miroir.

 **Vos sites Skype entreprise Server nécessitent-ils leurs propres configurations de surveillance personnalisées ?** Lorsque vous installez Skype entreprise Server, vous devez également installer des collections globales des paramètres de configuration CDR et QoE ; ces collections globales vous permettent d’appliquer les mêmes paramètres de CDR et QoE à votre organisation entière. In many cases, this will be sufficient: often-times you will want, say, to have CDR monitoring enabled for all of your users.

Cependant, il peut aussi arriver que vous souhaitiez appliquer différents paramètres à différents sites. Par exemple, vous pouvez vouloir utiliser les surveillances CDR et QoE pour votre site de Redmond, mais seulement la surveillance CDR pour votre site de Dublin. De même, vous pouvez avoir besoin de conserver les données de surveillance pendant 60 jours pour le site de Redmond, mais seulement pendant 30 jours pour le site de Dublin. Skype entreprise Server vous permet de créer des collections distinctes de paramètres de configuration de CDR et QoE sur l’étendue du site ; qui vous permet de gérer chaque site différemment. Cela vous permet de gérer différemment chaque site (cela inclut l’activation et la désactivation de la surveillance, ainsi que la configuration des paramètres de gestion tels que la durée de conservation des données.)

Remarquez que vous pouvez prendre cette décision avant de déployer la surveillance ou après. Par exemple, vous pouvez déployer la surveillance puis gérer l’intégralité de l’organisation en utilisant les paramètres globaux. Si vous changez d’avis, vous pouvez créer une collection distincte de paramètres pour le site de Redmond, puis utiliser ces paramètres pour gérer la surveillance pour Redmond (les paramètres appliqués sur l’étendue Site sont toujours prioritaires sur les paramètres appliqués sur l’étendue Global). Si vous changez encore d’avis, vous pouvez simplement supprimer les paramètres de configuration appliqués au site de Redmond. Lorsqu’une collection de paramètres de site est supprimée, la collection de paramètres globale sera automatiquement appliquée à ce site.

## <a name="sql-requirements-for-monitoring"></a>Configuration SQL requise pour la surveillance
<a name="topologies"> </a>

Quand vous activez la surveillance, les agents de collecte de données unifiée sont automatiquement installés et activés sur chaque serveur frontal. Pour plus d’informations sur les versions de SQL Server prises en charge, voir [Configuration requise pour Skype entreprise Server 2015](requirements-for-your-environment/server-requirements.md)

Les données d’analyse peuvent utiliser la même instance SQL Server que d’autres types de données. Généralement, la base de données des enregistrements des détails des appels (LcsCdr) et la base de données de qualité de l’expérience (QoEMetrics) utilisent la même instance SQL ; par ailleurs, ces deux bases de données utilisent souvent la même instance SQL que la base de données d’archivage (LcsLog). La seule limitation réelle concernant les instances SQL Server est que chaque instance SQL Server est limitée à :

- Une instance de la base de données principale de Skype entreprise Server 2015. (En règle générale, il est déconseillé d’avoir colocalisé votre base de données de surveillance dans la même instance SQL, ou même sur le même ordinateur que la base de données principale. Même si cela est possible, vous courez le risque de la base de données de surveillance en utilisant l’espace disque requis par la base de données principale.)

- une seule instance de la base de données LcsCdr ;

- une seule instance de la base de données QoEMetrics ;

- une seule instance de la base de données d’archivage.

Autrement dit, vous ne pouvez pas avoir deux instances de la base de données LcsCdr dans la même instance SQL Server. Pour utiliser plusieurs instances de cette base de données, vous devez configurer plusieurs instances SQL Server.

## <a name="see-also"></a>Voir aussi


[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
