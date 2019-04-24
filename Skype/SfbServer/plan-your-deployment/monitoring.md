---
title: Planifier la surveillance dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
description: 'Résumé : Passez en revue cette rubrique lors de la planification pour le service de surveillance dans Skype pour Business Server.'
ms.openlocfilehash: cfe5e0eb31ca2badb3c4610f33c0761a98972ce7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213913"
---
# <a name="plan-for-monitoring-in-skype-for-business-server"></a>Planifier la surveillance dans Skype pour Business Server

**Résumé :** Consulter cette rubrique lors de la planification pour le service de surveillance dans Skype pour Business Server.

Le service de surveillance dans Skype pour Business Server fournit un moyen pour les administrateurs à recueillir des données d’utilisation et de la qualité pour les sessions de communication qui ont lieu dans leur organisation, ce qui permet d’identifier les tendances et les problèmes. Surveillance continue de votre déploiement vous permet de détecter les problèmes éventuels au début et de conserver les utilisateurs de votre organisation satisfait.

Surveillance dans Skype pour Business Server ne nécessite pas un rôle de serveur distinct (comme c’était le cas dans les versions antérieures de Lync) ; au lieu de cela, le service de surveillance est intégré à chaque serveur frontal. Surveillance n’est pas activé par défaut dans Skype pour Business Server. Cet article vous aidera à déterminer s’il faut activer la surveillance pendant ou après votre Skype initiale pour la configuration du serveur d’entreprise et les ressources SQL que vous devez prendre en charge les activités de surveillance. Si vous ne savez pas exactement ce qui est surveillé ou non, ou comment la surveillance peut vous aider, rendez-vous sur [Informations de base sur la surveillance](monitoring.md#Basics). Pour commencer votre processus de planification, rendez-vous sur [Définition de la configuration requise pour la surveillance](monitoring.md#requirements). Pour plus de détails sur la configuration SQL requise pour la surveillance, rendez-vous sur [Configuration SQL requise pour la surveillance](monitoring.md#topologies).

## <a name="basics-about-monitoring"></a>Informations de base sur la surveillance
<a name="Basics"> </a>

Une session est un terme générique pour la connexion d’un utilisateur a :

- Une conférence

- Un outil de conférence comme l’audio/vidéo ou le partage d’application

- un autre utilisateur via une conversation P2P (comme la messagerie instantanée ou un appel audio).

> [!NOTE]
> Skype pour Business Server effectue le suivi des informations sur chaque session : qui appelle qui ; les points de terminaison ont été utilisés lors de la session ; Combien de temps la session a ; Quel est la qualité de la session ; et ainsi de suite. Skype pour Business Server ne pas enregistrer et stocker l’appel proprement dit. Qui comprend les sessions de messagerie instantanée : bien que Skype pour Business Server enregistre des informations sur les sessions de messagerie instantanée, il ne conserve pas un enregistrement de chaque message instantané qui a été envoyé au cours de la session.

Les informations de détail base appel collectées par Skype pour Business Server pour chaque session peuvent être utilisées pour :

- Analyse de **retour sur investissement (ROI)** . Les administrateurs peuvent comparer les données d’utilisation à des données similaires recueillies pour leur système de téléphonie précédent afin d’afficher des économies et de justifier le déploiement de Skype pour Business Server.

- 
            La **Gestion des stocks de périphériques**. Les informations de gestion des actifs aident les administrateurs à identifier les anciens périphériques qui sont encore en service et qui ont besoin d’être remplacés, ainsi qu’à identifier les périphériques coûteux qui ne sont pas utilisés ou le sont trop peu.

- **Support technique**. Résolution des problèmes de données permet de prise en charge ingénieurs déterminent pourquoi d’un utilisateur d’appel ayant échoué, sans avoir à collecter les journaux côté client ou serveur. Ces informations peuvent être facilement accessibles et compris par le personnel du support technique qui n’ont pas une connaissance technique approfondie de la Skype pour client d’entreprise et Skype pour Business Server.

- **Identification et résolution des problèmes du système**. Permet aux administrateurs de détecter les problèmes majeurs qui peuvent empêcher les utilisateurs finaux d’effectuer des tâches de base comme la participation à une conférence, l’émission d’un appel ou l’envoi d’un message instantané.

Surveillance fournit également un mécanisme qui permet de points de terminaison SIP (par exemple, Skype pour les entreprises) pour fournir des informations de dépannage que l’administrateur n’a pas accès à :

- **Mesures qui affectent la qualité**. Ces mesures traitent de la transmission effective de l’appel lui-même ; elles fournissent une sorte de carnet de voyage qui suit l’acheminement de l’appel sur le réseau. Ces mesures (qui incluent des éléments tels que la perte de paquets, la gigue et les durées d’aller-retour) fournissent des informations sur ce qui est arrivé à l’appel à partir du moment où il a quitté le point de terminaison d’une personne jusqu’à son arrivée au point de terminaison de l’autre personne.

- **Problèmes signalés à l’utilisateur final**. Ces mesures comprennent les notifications de qualité médiocre que Skype pour Business présente aux utilisateurs finaux dans les cas où ils sont trop lointain à partir d’un microphone, parlez trop bas, dispose d’une connexion réseau mauvaise ou vous rencontrez une mauvaise qualité, car un autre programme sur le ordinateur consomme les ressources disponibles.

- **Informations sur l’environnement**. Ces mesures détaillent des facteurs de qualité d’appel, notamment le type de micro et les haut-parleurs utilisés, si l’utilisateur est connecté via une connexion VPN et si l’utilisateur utilise une connexion sans fil.

À la fin de chaque appel, les points de terminaison compatibles avec SIP transmettent ces informations au serveur frontal ayant facilité l’appel. Aucune opération n’est nécessaire pour que les points de terminaison transmettent ces informations ; ce comportement est intégré au protocole SIP. Cependant, si vous souhaitez collecter et stocker ces informations, vous devez installer et activer la surveillance. Si vous installez et activez la surveillance, les informations relatives aux appels sont collectées par des agents exécutés sur le serveur frontal et relayées à une paire de bases de données SQL Server. Le service de surveillance (sous la forme « d’agents de collecte de données unifiée ») est colocalisé dans tous les serveurs frontaux. 

## <a name="define-your-requirements-for-monitoring"></a>Définition de la configuration requise pour la surveillance
<a name="requirements"> </a>

Il y a encore plusieurs problèmes clés qui doivent être résolus avant de commencer à installer et configurer l’analyse avec Skype pour Business Server :

 **Quand souhaitez-vous installer la surveillance ?** Surveillance pouvant être installé et configuré en même temps avoir installé et configuré Skype pour Business Server ; le Skype pour l’Assistant de déploiement Business Server vous fournira la possibilité d’associer des pools frontaux avec une base de données de surveillance lors de l’installation. Sinon, vous pouvez installer surveillance après avoir installé Skype pour Business Server proprement dit ; Cette opération peut être effectuée à l’aide du Générateur de topologie pour associer votre pools frontaux et les serveurs à une base de données de surveillance, puis publier la topologie révisée.

N’oubliez pas que SQL Server doit être installé et configuré avant que vous ne procédiez au déploiement et à la configuration de la fonctionnalité de surveillance. Toutefois, vous devrez déployer SQL Server les bases de données de surveillance seront créées pour vous lorsque vous publiez votre Skype pour la topologie du serveur d’entreprise.

 **Le type de données que vous souhaitez analyser ?** Skype pour Business Server permet de surveiller les deux types généraux de données : appel détaillant les données d’enregistrement et la qualité de l’expérience (QoE). Enregistrement des détails des appels offre un moyen pour effectuer le suivi de l’utilisation de Skype pour Business Server telles que voix sur IP (VoIP) appels ; messagerie instantanée (IM) ; transferts de fichiers ; audio/vidéo (A / V) conférence ; et les sessions de partage d’application. Ces informations vous aident à connaître le Skype pour les fonctionnalités de Business Server actuellement utilisées (et qui ne le sont pas) et fournit également des informations quant à lorsque ces fonctionnalités sont utilisées. Les données QoE vous permettent de conserver un enregistrement de la qualité des appels audio et vidéo passés dans votre organisation, tout en vous informant sur le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets).

