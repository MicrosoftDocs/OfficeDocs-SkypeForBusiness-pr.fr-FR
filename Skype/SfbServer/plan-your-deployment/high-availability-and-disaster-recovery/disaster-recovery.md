---
title: Récupération d’urgence du pool frontal dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
description: Pour la récupération d’urgence, Skype Entreprise Server offre le jumelage de pool avec leover en cas de panne d’un pool.
ms.openlocfilehash: b6a2c33c123f70850335ce55aba06071ff4104eb
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728833"
---
# <a name="front-end-pool-disaster-recovery-in-skype-for-business-server"></a>Récupération d’urgence du pool frontal dans Skype Entreprise Server
 
Pour la récupération d’urgence, Skype Entreprise Server offre le jumelage de pool avec leover en cas de panne d’un pool.
  
Pour les options de récupération d’urgence les plus robustes Skype Entreprise Server, déployez des paires de pools frontaux sur deux sites géographiquement dispersés. Chaque site possède un pool frontal associé à un pool frontal correspondant dans l’autre site. Les deux sites sont actifs et le service de sauvegarde fournit une réplication des données en temps réel pour maintenir la synchronisation des pools. Voir [Déployer des pools frontux](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md) couplés pour la récupération d’urgence dans Skype Entreprise Server si vous souhaitez implémenter le jumelage de pool frontal.
  
![Affiche les pools frontux sur deux sites différents, associés l’un à l’autre.](../../media/f74533c0-a10e-4f18-85a8-b9a008497573.jpg)
  
Si le pool d’un site échoue, vous pouvez faire échouer les utilisateurs de ce pool vers le pool de l’autre site, qui sert ensuite tous les utilisateurs des deux pools. Pour la planification de la capacité, vous devez concevoir chaque pool pour gérer la charge de travail de tous les utilisateurs des deux pools en cas d’incident.
  
Deux centres de données qui incluent des pools frontaux associés l’un à l’autre peuvent être séparés à n’importe quelle distance. Nous vous recommandons de coupler deux centres de données dans la même région du monde, avec des liens haut débit entre eux. 
  
Il est possible d’avoir deux centres de données dans différentes régions du monde, mais cela peut augmenter la perte de données en cas d’urgence, en raison de la latence dans la réplication des données.
  
Lorsque vous planifiez les pools à jumeler, vous devez garder à l’esprit que seuls les jumelages suivants sont pris en charge :
  
- Les pools Enterprise Edition peuvent uniquement être jumelés avec d’autres pools Enterprise Edition. De même, les pools Standard Edition peuvent uniquement être jumelés avec d’autres pools Standard Edition.
    
- Les pools physiques peuvent uniquement être jumelés avec d’autres pools physiques. De même, les pools virtuels peuvent uniquement être jumelés avec d’autres pools virtuels.
    
- Les pools associés doivent fonctionner sur le même système d’exploitation de base.
    
Ni le Générateur de topologie, ni la validation des topologies n’empêcheront le jumelage de deux pools qui ne suit pas ces recommandations. Par exemple, le Générateur de topologie vous permet de jumeler un pool Enterprise Edition avec un pool Standard Edition. Toutefois, ces types de jumelages ne sont pas pris en charge.
  
## <a name="backup-registrar-relationships-and-survivable-branch-appliances"></a>Relations du bureau d’enregistrement de sauvegarde et Survivable Branch Appliances

En plus de fournir une fonctionnalité de récupération d’urgence, deux pools associés jouent le rôle de serveur d’inscriptions de sauvegarde l’un pour l’autre. Chaque pool peut être la sauvegarde d’un seul autre pool frontal.
  
Même si les relations de sauvegarde entre deux pools frontux doivent être 1:1 et symétriques, chaque pool frontal peut toujours être le bureau d’enregistrement de sauvegarde pour n’importe quel nombre de Survivable Branch Appliances.
  
