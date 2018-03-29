---
title: Services de domaine Active Directory pour Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Les Services de domaine Active Directory fonctionne comme le service d’annuaire pour les réseaux Windows Server 2003, Windows Server 2008, Windows Server 2012 et Windows Server 2012 R2. Les Services de domaine Active Directory sert également de la Fondation sur laquelle repose le Skype pour l’infrastructure de sécurité de Business Server 2015. L’objectif de cette section est de décrire comment Skype pour Business Server 2015 utilise les Services de domaine Active Directory pour créer un environnement digne de confiance pour la messagerie instantanée, les conférences Web, media et voix. Pour plus d’informations sur la préparation de votre environnement pour les Services de domaine Active Directory, consultez Installation de Skype pour Business Server 2015 dans la documentation de déploiement. Pour plus d’informations sur le rôle des Services de domaine Active Directory dans les réseaux Windows Server, consultez la documentation de la version du système d’exploitation que vous utilisez.
ms.openlocfilehash: eb4a2d5a070f7840733dd20da859d2dede38750a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="active-directory-domain-services-for-skype-for-business-server-2015"></a>Services de domaine Active Directory pour Skype Entreprise Server 2015
 
Les Services de domaine Active Directory fonctionne comme le service d’annuaire pour les réseaux Windows Server 2003, Windows Server 2008, Windows Server 2012 et Windows Server 2012 R2. Les Services de domaine Active Directory sert également de la Fondation sur laquelle repose le Skype pour l’infrastructure de sécurité de Business Server 2015. L’objectif de cette section est de décrire comment Skype pour Business Server 2015 utilise les Services de domaine Active Directory pour créer un environnement digne de confiance pour la messagerie instantanée, les conférences Web, media et voix. Pour plus d’informations sur la préparation de votre environnement pour les Services de domaine Active Directory, consultez [Installation de Skype pour Business Server 2015](../../deploy/install/install.md) dans la documentation de déploiement. Pour plus d’informations sur le rôle des Services de domaine Active Directory dans les réseaux Windows Server, consultez la documentation de la version du système d’exploitation que vous utilisez.
  
Skype pour Business Server 2015 utilise les Services de domaine Active Directory pour stocker :
  
- Paramètres globaux qui exigent de tous les serveurs exécutant Skype pour 2015 de serveur d’entreprise dans une forêt.
    
- Informations sur le service qui identifie les rôles de tous les serveurs exécutant Skype pour 2015 de serveur d’entreprise dans une forêt.
    
- Certains paramètres utilisateur.
    
## <a name="active-directory-infrastructure"></a>Infrastructure Active Directory

Exigences de l’infrastructure pour Active Directory sont les suivants :
  
- Systèmes d’exploitation requis pour les contrôleurs de domaine
    
- Exigences de niveau fonctionnel de domaine et de forêt
    
- Exigences de domaine de catalogue global
    
Pour plus d’informations, reportez-vous à la section [exigences environnementales pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) dans la documentation de déploiement.
  
## <a name="universal-groups"></a>Groupes universels

Lors de la préparation de la forêt, Skype pour Business Server 2015 crée plusieurs groupes universels dans les Services de domaine Active Directory qui ont l’autorisation d’accéder et de gérer les paramètres globaux et les services. Ces groupes universels incluent :
  
- **Groupes administratifs**. Ces groupes définissent les rôles d’administrateur fondamentales pour un Skype pour réseau de serveur d’entreprise. Au cours de la préparation de la forêt, ces groupes administrateur sont ajoutés à Skype pour les groupes d’infrastructure de serveur d’entreprise.
    
- **Groupes de service**. Ces groupes sont des comptes de service qui sont nécessaires pour accéder aux différents services fournis par Skype pour Business Server.
    
- **Groupes d’infrastructure**. Ces groupes des droits d’accéder à des zones spécifiques de la Skype pour infrastructure de serveur d’entreprise. Ils fonctionnent comme des composants de groupes administratifs et vous ne devez pas les modifier ni leur ajouter directement des utilisateurs. Lors de la préparation de la forêt, des groupes de service et d’administration spécifiques sont ajoutés aux groupes d’infrastructure appropriés.
    
