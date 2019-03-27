---
title: La récupération d’urgence dans Skype fin pool de serveurs frontaux pour Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
description: La récupération d’urgence, Skype pour Business Server offre pool jumelage avec basculement en cas d’un pool tombe en panne.
ms.openlocfilehash: 56108fe2187b37fd6f3094d68a8cc89bac436bea
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897422"
---
# <a name="front-end-pool-disaster-recovery-in-skype-for-business-server"></a>La récupération d’urgence dans Skype fin pool de serveurs frontaux pour Business Server
 
La récupération d’urgence, Skype pour Business Server offre pool jumelage avec basculement en cas d’un pool tombe en panne.
  
Pour les plus robuste d’urgence récupération options Skype pour Business Server, déployer paires de pools frontaux à deux sites géographiquement dispersés. Chaque site possède un pool frontal couplé à un pool frontal correspondant dans l’autre site. Les deux sites sont actifs, et le service de sauvegarde assure la réplication des données en temps réel pour garder les pools synchronisés. Si vous souhaitez mettre en œuvre Front-End du jumelage des pools, voir [Deploy couplé pools frontaux pour la récupération d’urgence dans Skype pour Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md) .
  
![Montre les pools frontaux sur deux sites différents, couplés](../../media/f74533c0-a10e-4f18-85a8-b9a008497573.jpg)
  
Si le pool dans un site échoue, vous pouvez basculer les utilisateurs de ce pool vers le pool dans l’autre site, qui fournit alors les services à tous les utilisateurs dans les deux pools. À des fins de planification de capacité, vous devez concevoir chaque pool pour gérer la charge de travail de tous les utilisateurs dans les deux pools en cas de sinistre.
  
La distance séparant deux centres de données qui comprennent des pools frontaux associés l’un à l’autre n’est pas limitée. Nous vous recommandons de relier deux centres de données qui se trouvent dans la même région du monde par des connexions haut débit. 
  
Il est possible d’avoir deux centres de données situés dans des régions du monde différentes, mais cette situation peut entraîner une perte de données plus importante en cas de sinistre en raison de la latence de la réplication de données.
  
Quand vous préparez le jumelage des pools, gardez à l’esprit que seuls les jumelages suivants sont pris en charge :
  
- Les pools Enterprise Edition peuvent uniquement être jumelés avec d’autres pools Enterprise Edition. De même, les pools Standard Edition peuvent uniquement être jumelés avec d’autres pools Standard Edition.
    
- Les pools physiques peuvent uniquement être jumelés avec d’autres pools physiques. De même, les pools virtuels peuvent uniquement être jumelés avec d’autres pools virtuels.
    
- Les pools associés doivent exécuter le même système d’exploitation de base.
    
Ni le générateur de topologie, ni la validation des topologies n’empêcheront le jumelage de deux pools qui ne suit pas ces recommandations. Par exemple, le générateur de topologie vous permet de jumeler un pool Enterprise Edition avec un pool Standard Edition. Cependant, ces types de jumelages ne sont pas pris en charge.
  
## <a name="backup-registrar-relationships-and-survivable-branch-appliances"></a>Relations des serveurs d’inscriptions de sauvegarde et de Survivable Branch Appliances

En plus de fournir une fonctionnalité de récupération d’urgence, deux pools associés jouent le rôle de serveur d’inscriptions de sauvegarde l’un pour l’autre. Chaque pool peut être la sauvegarde pour qu’un autre pool frontal.
  
Même si les relations de sauvegarde entre deux pools frontaux doivent être 1:1 et symétriques, chaque pool frontal peut également être le serveur d’inscriptions de sauvegarde de plusieurs Survivable Branch Appliances.
  
Remarquez que Skype Entreprise n’étend pas la prise en charge de la récupération d’urgence aux utilisateurs hébergés sur un Survivable Branch Appliance. Si un pool frontal qui joue le rôle de sauvegarde pour un Survivable Branch Appliance ne fonctionne plus, les utilisateurs connectés au Survivable Branch Appliance passent en mode résilience même après le basculement des utilisateurs hébergés sur le pool frontal vers le pool frontal de sauvegarde.
  
