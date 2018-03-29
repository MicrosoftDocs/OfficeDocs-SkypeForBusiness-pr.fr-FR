---
title: Planification de la surveillance dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/21/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
description: 'Résumé : Passez en revue cette rubrique lors de la planification pour le service de surveillance dans Skype pour Business Server 2015.'
ms.openlocfilehash: 82cad33f6094711f592633229db81b598df56fcb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-monitoring-in-skype-for-business-server-2015"></a>Planification de la surveillance dans Skype Entreprise Server 2015
 
**Résumé :** Lors de la planification pour le service de surveillance dans Skype pour Business Server 2015, consultez cette rubrique.
  
Le service de surveillance dans Skype pour Business Server 2015 offre un moyen pour les administrateurs de collecter des données d’utilisation et de qualité pour les sessions de communication qui interviennent dans leur organisation, ce qui leur permet d’identifier des tendances et des problèmes. Surveillance continue de votre déploiement vous permet de vous détecterez les problèmes rapidement et de conserver les utilisateurs de votre organisation satisfait. 
  
Surveillance dans Skype pour Business Server ne nécessite pas un rôle de serveur distinct (c’était le cas dans les versions précédentes de Lync) ; au lieu de cela, le service de surveillance est intégré à chaque serveur frontal. Surveillance n’est pas activée par défaut dans Skype pour Business Server. Cet article vous aidera à déterminer s’il faut activer l’analyse pendant ou après votre Skype initiale pour la configuration du serveur de l’entreprise et les ressources SQL que vous devez prendre en charge les activités de surveillance. Si vous ne savez pas exactement ce qui est surveillé ou non, ou comment la surveillance peut vous aider, rendez-vous sur [Informations de base sur la surveillance](monitoring.md#Basics). Pour commencer votre processus de planification, rendez-vous sur [Définition de la configuration requise pour la surveillance](monitoring.md#requirements). Pour plus de détails sur la configuration SQL requise pour la surveillance, rendez-vous sur [Configuration SQL requise pour la surveillance](monitoring.md#topologies).
  
## <a name="basics-about-monitoring"></a>Informations de base sur la surveillance
<a name="Basics"> </a>

Une session est un terme générique pour la connexion d’un utilisateur à a :
  
- Une conférence
    
- Un outil de conférence comme l’audio/vidéo ou le partage d’application
    
- un autre utilisateur via une conversation P2P (comme la messagerie instantanée ou un appel audio).
    
> [!NOTE]
> Skype pour Business Server effectue le suivi des informations relatives à chaque session : qui a appelé qui ; quels points de terminaison ont été utilisés dans la session ; Combien de temps la session a ; Quelle était la qualité de la session ; et ainsi de suite. Skype pour Business Server ne pas enregistrer et stocker l’appel réel lui-même. Qui inclut des sessions de messagerie instantanées : bien que Skype pour Business Server enregistre les informations sur les sessions de messagerie instantanées, il ne conserve pas un enregistrement de chaque message instantané qui vous a été envoyé au cours de la session. 
  
Les informations détaillées des appels de base collectées par Skype pour Business Server pour chaque session peuvent être utilisées pour :
  
- Analyse de **retour sur investissement (ROI)** . Les administrateurs peuvent comparer les données d’utilisation pour des données similaires recueillies pour leur système de téléphonie précédent afin d’afficher les économies de coût et de justifier le déploiement de Skype pour Business Server.
    
- 
            La **Gestion des stocks de périphériques**. Les informations de gestion des actifs aident les administrateurs à identifier les anciens périphériques qui sont encore en service et qui ont besoin d’être remplacés, ainsi qu’à identifier les périphériques coûteux qui ne sont pas utilisés ou le sont trop peu.
    
- **Support technique**. Des données de dépannage vous aide à prise en charge des ingénieurs de déterminent pourquoi un utilisateur appeler échec, sans avoir à collecter les journaux de côté client ou serveur. Ces informations sont facilement accessibles et comprises par le personnel du support technique qui n’ont pas une connaissance technique approfondie de la Skype pour client d’entreprise et Skype pour Business Server 2015.
    
- **Identification et résolution des problèmes du système**. Permet aux administrateurs de détecter les problèmes majeurs qui peuvent empêcher les utilisateurs finaux d’effectuer des tâches de base comme la participation à une conférence, l’émission d’un appel ou l’envoi d’un message instantané.
    
Surveillance fournit également un mécanisme qui permet des points de terminaison SIP (par exemple, Skype pour les entreprises) pour fournir des informations de résolution des problèmes que l’administrateur n’a pas accès à :
  
- **Mesures qui affectent la qualité**. Ces mesures traitent de la transmission effective de l’appel lui-même ; elles fournissent une sorte de carnet de voyage qui suit l’acheminement de l’appel sur le réseau. Ces mesures (qui incluent des éléments tels que la perte de paquets, la gigue et les durées d’aller-retour) fournissent des informations sur ce qui est arrivé à l’appel à partir du moment où il a quitté le point de terminaison d’une personne jusqu’à son arrivée au point de terminaison de l’autre personne.
    
- **Problèmes signalés à l’utilisateur final**. Ces mesures incluent les notifications de mauvaise qualité que Skype pour entreprise présente aux utilisateurs finaux dans les cas où ils sont trop loin à partir d’un microphone, parlez trop bas, dispose d’une connexion réseau est mauvaise ou vous rencontrez de qualité médiocre car un autre programme sur la ordinateur consomme les ressources disponibles.
    
- **Informations sur l’environnement**. Ces mesures détaillent des facteurs de qualité d’appel, notamment le type de micro et les haut-parleurs utilisés, si l’utilisateur est connecté via une connexion VPN et si l’utilisateur utilise une connexion sans fil.
    
À la fin de chaque appel, les points de terminaison compatibles avec SIP transmettent ces informations au serveur frontal ayant facilité l’appel. Aucune opération n’est nécessaire pour que les points de terminaison transmettent ces informations ; ce comportement est intégré au protocole SIP. Cependant, si vous souhaitez collecter et stocker ces informations, vous devez installer et activer la surveillance. Si vous installez et activez la surveillance, les informations relatives aux appels sont collectées par des agents exécutés sur le serveur frontal et relayées à une paire de bases de données SQL Server. Le service de surveillance (sous la forme « d’agents de collecte de données unifiée ») est colocalisé dans tous les serveurs frontaux.  
  
## <a name="define-your-requirements-for-monitoring"></a>Définition de la configuration requise pour la surveillance
<a name="requirements"> </a>

Il existe toujours plusieurs questions clés qui doivent être résolues avant de commencer à installer et configurer le contrôle avec Skype pour Business Server 2015 :
  
 **Quand souhaitez-vous installer la surveillance ?** Surveillance peut être installée et configurée en même temps que vous installez et configuré Skype pour 2015 de serveur d’entreprise ; le Skype pour l’Assistant de déploiement de Business Server 2015 vous fournira la possibilité d’associer vos pools de Front-End avec une analyse de la base de données lors de l’installation. Vous pouvez également installer surveillance après avoir installé Skype pour Business Server 2015, lui-même ; Pour cela, à l’aide de générateur de topologies pour associer vos pools de Front-End et les serveurs avec une analyse de la base de données, puis publiez la topologie révisée.
  
N’oubliez pas que SQL Server doit être installé et configuré avant que vous ne procédiez au déploiement et à la configuration de la fonctionnalité de surveillance. Toutefois, vous devrez déployer SQL Server lui-même ; les bases de données de surveillance seront créés pour vous lorsque vous publiez votre Skype pour la topologie du serveur de l’entreprise.
  
 **Le type de données que vous souhaitez surveiller ?** Skype pour Business Server 2015 vous permet de contrôler deux types généraux de données : appel détaillant les données d’enregistrement (CDR) et qualité d’expérience (QoE). D’enregistrement des données fournit un moyen d’effectuer le suivi de l’utilisation de Skype pour les fonctionnalités de Business Server 2015 tels que la voix sur IP (VoIP) pour les appels ; instant messaging (IM) ; transferts de fichiers ; audio/vidéo (A / V) de conférence ; et sessions de partage d’application. Cette information vous aide à savoir quel Skype pour les fonctionnalités de Business Server 2015 sont utilisées (et qui ne le sont pas) et fournit également des informations que lorsque ces fonctionnalités sont utilisées. Les données QoE vous permettent de conserver un enregistrement de la qualité des appels audio et vidéo passés dans votre organisation, tout en vous informant sur le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets).
  