Notez que Skype Entreprise n’étend pas la prise en charge de la récupération d’urgence aux utilisateurs d’un Survivable Branch Appliance. Si un pool frontal qui sert de sauvegarde pour un Survivable Branch Appliance tombe en panne, les utilisateurs qui se sont inscrits au Survivable Branch Appliance tombent en mode résistance même si les utilisateurs qui sont homed on the Front End pool are failed over to the backup Front End pool.
  
## <a name="recovery-time-for-pool-failover-and-pool-failback"></a>Temps de récupération pour le failover et la restauration du pool

Pour leover de pool et la restauration de pool, la cible d’ingénierie pour l’objectif de temps de récupération (RTO) est de 15 à 20 minutes. Il s’agit du temps nécessaire pour que le failover se produise, une fois que les administrateurs ont déterminé qu’il y avait un sinistre et démarré les procédures deover. Cette durée ne comprend pas le temps nécessaire aux administrateurs pour évaluer la situation et prendre une décision, ni le temps nécessaire aux utilisateurs pour se connecter une fois le basculement terminé.
  
Pour le failover et la restauration de pool, la cible d’ingénierie pour l’objectif de point de récupération (RPO) est de 5 minutes. Cela représente une mesure en temps des données qui pourraient être perdues en raison de la panne, en raison de la latence de réplication du service de sauvegarde. Par exemple, si un pool est en panne à 10 h 00 et que le RPO est de 5 minutes, les données écrites dans le pool entre 9 h 55 et 09 h 55. et 10:00 A.M.might not have replicated to the backup pool, and would be lost.
  
Les chiffres de RTO et de RPO de ce document considèrent que les deux centres de données sont situés dans la même région du monde avec un transport haute vitesse à faible latence entre les deux sites. Ces nombres sont mesurés pour un pool avec 40 000 utilisateurs actifs simultanément et 200 000 utilisateurs activés pour Skype Entreprise par rapport à un modèle utilisateur prédéfiny où il n’existe aucun journal des travaux en souffrance dans la réplication des données. Ces chiffres peuvent changer en fonction du test et de la validation des performances.
  
## <a name="central-management-store-failover"></a>Failover du magasin central de gestion

Le magasin central de gestion contient des données de configuration sur les serveurs et les services de votre déploiement. Chaque Skype Entreprise Server comprend un magasin central de gestion, qui est hébergé par le serveur principal d’un pool frontal.
  
Si vous associez le pool qui héberge le magasin central de gestion, une base de données du magasin central de gestion de sauvegarde est définie dans le pool de sauvegarde. À tout moment, l’une des deux bases de données du magasin central de gestion est active et l’autre est une base de données de veille. Le contenu est répliqué par le service de sauvegarde de la base de données active vers la base de données de secours.
  
![Affiche deux pools frontaux, l’un avec le magasin CMS actif et l’autre avec le magasin CMS de sauvegarde passive.](../../media/aa479398-eb56-4854-8d50-1eff39c58a56.jpg)
  
Lors d’un changement de pool qui implique le pool hébergeant le magasin central de gestion, vous devez faire échouer le magasin central de gestion avant de faire échouer le pool frontal.
  
Une fois l’urgence réparée, il n’est pas nécessaire de faire échouer le magasin central de gestion. Le magasin central de gestion peut rester dans le pool vers qui vous l’avez fait échouer.
  
Les objectifs d’ingénierie pour le failover du magasin central de gestion sont de 5 minutes pour l’objectif de temps de récupération (RTO) et de 5 minutes pour l’objectif de point de récupération (RPO).
  
## <a name="front-end-pool-pairing-data-security"></a>Sécurité des données de jumelage de pool frontal

Le service de sauvegarde transfère en continu les données utilisateur et le contenu des conférences entre deux pools frontux couplés. Les données utilisateur contiennent des UR SIP utilisateur, ainsi que des planifications de conférence, des listes de contacts et des paramètres. Le contenu des conférences inclut PowerPoint téléchargements Microsoft, ainsi que les tableaux blancs utilisés dans les conférences.
  