Pour plus d’informations sur les groupes universels spécifiques créés lors de la préparation d’Active Directory pour Skype pour Business Server, ainsi que les groupes d’administration et de service qui sont ajoutés à des groupes à l’infrastructure, consultez [les modifications apportées par la préparation de la forêt dans Skype pour entreprise Serveur](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) dans la documentation de déploiement.
  
> [!NOTE]
> Skype pour Business Server 2015 prend en charge les groupes universels dans le Windows Server 2012, ainsi que les systèmes d’exploitation de Windows Server 2003 pour les contrôleurs de domaine. Les membres de groupes universels peuvent inclure d’autres groupes et comptes provenant de n’importe quel domaine de l’arbre ou de la forêt de domaines et peuvent se voir attribuer des autorisations dans n’importe quel domaine également. Prise en charge du groupe universel, associé à la délégation de l’administrateur, simplifie la gestion d’un Skype pour le déploiement du serveur de l’entreprise. Par exemple, il n’est pas nécessaire d’ajouter un domaine à un autre domaine pour permettre à un administrateur de les gérer tous les deux. 
  
## <a name="role-based-access-control"></a>Contrôle d’accès basé sur un rôle

En plus de créer des groupes de service et d’administration universels et d’ajouter des groupes de service et d’administration aux groupes universels appropriés, la préparation de forêt crée également des groupes de Contrôle d’accès basé sur un rôle (RBAC). Pour plus d’informations sur les groupes RBAC spécifiques créés en préparation de la forêt, reportez-vous à la section [modifications apportées par la préparation de la forêt dans Skype pour Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) dans la documentation de déploiement. Pour plus d’informations sur les groupes RBAC, consultez [contrôle d’accès basé sur les rôles (RBAC) pour Skype pour Business Server 2015](role-based-access-control-rbac.md).
  
## <a name="access-control-entries-aces-and-inheritance"></a>Entrées de contrôle d’accès (ACE) et héritage

La préparation de la forêt crée des ACE privées et publiques et ajoute des ACE pour les groupes universels qu’elle crée. Il crée des entrées ACE spécifiques privés sur le conteneur Paramètres globaux utilisé par Skype pour Business Server. Ce conteneur est utilisé uniquement par Skype pour Business Server et se trouve dans le conteneur Configuration ou le conteneur système dans le domaine racine, selon où vous stockez les paramètres globaux.
  
L’étape de préparation du domaine ajoute les entrées de contrôle d’accès (ACE) nécessaires aux groupes universels qui permettent d’héberger et de gérer les utilisateurs au sein du domaine. La préparation de domaine crée des ACE à la racine du domaine et dans trois conteneurs intégrés : Utilisateur, Ordinateurs et Contrôleurs de domaine.
  
Pour plus d’informations sur les entrées ACE publics créé et ajouté à la préparation de la forêt et de la préparation du domaine, reportez-vous à la section [modifications apportées par la préparation de la forêt dans Skype pour le serveur de l’entreprise](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) et les [modifications apportées par la préparation du domaine dans Skype pour Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md) dans le Documentation sur le déploiement.
  
Organisations verrouillent souvent des Services de domaine Active Directory (AD DS) pour aider à atténuer les risques de sécurité. Toutefois, un environnement Active Directory de verrouillage peut limiter les autorisations requises par Skype pour Business Server 2015. Ceci peut inclure la suppression des ACE des conteneurs et des unités d’organisation (OU) et la désactivation de l’héritage des autorisations sur les objets Utilisateur, Contact, InetOrgPerson ou Ordinateur. Dans un texte verrouillé vers le bas de l’environnement Active Directory, autorisations doivent être définies manuellement sur des conteneurs et unités d’organisation qui en ont besoin.
  
## <a name="server-information"></a>Informations du serveur

Lors de l’activation, Skype pour Business Server 2015 publie des informations sur le serveur dans les trois emplacements suivants dans les Services de domaine Active Directory :
  
- Une connexion de service point (SCP) sur l’objet ordinateur Active Directory correspondant à un ordinateur physique sur lequel Skype pour Business Server 2015 est installé.
    
