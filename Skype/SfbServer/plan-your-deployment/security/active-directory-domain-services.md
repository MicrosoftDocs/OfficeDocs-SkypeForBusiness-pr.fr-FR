---
title: Services de domaine Active Directory pour Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Services de domaine Active Directory fonctionne comme service d’annuaire pour les réseaux Windows Server 2003, Windows Server 2008, Windows Server 2012 et Windows Server 2012 R2. Services de domaine Active Directory sert également de base sur laquelle repose le Skype pour l’infrastructure de sécurité Business Server. L’objectif de cette section est de décrire comment Skype pour Business Server utilise les Services de domaine Active Directory pour créer un environnement sûr pour la messagerie instantanée, la conférence Web, multimédia et voix. Pour plus d’informations sur la préparation de votre environnement pour les Services de domaine Active Directory, voir Skype installer for Business Server dans la documentation de déploiement. Pour plus d’informations sur le rôle des Services de domaine Active Directory dans les réseaux Windows Server, voir la documentation de la version du système d’exploitation que vous utilisez.
ms.openlocfilehash: ba37ffb806951a6726478b5404c7ff756a9f9522
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888077"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>Services de domaine Active Directory pour Skype pour Business Server
 
Services de domaine Active Directory fonctionne comme service d’annuaire pour les réseaux Windows Server 2003, Windows Server 2008, Windows Server 2012 et Windows Server 2012 R2. Services de domaine Active Directory sert également de base sur laquelle repose le Skype pour l’infrastructure de sécurité Business Server. L’objectif de cette section est de décrire comment Skype pour Business Server utilise les Services de domaine Active Directory pour créer un environnement sûr pour la messagerie instantanée, la conférence Web, multimédia et voix. Pour plus d’informations sur la préparation de votre environnement pour les Services de domaine Active Directory, voir [Installation de Skype pour Business Server](../../deploy/install/install.md) dans la documentation de déploiement. Pour plus d’informations sur le rôle des Services de domaine Active Directory dans les réseaux Windows Server, voir la documentation de la version du système d’exploitation que vous utilisez.
  
Skype pour Business Server utilise les Services de domaine Active Directory pour stocker :
  
- Paramètres globaux qui requièrent tous les serveurs exécutant Skype pour Business Server dans une forêt.
    
- Informations de service qui identifient les rôles de tous les serveurs exécutant Skype pour Business Server dans une forêt.
    
- Certains paramètres utilisateur.
    
## <a name="active-directory-infrastructure"></a>Infrastructure Active Directory

Conditions d’infrastructure requises pour Active Directory sont les suivantes :
  
- Systèmes d’exploitation requis pour les contrôleurs de domaine
    
- Exigences de niveau fonctionnel de domaine et de forêt
    
- Exigences de domaine de catalogue global
    