À partir du pool source, ces données sont exportées à partir du stockage local, compressées, puis transférées vers le pool cible, où elles sont décompressées et importées vers le stockage local. Le service de sauvegarde suppose que le lien de communications entre les deux centres de données se trouve dans le réseau d’entreprise protégé contre Internet. Il ne chiffre pas les données transférées entre les deux centres de données, et les données ne sont pas encapsulées en natif dans un protocole sécurisé, tel que HTTPS. Par conséquent, une attaque de l’intermédiaire de la part du personnel interne au sein du réseau d’entreprise est possible.
  
Toute entreprise qui déploie des Skype Entreprise Server plusieurs centres de données et utilise la fonctionnalité de récupération d’urgence doit s’assurer que le trafic entre les centres de données est protégé par leur intranet d’entreprise. Les entreprises qui se soucient de la protection contre les attaques internes doivent sécuriser les liens de communication entre les centres de données. Il s’agit d’une exigence standard qui permet également aux protech de nombreux autres types de données sensibles d’entreprise transférées entre des centres de données.
  
Bien que le risque d’attaques de l’intermédiaire au sein du réseau d’entreprise existe, il est relativement contenu par rapport à l’exposition du trafic vers Internet. Plus précisément, les données utilisateur exposées par le service de sauvegarde (telles que les UR SIP) sont généralement disponibles pour tous les employés au sein de l’entreprise via d’autres moyens tels que le carnet d’adresses global ou d’autres logiciels d’annuaire. Par conséquent, vous devez vous concentrer sur la sécurisation du WAN entre les deux centres de données lorsque le service de sauvegarde est utilisé pour copier des données entre les deux pools couplés.
  
### <a name="mitigating-security-risks"></a>Atténuation des risques de sécurité

Vous avez plusieurs façons d’améliorer la protection de la sécurité pour le trafic du service de sauvegarde. Cela va de la restriction de l’accès aux centres de données à la sécurisation du transport WAN entre les deux centres de données. Dans la plupart des cas, les entreprises qui déploient Skype Entreprise Server ont peut-être déjà l’infrastructure de sécurité requise. Pour les entreprises qui recherchent des conseils, Microsoft fournit une solution qui illustre comment créer une infrastructure informatique sécurisée. Pour plus d’informations, voir [https://go.microsoft.com/fwlink/p/?LinkId=268544](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725770(v=ws.10)) . 
  
Nous ne voulons pas dire qu’il s’agit de la seule solution, ni qu’il s’agit de la solution préférée pour Skype Entreprise Server. Nous recommandons aux clients d’entreprise de choisir la solution qui répond à leurs besoins spécifiques, en fonction de leurs besoins et de leur infrastructure de sécurité informatique. L’exemple de solution Microsoft utilise IPSec et la stratégie de groupe pour l’isolation de serveur et de domaine.
  
Une autre solution possible consiste à utiliser IPSec uniquement pour sécuriser les données envoyées par le service de sauvegarde lui-même. Si vous choisissez cette méthode, vous devez configurer les règles IPSec pour le protocole SMB pour les serveurs suivants, où le pool A et le pool B sont deux pools frontaux couplés.
  
- Service SMB (TCP/445) de chaque serveur frontal du pool A vers le magasin de fichiers utilisé par le pool B.
    
- Service SMB (TCP/445) de chaque serveur frontal du pool B vers le magasin de fichiers utilisé par le pool A.
    
> [!CAUTION]
>  IPsec n’est pas destiné à remplacer la sécurité au niveau de l’application, telle que SSL/TLS. L’un des avantages de l’utilisation d’IPsec est qu’il peut assurer la sécurité du trafic réseau pour les applications existantes sans avoir à les modifier. Les entreprises qui souhaitent simplement sécuriser le transport entre les deux centres de données doivent consulter leurs fournisseurs de matériel réseau respectifs pour savoir comment configurer des connexions WAN sécurisées à l’aide de l’équipement du fournisseur.
  
## <a name="see-also"></a>Voir aussi

[Déployer des pools frontux couplés pour la récupération d’urgence dans Skype Entreprise Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)