## <a name="recovery-time-for-pool-failover-and-pool-failback"></a>Temps de récupération nécessaire pour basculer et restaurer les pools

Pour le basculement de pool et la restauration de pool, le but à atteindre pour la durée maximale d’interruption admissible (RTO) est de 15-20 minutes. Il s’agit de la durée nécessaire pour que le basculement ait lieu, une fois que les administrateurs ont identifié une panne et lancé les procédures de basculement. Cette durée ne comprend pas le temps nécessaire aux administrateurs pour évaluer la situation et prendre une décision, ni le temps nécessaire aux utilisateurs pour se connecter une fois le basculement terminé.
  
Pour le basculement de pool et la restauration de pool, le but à atteindre pour la perte de données maximale admissible (RPO) est de 5 minutes. Cela représente une mesure en temps des données qui pourraient être perdues en raison de la panne, en raison de la latence de réplication du service de sauvegarde. Par exemple, si un pool tombe en panne à 10:00, et le RPO est de 5 minutes, les données écrites dans le pool entre 9:55:00 et 10 heures du matin .might pas répliqués vers le pool de sauvegarde et seraient perdus.
  
Les chiffres de RTO et de RPO de ce document considèrent que les deux centres de données sont situés dans la même région du monde avec un transport haute vitesse à faible latence entre les deux sites. Ces chiffres sont mesurés pour un pool avec 40 000 utilisateurs actifs et 200 000 utilisateurs activés pour Lync par rapport à un modèle utilisateur prédéfini pour lequel il n’y a pas de journal des travaux en souffrance dans la réplication des données. Ces chiffres peuvent changer en fonction du test et de la validation des performances.
  
## <a name="central-management-store-failover"></a>Basculement du magasin central de gestion

Le magasin central de gestion contient des données de configuration relatives aux serveurs et aux services dans votre déploiement. Chaque Skype pour le déploiement de Business Server inclut un magasin Central de gestion, qui est hébergé par le serveur principal d’un pool frontal.
  
Si vous associez le pool qui héberge le magasin central de gestion, une base de données de sauvegarde du magasin central de gestion est configurée dans le pool de sauvegarde. L’une des deux bases de données du magasin central de gestion est toujours active tandis que l’autre constitue la base de données de secours. Le contenu est répliqué par le service de sauvegarde de la base de données active vers la base de données de secours.
  
![Montre deux pools frontaux, un avec le magasin CMS actif et l’autre avec le magasin CMS passif](../../media/aa479398-eb56-4854-8d50-1eff39c58a56.jpg)
  
Durant un basculement de pool impliquant les pools hébergeant le magasin central de gestion, vous devez faire basculer le magasin central de gestion avant le basculement du pool frontal.
  
Une fois la récupération d’urgence effectuée, il n’est pas nécessaire de rebasculer le magasin central de gestion. Le magasin central de gestion peut rester dans le pool vers lequel vous avez effectué le basculement.
  
Les objectifs d’ingénierie du basculement du magasin central de gestion sont les suivants : un objectif de durée de reprise (RTO) de 5 minutes et 5 minutes pour chaque objectif de point de reprise (RPO).
  
## <a name="front-end-pool-pairing-data-security"></a>Sécurité des données d’appariement de pools frontaux

Le service de sauvegarde transfère les données utilisateur et le contenu de conférence entre deux pools frontaux associés de manière continue. Les données utilisateur contiennent des URI SIP d’utilisateur, ainsi que des paramètres et listes de contacts. Le contenu de conférence inclut des téléchargements Microsoft PowerPoint ainsi que les tableaux blancs utilisés lors des conférences.
  