Si vous choisissez d’activer la surveillance dans Skype pour Business Server, vous pouvez activer la surveillance des détails des appels et QoE de surveillance, ou vous pouvez choisir d’activer un type de surveillance tout en laissant l’autre type désactivé. Par exemple, supposons que vos utilisateurs se servent uniquement de la messagerie instantanée et du transfert de fichier, et ne passent pas d’appels audio ou vidéo. Dans ce cas, l’activation de la surveillance QoE s’avère superflue. De même, Skype pour Business Server facilite activer et désactiver la surveillance après que surveillance a été déployé. Par exemple, il est possible que vous choisissiez de déployer la surveillance tout en laissant la surveillance QoE désactivée dans un premier temps. Si vos utilisateurs commencent à rencontrer des problèmes avec les appels audio et vidéo, vous pouvez alors activer la surveillance QoE et utiliser ces données pour vous aider à identifier et résoudre ces problèmes.

Il n’existe aucun avantage particulier (ou inconvénient) à l’installation de surveillance en même temps que vous installez Skype pour Business Server et l’installation de surveillance après que Skype pour Business Server a été installé. Le point à retenir est que, avant l’installation de surveillance, vous devez sélectionner un ordinateur pour héberger le serveur principal de surveillance magasin et une version prise en charge de SQL Server doit être configuré sur cet ordinateur et de l’installation avant de pouvoir utiliser cet ordinateur pour la surveillance . Si vous avez déjà installé SQL Server sur un ordinateur et cet ordinateur est prêt à être utilisé si vous pouvez installer en même temps que vous installez Skype pour Business Server de surveillance. Si vous n’avez pas un ordinateur principal prêt vous pouvez procéder à l’installation Skype pour Business Server seul puis installer surveillance chaque fois que l’ordinateur principal est prêt à être utilisé.

 **Combien backend bases de données de surveillance avez-vous besoin ?** Il a été estimé qu’une base de données colocalisée pour la surveillance et d’archivage peut prendre en charge Skype 240 000 pour les utilisateurs Business Server). En outre, une base de données de surveillance unique peut être utilisé par plusieurs pools frontaux ; Si vous avez trois pools frontaux dans votre organisation vous pouvez associer les trois de ces pools avec le même magasin principal.