Si vous choisissez d’activer analyse dans Skype pour 2015 de serveur d’entreprise vous pouvez activer les CDR de surveillance et mesure de surveillance, ou vous pouvez choisir d’activer un type de surveillance tout en laissant l’autre type désactivé. Par exemple, supposons que vos utilisateurs se servent uniquement de la messagerie instantanée et du transfert de fichier, et ne passent pas d’appels audio ou vidéo. Dans ce cas, l’activation de la surveillance QoE s’avère superflue. De même, Skype pour Business Server 2015 facilite activer et désactiver l’analyse après que la surveillance a été déployée. Par exemple, il est possible que vous choisissiez de déployer la surveillance tout en laissant la surveillance QoE désactivée dans un premier temps. Si vos utilisateurs commencent à rencontrer des problèmes avec les appels audio et vidéo, vous pouvez alors activer la surveillance QoE et utiliser ces données pour vous aider à identifier et résoudre ces problèmes.
  
Il n’y a aucun avantage particulier (ou inconvénients) pour l’installation de surveillance en même temps que vous installez Skype pour Business Server 2015 ou installation d’analyse après avoir installé Skype pour Business Server 2015. Le point à retenir est que, avant l’installation de surveillance, vous devez sélectionner un ordinateur pour héberger le serveur principal magasin de surveillance et une version prise en charge de SQL Server doit être configuré sur cet ordinateur et de l’installation avant de pouvoir utiliser cet ordinateur pour la surveillance . Si vous avez déjà installé SQL Server sur un ordinateur et si cet ordinateur est prêt à l’emploi vous pouvez installer le contrôle en même temps que vous installez Skype pour Business Server 2015. Si vous ne disposez pas d’un ordinateur principal prêt puis vous pouvez procéder à l’installation de Skype pour Business Server 2015 par lui-même, puis installer le contrôle chaque fois que l’ordinateur principal est prêt à l’emploi.
  
 **Surveillance des bases de données de back-end combien vous faut-il ?** Il a été estimé qu’une base de données concurrentes pour la surveillance et l’archivage peut prendre en charge 240,000 Skype pour les utilisateurs de Business Server 2015). En outre, une base de données de surveillance unique peut être utilisé par plusieurs pools de Front-End ; Si vous avez trois pools frontal dans votre organisation vous pouvez associer tous les trois de ces pools avec la même banque de back-end.
  