Dans le pool source, ces données sont exportées à partir du stockage local, compressées, transférées au pool cible, où elles sont décompressées, et importées vers le stockage local. Le service de sauvegarde part du principe que le lien de communication entre les deux centres de données est à l’intérieur du réseau d’entreprise qui est protégé d’Internet. Il ne chiffre pas les données transférées entre les deux centres de données, et n’est pas non plus encapsulé de manière native dans un protocole sécurisé, tel que HTTPS. Par conséquent, une attaque man-in-the-middle du personnel interne au sein du réseau d’entreprise est possible.
  
Toute entreprise qui déploie Skype pour Business Server dans plusieurs centres de données et utilise la fonctionnalité de récupération d’urgence devez vous assurer que le trafic entre les centres de données est protégé par leur Intranet d’entreprise. Les entreprises qui se soucient de la protection contre les attaques internes doivent sécuriser les liens de communication entre les centres de données. Cette exigence standard permet également de protéger de nombreux autres types de données professionnelles confidentielles transférées entre ces centres de données.
  
Si le risque d’attaques de l’intercepteur (« man-in-the-middle ») sur le réseau d’entreprise existe, il est relativement contrôlé en comparaison de l’exposition du trafic sur Internet. Plus précisément, les données utilisateur exposées par le service de sauvegarde (tels les URI SIP) sont généralement disponibles pour tous les employés de l’entreprise via d’autres moyens tels que le carnet d’adresses global ou un autre logiciel de répertoire. Votre attention doit donc être portée sur la sécurisation du réseau étendu (WAN) entre les deux centres de données lorsque le service de sauvegarde est utilisé pour copier les données entre les deux pools associés.
  
### <a name="mitigating-security-risks"></a>Réduction des risques de sécurité

Vous disposez de plusieurs méthodes vous permettent d’améliorer la protection de sécurité pour le trafic de Service de sauvegarde. Cela va de restriction de l’accès aux centres de données à la sécurisation du réseau étendu transport entre les deux centres de données. Dans la plupart des cas, les entreprises déploiement Skype pour Business Server peut-être déjà en place l’infrastructure de sécurité requis. Pour les entreprises de la recherche pour obtenir des instructions, Microsoft fournit une solution à titre d’exemple de construction d’une infrastructure informatique sécurisée. Pour plus d’informations, voir [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?LinkId=268544). 
  
Nous n’impliquent que c’est la seule solution, ni nous implique qu’il est préférable de Skype pour Business Server. Nous recommandons aux clients professionnels de choisir la solution qui répond à leurs besoins spécifiques en fonction de leur infrastructure et de leurs exigences en matière de sécurité informatique. La solution exemple de Microsoft a recours à IPSec et la Stratégie de groupe pour l’isolation de serveur et de domaine.
  
Une autre solution possible consiste à utiliser IPSec simplement pour sécuriser les données envoyées par le service de sauvegarde proprement dit. Si vous choisissez cette méthode, vous devez configurer les règles IPSec du protocole SMB pour les serveurs ci-dessous, où le pool A et le pool B sont deux pools frontaux associés.
  
- Service SMB (TCP/445) de chaque serveur frontal dans le pool A vers le magasin de fichiers utilisé par le pool B.
    
- Service SMB (TCP/445) de chaque serveur frontal dans le pool B vers le magasin de fichiers utilisé par le pool A.
    
> [!CAUTION]
>  IPsec n’est pas destiné à remplacer la sécurité au niveau de l’application, comme SSL/TLS. L’intérêt d’utiliser IPsec est qu’il peut assurer la sécurité du trafic réseau pour les applications existantes sans avoir à les modifier. Les entreprises want sécuriser simplement le transport entre les deux centres de données, consultez leurs fournisseurs de matériel réseau respectifs sur les moyens de définir des connexions WAN sécurisées à l’aide d’équipement du fournisseur.
  
## <a name="see-also"></a>Voir aussi

[Déployer les pools frontaux couplés pour la récupération d’urgence dans Skype pour Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)