Pour de nombreuses organisations, la capacité de base de données ne sera pas un facteur décisif pour la détermination du nombre de bases de données de surveillance principales requises. Il semblerait plutôt que la vitesse du réseau soit un point important. Supposons que vous possédez trois pools frontaux, mais qu’un de ses pools est situé sur une connexion réseau lente. Dans ce cas, vous voudrez probablement utiliser deux bases de données de surveillance : une pour les deux pools dotés d’une bonne connexion réseau et une pour le pool situé sur la connexion réseau lente.

Vous devez également prendre en compte que Skype pour Business Server prend en charge l’utilisation des bases de données miroir. La « mise en miroir de base de données » permet de conserver simultanément deux copies d’une base de données, se trouvant chacune sur un serveur différent. À chaque fois que des données sont écrites sur la base de données primaire, elles sont également écrites sur la base de données miroir. Si la base de données principale doit échouer ou sinon elles deviennent donc indisponible, vous pouvez « basculer » à la base de données miroir à l’aide d’un simple Skype pour commande PowerShell de serveur d’entreprise. Par exemple :

```
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

Cela est important pour la planification, car la mise en miroir nécessite de doubler le nombre requis de bases de données : en plus de chaque base de données primaire vous aurez besoin d’une deuxième base de données pour servir de miroir.

 **Votre Skype pour les sites Business Server doivent-ils leurs propre surveillance des configurations personnalisées ?** Lorsque vous installez Skype pour Business Server vous installez également les collections globales de paramètres de configuration CDR et QoE ; Ces collections globales vous donnent la possibilité d’appliquer les mêmes paramètres CDR et QoE dans toute l’organisation. In many cases, this will be sufficient: often-times you will want, say, to have CDR monitoring enabled for all of your users.

Cependant, il peut aussi arriver que vous souhaitiez appliquer différents paramètres à différents sites. Par exemple, vous pouvez vouloir utiliser les surveillances CDR et QoE pour votre site de Redmond, mais seulement la surveillance CDR pour votre site de Dublin. De même, vous pouvez avoir besoin de conserver les données de surveillance pendant 60 jours pour le site de Redmond, mais seulement pendant 30 jours pour le site de Dublin. Skype pour Business Server vous permet de créer différentes collections de paramètres de configuration CDR et QoE au niveau du site ; Ainsi, vous pouvez gérer différemment de chaque site. Cela vous permet de gérer différemment chaque site (cela inclut l’activation et la désactivation de la surveillance, ainsi que la configuration des paramètres de gestion tels que la durée de conservation des données.)

Remarquez que vous pouvez prendre cette décision avant de déployer la surveillance ou après. Par exemple, vous pouvez déployer la surveillance puis gérer l’intégralité de l’organisation en utilisant les paramètres globaux. Si vous changez d’avis, vous pouvez créer une collection distincte de paramètres pour le site de Redmond, puis utiliser ces paramètres pour gérer la surveillance pour Redmond (les paramètres appliqués sur l’étendue Site sont toujours prioritaires sur les paramètres appliqués sur l’étendue Global). Si vous changez encore d’avis, vous pouvez simplement supprimer les paramètres de configuration appliqués au site de Redmond. Lorsqu’une collection de paramètres de site est supprimée, la collection de paramètres globale sera automatiquement appliquée à ce site.

## <a name="sql-requirements-for-monitoring"></a>Configuration SQL requise pour la surveillance
<a name="topologies"> </a>

Quand vous activez la surveillance, les agents de collecte de données unifiée sont automatiquement installés et activés sur chaque serveur frontal. Pour les versions prises en charge de SQL Server et d’autres détails, voir [configuration du serveur pour Skype pour Business Server 2015](requirements-for-your-environment/server-requirements.md)

Les données d’analyse peuvent utiliser la même instance SQL Server que d’autres types de données. Généralement, la base de données des enregistrements des détails des appels (LcsCdr) et la base de données de qualité de l’expérience (QoEMetrics) utilisent la même instance SQL ; par ailleurs, ces deux bases de données utilisent souvent la même instance SQL que la base de données d’archivage (LcsLog). La seule limitation réelle concernant les instances SQL Server est que chaque instance SQL Server est limitée à :

- Une instance de le Skype pour la base de données principale Business Server 2015. (En règle générale, il est déconseillé que votre base de données de surveillance se trouver dans la même instance SQL, ou même sur le même ordinateur, que la base de données principale. Bien que techniquement possible, vous courez le risque de la base de données de surveillance à l’aide de l’espace disque requis par la base de données principale.)

- une seule instance de la base de données LcsCdr ;

- une seule instance de la base de données QoEMetrics ;

- une seule instance de la base de données d’archivage.

Autrement dit, vous ne pouvez pas avoir deux instances de la base de données LcsCdr dans la même instance SQL Server. Pour utiliser plusieurs instances de cette base de données, vous devez configurer plusieurs instances SQL Server.

## <a name="see-also"></a>Voir aussi


[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