- Les objets Serveur créés dans le conteneur de la classe **msRTCSIP-Pools**.
    
- Serveurs de confiance spécifiés dans le Générateur de topologies.
    
## <a name="service-connection-points"></a>Points de connexion de service

Chaque Skype pour objet 2015 de serveur d’entreprise dans les Services de domaine Active Directory a un SCP appelé Services RTC, qui à son tour contient un certain nombre d’attributs qui identifient chaque ordinateur et spécifier les services qu’il fournit. Le SCP plus important entre les attributs sont *serviceBindingInformation* , la *serviceDNSNameType* , *serviceClassname* et *serviceDNSName* . Les applications de gestion des actifs tiers peuvent récupérer les informations du serveur sur un déploiement en émettant des requêtes concernant ces données et d’autres attributs de points de connexion de service.
  
## <a name="active-directory-server-objects"></a>Objets de serveur Active Directory

Chaque Skype pour le rôle de serveur d’entreprise serveur 2015 a un Active Directory correspondant objet dont les attributs définissent les services fournis par ce rôle. Également, lors de l’activation d’un serveur Standard Edition server ou lors de la création d’un pool Enterprise Edition, Skype pour Business Server 2015 crée un nouvel objet **msRTCSIP-Pool** dans le conteneur de **Pools msRTCSIP** . La classe **msRTCSIP-Pool ** spécifie le nom de domaine complet (FQDN) du pool, ainsi que l’association entre les composants frontaux et principaux du pool. (Un serveur Standard Edition server est considéré comme un regroupement logique dont les extrémités avant et arrière sont COLOCALISÉES sur un seul ordinateur.)
  
## <a name="trusted-servers"></a>Serveurs approuvés

Dans Skype pour Business Server 2015, les serveurs de confiance sont celles spécifiées lorsque vous exécutez le Générateur de topologies et publiez votre topologie. La topologie publiée, y compris toutes les informations du serveur, est enregistrée dans le magasin central de gestion. Seuls les serveurs définis dans le magasin central de gestion sont approuvés. Dans Skype pour Business Server 2015, un serveur de confiance est celle qui répond aux critères suivants :
  
- Le nom de domaine complet (FQDN) du serveur se trouve dans la topologie enregistrée dans le magasin central de gestion.
    
- Le serveur présente un certificat valide d’une autorité de certification approuvée. Pour plus d’informations, reportez-vous à la section [exigences environnementales pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
    
Si l’un de ces critères est manquant, le serveur n’est pas approuvé et la connexion avec celui-ci est refusée. Cette double exigence empêche une attaque possible, si peu probable, dans lequel un serveur non autorisé tente de prendre en charge le nom de domaine complet d’un serveur valide.
  
En outre, pour Microsoft Office Communications Server 2007 R2 et les déploiements de Microsoft Office Communications Server 2007 communiquer avec Skype pour les serveurs d’entreprise serveur 2015, Skype pour Business Server 2015 crée des conteneurs au cours de la forêt Préparation pour maintenir des listes de serveurs de confiance pour les versions précédentes. Le tableau suivant décrit les conteneurs créés pour permettre la compatibilité avec les déploiements précédents.
  
**Confiance des listes de serveurs et de leurs conteneurs Active Directory pour assurer la compatibilité avec les versions précédentes**

|**Liste de serveurs approuvés**|**Conteneur Active Directory**|
|:-----|:-----|
|Serveurs Standard Edition et serveurs frontaux du pool d’entreprise  <br/> |RTC Service/Paramètres globaux  <br/> |
|Serveurs de conférence  <br/> |RTC Service/MCU approuvés  <br/> |
|Serveurs de composants Web  <br/> |RTC Service/TrustedWebComponentsServers  <br/> |
|Serveurs de médiation et serveurs Communicator Web Access, serveur d’application, serveur d’inscriptions avec QoE, service de conférence A/V (également serveurs SIP tiers)  <br/> |RTC Service/Services approuvés  <br/> |
|Serveurs proxy  <br/> |Skype pour Business Server 2015 ne gère pas la compatibilité descendante pour les serveurs proxy  <br/> |
   