Pour plus d’informations, consultez [exigences pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [configuration serveur requise pour Skype pour Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
## <a name="universal-groups"></a>Groupes universels

Pendant la préparation de la forêt, Skype pour Business Server crée différents groupes universels dans les Services de domaine Active Directory qui ont l’autorisation d’accéder et de gérer les services et les paramètres globaux. Ces groupes universels incluent :
  
- **Groupes administratifs**. Ces groupes définissent les rôles d’administrateur fondamentaux pour un Skype pour réseau Business Server. Pendant la préparation de la forêt, ces groupes d’administrateurs sont ajoutés à Skype pour les groupes d’infrastructure Business Server.
    
- **Groupes de service**. Ces groupes sont des comptes de service qui sont nécessaires pour accéder à différents services fournis par Skype pour Business Server.
    
- **Groupes d’infrastructure**. Ces groupes accordent des autorisations pour accéder à des zones spécifiques de le Skype pour l’infrastructure de serveur d’entreprise. Ils fonctionnent comme des composants de groupes administratifs et vous ne devez pas les modifier ni leur ajouter directement des utilisateurs. Lors de la préparation de la forêt, des groupes de service et d’administration spécifiques sont ajoutés aux groupes d’infrastructure appropriés.
    
Pour plus d’informations sur les groupes universels spécifiques créés lors de la préparation d’Active Directory pour Skype pour Business Server, ainsi que les groupes d’administration et de service qui sont ajoutés aux groupes d’infrastructure, voir [modifications effectuées par la préparation de la forêt dans Skype pour les entreprises Serveur](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) dans la documentation de déploiement.
  
> [!NOTE]
> Skype pour Business Server prend en charge les groupes universels dans Windows Server 2012, ainsi que les systèmes d’exploitation de Windows Server 2003 pour les contrôleurs de domaine. Les membres de groupes universels peuvent inclure d’autres groupes et comptes provenant de n’importe quel domaine de l’arbre ou de la forêt de domaines et peuvent se voir attribuer des autorisations dans n’importe quel domaine également. Prise en charge du groupe universel, alliée à la délégation, simplifie la gestion d’un Skype pour le déploiement de serveur d’entreprise. Par exemple, il n’est pas nécessaire d’ajouter un domaine à un autre domaine pour permettre à un administrateur de les gérer tous les deux. 
  
## <a name="role-based-access-control"></a>Contrôle d’accès basé sur un rôle

En plus de créer des groupes de service et d’administration universels et d’ajouter des groupes de service et d’administration aux groupes universels appropriés, la préparation de forêt crée également des groupes de Contrôle d’accès basé sur un rôle (RBAC). Pour plus d’informations sur les groupes RBAC spécifiques créés par la préparation de la forêt, voir [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) dans la documentation de déploiement. Pour plus d’informations sur les groupes de RBAC, voir [contrôle d’accès basé sur un rôle (RBAC) pour Skype pour Business Server](role-based-access-control-rbac.md).
  
## <a name="access-control-entries-aces-and-inheritance"></a>Entrées de contrôle d’accès (ACE) et héritage

La préparation de la forêt crée des ACE privées et publiques et ajoute des ACE pour les groupes universels qu’elle crée. Il crée ACE privées spécifiques sur le conteneur des paramètres globaux utilisé par Skype pour Business Server. Ce conteneur est utilisé uniquement par Skype pour Business Server et se trouve dans le conteneur de Configuration ou dans le conteneur système dans le domaine racine, en fonction de dans lequel vous stockez les paramètres globaux.
  
L’étape de préparation du domaine ajoute les entrées de contrôle d’accès (ACE) nécessaires aux groupes universels qui permettent d’héberger et de gérer les utilisateurs au sein du domaine. La préparation de domaine crée des ACE à la racine du domaine et dans trois conteneurs intégrés : Utilisateur, Ordinateurs et Contrôleurs de domaine.
  
Pour plus d’informations sur les ACE publics créé et ajouté à la préparation de la forêt et du domaine, consultez [modifications effectuées par la préparation de la forêt dans Skype pour Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) et les [modifications effectuées par la préparation du domaine dans Skype pour Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md) dans le Documentation de déploiement.
  
Organisations verrouillent souvent les Services de domaine Active Directory (AD DS) pour atténuer les risques de sécurité. Toutefois, un environnement d’Active Directory verrouillé peut limiter les autorisations requises Skype pour Business Server. Ceci peut inclure la suppression des ACE des conteneurs et des unités d’organisation (OU) et la désactivation de l’héritage des autorisations sur les objets Utilisateur, Contact, InetOrgPerson ou Ordinateur. Dans un élément verrouillé vers le bas de l’environnement Active Directory, les autorisations doivent être définies manuellement sur les conteneurs et unités d’organisation qui en ont besoin.
  
## <a name="server-information"></a>Informations du serveur

Durant l’activation, Skype pour Business Server publie des informations sur le serveur aux trois emplacements suivants dans les Services de domaine Active Directory :
  
- Une connexion de service point (SCP) sur chaque objet ordinateur de Active Directory correspondant à un ordinateur physique sur lequel Skype pour Business Server est installé.
    
- Les objets Serveur créés dans le conteneur de la classe **msRTCSIP-Pools**.
    
- Serveurs approuvés spécifiés dans le Générateur de topologie.
    
## <a name="service-connection-points"></a>Points de connexion de service

Chaque Skype pour objet Business Server dans les Services de domaine Active Directory a un SCP appelé Services RTC, qui à son tour contient un nombre d’attributs qui identifient chaque ordinateur et de spécifier les services qu’il fournit. Parmi le plus important SCP les attributs sont *notamment serviceDNSName* , *serviceDNSNameType* , *serviceClassname* et *serviceBindingInformation* . Les applications de gestion des actifs tiers peuvent récupérer les informations du serveur sur un déploiement en émettant des requêtes concernant ces données et d’autres attributs de points de connexion de service.
  
## <a name="active-directory-server-objects"></a>Objets serveur Active Directory

Chaque Skype pour le rôle de serveur Business Server possède un annuaire Active Directory correspondant d’objet dont les attributs définissent les services fournis par le rôle. En outre, lorsqu’un serveur Standard Edition server est activé, ou lors de la création d’un pool Enterprise Edition, Skype pour Business Server crée un nouvel objet **msRTCSIP-Pool** dans le conteneur **msRTCSIP-Pools** . La classe **msRTCSIP-Pool ** spécifie le nom de domaine complet (FQDN) du pool, ainsi que l’association entre les composants frontaux et principaux du pool. (Un serveur Standard Edition server est considéré comme un pool logique dont avant et arrière sont colocalisés sur un seul ordinateur.)
  
## <a name="trusted-servers"></a>Serveurs approuvés

Dans Skype pour Business Server, les serveurs approuvés sont celles spécifiées lorsque vous exécutez le Générateur de topologie et publiez votre topologie. La topologie publiée, y compris toutes les informations du serveur, est enregistrée dans le magasin central de gestion. Seuls les serveurs définis dans le magasin central de gestion sont approuvés. Dans Skype pour Business Server, un serveur approuvé doit satisfaire aux critères suivants :
  
- Le nom de domaine complet (FQDN) du serveur se trouve dans la topologie enregistrée dans le magasin central de gestion.
    
- Le serveur présente un certificat valide d’une autorité de certification approuvée. Pour plus d’informations, consultez [exigences pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou la [configuration système requise pour Skype pour Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
Si l’un de ces critères est manquant, le serveur n’est pas approuvé et la connexion avec celui-ci est refusée. Cette double exigence empêche une attaque possible, peu probable, dans laquelle un serveur non autorisé tente de prendre le nom de domaine complet d’un serveur valide.
  
En outre, pour activer les déploiements de Microsoft Office Communications Server 2007 R2 et Microsoft Office Communications Server 2007 communiquer avec Skype pour les serveurs d’entreprise, Skype pour Business Server crée des conteneurs pendant la préparation de la forêt destinés aux listes de serveurs approuvés pour les versions précédentes. Le tableau suivant décrit les conteneurs créés pour permettre la compatibilité avec les déploiements précédents.
  
**Approuvés des listes de serveurs et leurs conteneurs Active Directory pour assurer la compatibilité avec les versions précédentes**

|**Liste des serveurs approuvés**|**Conteneur Active Directory**|
|:-----|:-----|
|Serveurs Standard Edition et serveurs frontaux du pool d’entreprise  <br/> |RTC Service/Paramètres globaux  <br/> |
|Serveurs de conférence  <br/> |RTC Service/MCU approuvés  <br/> |
|Serveurs de composants Web  <br/> |RTC Service/TrustedWebComponentsServers  <br/> |
|Serveurs de médiation et serveurs Communicator Web Access, serveur d’application, serveur d’inscriptions avec QoE, service de conférence A/V (également serveurs SIP tiers)  <br/> |RTC Service/Services approuvés  <br/> |
|Serveurs proxy  <br/> |Skype pour Business Server ne prend pas en charge de compatibilité descendante pour les serveurs proxy  <br/> |
   

## <a name="see-also"></a>Voir aussi

[Préparer Active Directory pour Skype pour Business Server](../../deploy/install/prepare-active-directory.md)