Pour de nombreuses organisations, la capacité de base de données ne sera pas un facteur décisif pour la détermination du nombre de bases de données de surveillance principales requises. Il semblerait plutôt que la vitesse du réseau soit un point important. Supposons que vous possédez trois pools frontaux, mais qu’un de ses pools est situé sur une connexion réseau lente. Dans ce cas, vous voudrez probablement utiliser deux bases de données de surveillance : une pour les deux pools dotés d’une bonne connexion réseau et une pour le pool situé sur la connexion réseau lente.
  
Vous devez également prendre en compte que Skype pour Business Server 2015 prend en charge l’utilisation de bases de données miroir. La « mise en miroir de base de données » permet de conserver simultanément deux copies d’une base de données, se trouvant chacune sur un serveur différent. À chaque fois que des données sont écrites sur la base de données primaire, elles sont également écrites sur la base de données miroir. Si la base de données principale doit échouer ou sinon deviennent indisponible, vous pouvez « basculer » à la base de données mise en miroir à l’aide d’un simple Skype pour commande PowerShell de Business Server 2015. Par exemple :
  
```
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

Cela est important pour la planification, car la mise en miroir nécessite de doubler le nombre requis de bases de données : en plus de chaque base de données primaire vous aurez besoin d’une deuxième base de données pour servir de miroir.
  
 **Votre Skype pour les sites de Business Server 2015 avez besoin de leurs propre des configurations d’analyse personnalisées ?** Lorsque vous installez Skype pour Business Server 2015 vous installez également des collections globales CDR et QoE de paramètres de configuration ; Ces collections globales vous donnent la possibilité d’appliquer les mêmes paramètres de CD-r et QoE dans toute l’organisation. Dans bien des cas, cela suffira : souvent, vous souhaiterez activer la surveillance CDR pour tous vos utilisateurs.
  
Cependant, il peut aussi arriver que vous souhaitiez appliquer différents paramètres à différents sites. Par exemple, vous pouvez vouloir utiliser les surveillances CDR et QoE pour votre site de Redmond, mais seulement la surveillance CDR pour votre site de Dublin. De même, vous pouvez avoir besoin de conserver les données de surveillance pendant 60 jours pour le site de Redmond, mais seulement pendant 30 jours pour le site de Dublin. Skype pour Business Server 2015 permet de créer des collections distinctes, CDR et QoE de paramètres de configuration au niveau de l’étendue du site ; qui vous permet de gérer différemment de chaque site. Cela vous permet de gérer différemment chaque site (cela inclut l’activation et la désactivation de la surveillance, ainsi que la configuration des paramètres de gestion tels que la durée de conservation des données.)
  
Remarquez que vous pouvez prendre cette décision avant de déployer la surveillance ou après. Par exemple, vous pouvez déployer la surveillance puis gérer l’intégralité de l’organisation en utilisant les paramètres globaux. Si vous changez d’avis, vous pouvez créer une collection distincte de paramètres pour le site de Redmond, puis utiliser ces paramètres pour gérer la surveillance pour Redmond (les paramètres appliqués sur l’étendue Site sont toujours prioritaires sur les paramètres appliqués sur l’étendue Global). Si vous changez encore d’avis, vous pouvez simplement supprimer les paramètres de configuration appliqués au site de Redmond. Lorsqu’une collection de paramètres de site est supprimée, la collection de paramètres globale sera automatiquement appliquée à ce site.
  
## <a name="sql-requirements-for-monitoring"></a>Configuration SQL requise pour la surveillance
<a name="topologies"> </a>

Quand vous activez la surveillance, les agents de collecte de données unifiée sont automatiquement installés et activés sur chaque serveur frontal. Vous aurez à installer et à configurer l’une des bases de données suivantes pour qu’elle serve de magasin principal de données pour vos données de surveillance :
  
- Microsoft SQL Server 2008 R2 Enterprise Edition (édition 64 bits).
    
- Microsoft SQL Server 2008 R2 Standard Edition (édition 64 bits).
    
- Microsoft SQL Server 2012 Enterprise Edition (édition 64 bits).
    
- Microsoft SQL Server 2012 Standard Edition (édition 64 bits).
    
- Microsoft SQL Server 2014 Enterprise Edition (édition 64 bits).
    
- Microsoft SQL Server 2014 Standard Edition (édition 64 bits).
    
Les versions 32 bits de SQL Server ne sont pas prises en charge en tant que magasin principal. Skype pour Business Server 2015 ne gère pas les éditions Express de SQL Server 2008 ou SQL Server 2012. Pour plus d’informations sur les besoins de la base de données de Skype pour Business Server 2015, consultez la rubrique [Prise en charge du logiciel de base de données](http://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx).
  
Les données d’analyse peuvent utiliser la même instance SQL Server que d’autres types de données. Généralement, la base de données des enregistrements des détails des appels (LcsCdr) et la base de données de qualité de l’expérience (QoEMetrics) utilisent la même instance SQL ; par ailleurs, ces deux bases de données utilisent souvent la même instance SQL que la base de données d’archivage (LcsLog). La seule limitation réelle concernant les instances SQL Server est que chaque instance SQL Server est limitée à :
  
- Une instance de la Skype pour la base de données back-end de Business Server 2015. (En règle générale, il est déconseillé que votre base de données analyse être colocalisés dans la même instance SQL, ou même sur le même ordinateur, comme la base de données back-end. Bien que techniquement possible, vous courez le risque de la surveillance à l’aide de l’espace disque requis par la base de données back-end de la base de données.) 
    
- une seule instance de la base de données LcsCdr ;
    
- une seule instance de la base de données QoEMetrics ;
    
- une seule instance de la base de données d’archivage.
    
Autrement dit, vous ne pouvez pas avoir deux instances de la base de données LcsCdr dans la même instance SQL Server. Pour utiliser plusieurs instances de cette base de données, vous devez configurer plusieurs instances SQL Server.
  
## <a name="see-also"></a>Voir aussi
<a name="topologies"> </a>

#### 

[Déploiement de surveillance](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

