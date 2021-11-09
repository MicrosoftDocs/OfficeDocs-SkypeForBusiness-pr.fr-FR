---
title: Services de domaine Active Directory pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Les services de domaine Active Directory fonctionnent en tant que service d’annuaire pour les réseaux Windows Server 2003, Windows Server 2008, Windows Server 2012 et Windows Server 2012 R2. Les services de domaine Active Directory servent également de base à la Skype Entreprise Server de sécurité de l’utilisateur. L’objectif de cette section est de décrire comment Skype Entreprise Server utilise les services de domaine Active Directory pour créer un environnement digne de confiance pour la messagerie instantanée, les conférences Web, les médias et la voix. Pour plus d’informations sur la préparation de votre environnement pour les services de domaine Active Directory, voir Install Skype Entreprise Server in the Deployment documentation. Pour des détails sur le rôle des services de domaine Active Directory dans les réseaux Windows Server, voir la documentation concernant votre version du système d’exploitation.
ms.openlocfilehash: a96d2691513ae98195856f717b338a98e589a28e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859011"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>Services de domaine Active Directory pour Skype Entreprise Server
 
Les services de domaine Active Directory fonctionnent en tant que service d’annuaire pour les réseaux Windows Server 2003, Windows Server 2008, Windows Server 2012 et Windows Server 2012 R2. Les services de domaine Active Directory servent également de base à la Skype Entreprise Server de sécurité de l’utilisateur. L’objectif de cette section est de décrire comment Skype Entreprise Server utilise les services de domaine Active Directory pour créer un environnement digne de confiance pour la messagerie instantanée, les conférences Web, les médias et la voix. Pour plus d’informations sur la préparation de votre environnement pour les services de domaine Active Directory, voir [Install Skype Entreprise Server](../../deploy/install/install.md) in the Deployment documentation. Pour des détails sur le rôle des services de domaine Active Directory dans les réseaux Windows Server, voir la documentation concernant votre version du système d’exploitation.
  
Skype Entreprise Server services de domaine Active Directory pour stocker :
  
- Paramètres globaux que tous les serveurs exécutant Skype Entreprise Server dans une forêt requièrent.
    
- Informations de service qui identifient les rôles de tous les serveurs exécutant des Skype Entreprise Server dans une forêt.
    
- Certains paramètres utilisateur.
    
## <a name="active-directory-infrastructure"></a>Infrastructure Active Directory

Les conditions d’infrastructure requises pour Active Directory incluent les suivantes :
  
- Configuration de système d’exploitation requise pour les contrôleurs de domaine
    
- Configuration requise de niveau fonctionnel du domaine ou de la forêt
    
- Configuration de catalogue global requise
    
Pour plus d’informations, voir [Environmental requirements for Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server requirements for Skype Entreprise Server [2019](../../../SfBServer2019/plan/system-requirements.md).
  
## <a name="universal-groups"></a>Groupes universels

Lors de la préparation de la forêt, Skype Entreprise Server crée différents groupes universels au sein des services de domaine Active Directory qui ont l’autorisation d’accéder aux paramètres et services globaux et de les gérer. Ces groupes universels incluent les suivants :
  
- **Groupes d’administration**. Ces groupes définissent les rôles d’administrateur fondamentaux d’Skype Entreprise Server réseau. Lors de la préparation de la forêt, ces groupes d’administrateurs sont ajoutés aux groupes Skype Entreprise Server’infrastructure.
    
- **Groupes de services** Ces groupes sont des comptes de service requis pour accéder aux différents services fournis par Skype Entreprise Server.
    
- **Groupes d’infrastructure.** Ces groupes permettent d’accéder à des zones spécifiques de l’infrastructure Skype Entreprise Server’infrastructure. Ils fonctionnent comme des composants de groupes d’administration et vous ne devez pas les modifier ou y ajouter directement des utilisateurs. Pendant la préparation de la forêt, des groupes de services et d’administration spécifiques sont ajoutés aux groupes d’infrastructure appropriés.
    
Pour plus d’informations sur les groupes universels spécifiques créés lors de la préparation d’AD pour Skype Entreprise Server, ainsi que sur les groupes de service et d’administration ajoutés aux groupes d’infrastructure, voir Modifications apportées par la préparation de la forêt dans [Skype Entreprise Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) dans la documentation de déploiement.
  
> [!NOTE]
> Skype Entreprise Server prend en charge les groupes universels dans le Windows Server 2012, ainsi que les systèmes d’exploitation Windows Server 2003 pour les contrôleurs de domaine. Les membres de groupes universels peuvent inclure d’autres groupes et comptes de n’importe quel domaine dans l’arborescence ou la forêt de domaines et peuvent se voir attribuer des autorisations dans n’importe quel domaine de l’arborescence ou de la forêt de domaines. La prise en charge des groupes universels, combinée à la délégation d’administrateur, simplifie la gestion d’Skype Entreprise Server déploiement. Par exemple, il n’est pas nécessaire d’ajouter un domaine à un autre pour permettre à un administrateur de gérer les deux. 
  
## <a name="role-based-access-control"></a>Contrôle d’accès basé sur un rôle

Outre la création de groupes de service et d’administration universels et l’ajout de groupes de service et d’administration aux groupes universels appropriés, la préparation de la forêt crée également des groupes Role-Based contrôle d’accès (RBAC). Pour plus d’informations sur les groupes RBAC spécifiques créés par la préparation de la forêt, voir Modifications apportées par la préparation de la forêt [Skype Entreprise Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) dans la documentation de déploiement. Pour plus d’informations sur les groupes RBAC, voir Contrôle d’accès basé sur un rôle [(RBAC) pour Skype Entreprise Server](role-based-access-control-rbac.md).
  
## <a name="access-control-entries-aces-and-inheritance"></a>Entrées de contrôle d’accès (ACE) et héritage

La préparation de la forêt crée des ace privées et publiques et ajoute des ace pour les groupes universels qu’elle crée. Il crée des ace privées spécifiques sur le conteneur de paramètres globaux utilisé par Skype Entreprise Server. Ce conteneur est utilisé uniquement par Skype Entreprise Server et se trouve soit dans le conteneur configuration, soit dans le conteneur système dans le domaine racine, selon l’emplacement où vous stockez les paramètres globaux.
  
L’étape de préparation du domaine ajoute les entrées de contrôle d’accès nécessaires aux groupes universels qui accordent les autorisations d’hébergement et de gestion des utilisateurs dans le domaine. La préparation du domaine créé des entrées de contrôle d’accès sur la racine du domaine et dans trois conteneurs intégrés : Utilisateurs, Ordinateurs et Contrôleurs de domaine.
  
Pour plus d’informations sur les ACE publiques créées et ajoutées par la préparation de la forêt et la préparation du domaine, voir Modifications apportées par la préparation de la forêt dans [Skype Entreprise Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) et Modifications apportées par la préparation du domaine dans [Skype Entreprise Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md) dans la documentation de déploiement.
  
Les organisations verrouillent souvent les services de domaine Active Directory (AD DS) dans le but de réduire les risques liés à la sécurité. Toutefois, un environnement Active Directory verrouillé peut limiter les autorisations dont Skype Entreprise Server a besoin. Cela peut inclure la suppression des entrées de contrôle d’accès des conteneurs et des unités d’organisation ou la désactivation de l’héritage des autorisations sur les objets Utilisateur, Contact, InetOrgPerson ou Ordinateur. Dans un environnement Active Directory verrouillé, les autorisations doivent être manuellement définies sur les conteneurs et les unités d’organisation qui les requièrent.
  
## <a name="server-information"></a>Informations relatives aux serveurs

Pendant l’activation, Skype Entreprise Server des informations sur le serveur aux trois emplacements suivants dans les services de domaine Active Directory :
  
- Point de connexion de service (SCP) sur chaque objet ordinateur Active Directory correspondant à un ordinateur physique sur lequel Skype Entreprise Server est installé.
    
- les objets serveur créés dans le conteneur de la classe **msRTCSIP-Pools** ;
    
- Serveurs de confiance spécifiés dans le Générateur de topologies.
    
## <a name="service-connection-points"></a>Points de connexion de service

Chaque objet Skype Entreprise Server dans les services de domaine Active Directory possède un point de service SCP appelé RTC Services, qui contient à son tour un certain nombre d’attributs qui identifient chaque ordinateur et spécifient les services qu’il fournit. Les attributs SCP les plus importants sont  *serviceDNSName*  , *serviceDNSNameType*  , *serviceClassname*  et *serviceBindingInformation*  . Les applications tierces de gestion des actifs peuvent obtenir des informations sur les serveurs d’un déploiement en recherchant ces attributs, ainsi que d’autres attributs de point de connexion de service.
  
## <a name="active-directory-server-objects"></a>Objets serveur Active Directory

Chaque Skype Entreprise Server de serveur a un objet Active Directory correspondant dont les attributs définissent les services fournis par ce rôle. En outre, lorsqu’un serveur Édition Standard est activé ou lorsqu’un pool Êdition Entreprise est créé, Skype Entreprise Server crée un objet **msRTCSIP-Pool** dans le conteneur **msRTCSIP-Pools.** La classe **msRTCSIP-Pool** définit le nom de domaine complet (FQDN) du pool, de même que l’association entre les composants frontal et principal du pool. (Un serveur Standard Edition Server est considéré comme un pool logique dont les composants frontal et principal sont colocalisés sur un même ordinateur.)
  
## <a name="trusted-servers"></a>Serveurs approuvés

Dans Skype Entreprise Server, les serveurs de confiance sont ceux spécifiés lorsque vous exécutez le Générateur de topologie et publiez votre topologie. La topologie publiée, avec toutes les informations sur les serveurs, est stockée dans le magasin central de gestion. Seuls les serveurs définis dans le magasin central de gestion sont approuvés. Dans Skype Entreprise Server, un serveur approuvé répond aux critères suivants :
  
- Le nom de domaine complet (FQDN) du serveur existe dans la topologie stockée dans le magasin central de gestion.
    
- Le serveur présente un certificat valide émanant d’une autorité de certification approuvée. Pour plus d’informations, voir [Environmental requirements for Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or System requirements for Skype Entreprise Server [2019](../../../SfBServer2019/plan/system-requirements.md).
    
Si un de ces critères n’est pas respecté, le serveur n’est pas approuvé et la connexion au serveur est refusée. Cette double exigence empêche une attaque possible, si peu probable, au cours de laquelle un serveur non malveillant tente de prendre le nom de groupe d’un serveur valide.
  
En outre, pour permettre aux déploiements Microsoft Office Communications Server 2007 R2 et Microsoft Office Communications Server 2007 de communiquer avec des serveurs Skype Entreprise Server, Skype Entreprise Server crée des conteneurs lors de la préparation de la forêt pour la mise en place de listes de serveurs de confiance pour les versions précédentes. Le tableau ci-dessous décrit les conteneurs créés dans un but de compatibilité avec les déploiements précédents.
  
**Listes de serveurs approuvés et leurs conteneurs Active Directory pour compatibilité avec les éditions précédentes**

|**Liste des serveurs approuvés**|**Conteneur Active Directory**|
|:-----|:-----|
|Serveurs Standard Edition Server et serveurs frontaux de pool d’entreprise  <br/> |Service RTC/Paramètres globaux  <br/> |
|Serveurs de conférence  <br/> |RTC Service/Serveurs MCU approuvés (Trusted MCUs)  <br/> |
|Serveurs de composants web  <br/> |Service RTC/Serveurs de composants web approuvés  <br/> |
|Serveurs de médiation et serveurs Communicator Web Access, serveur d’application, serveur d’inscriptions avec QoE, service de conférence A/V (également serveurs SIP tiers)  <br/> |Service RTC/Services approuvés  <br/> |
|Serveurs proxy  <br/> |Skype Entreprise Server ne prend pas en charge la compatibilité ascendante pour les serveurs proxy  <br/> |
   

## <a name="see-also"></a>Voir aussi

[Préparer Active Directory pour Skype Entreprise Server](../../deploy/install/prepare-active-directory.md)
