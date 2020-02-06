---
title: Services de domaine Active Directory pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Les fonctions des services de domaine Active Directory comme service d’annuaire pour Windows Server 2003, Windows Server 2008, Windows Server 2012 et les réseaux Windows Server 2012 R2. Les services de domaine Active Directory servent également de base pour la création de l’infrastructure de sécurité de Skype entreprise Server. L’objectif de cette section est de décrire la façon dont Skype entreprise Server utilise les services de domaine Active Directory (AD FS) pour créer un environnement digne de confiance pour la messagerie instantanée, les conférences Web, les médias et la voix. Pour plus d’informations sur la préparation de votre environnement pour les services de domaine Active Directory, voir Installer Skype entreprise Server dans la documentation de déploiement. Pour plus d’informations sur le rôle des services de domaine Active Directory dans les réseaux Windows Server, voir la documentation relative à la version du système d’exploitation que vous utilisez.
ms.openlocfilehash: ec3a09e2203b6f862d87403818b43ab6daae33ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815712"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>Services de domaine Active Directory pour Skype entreprise Server
 
Les fonctions des services de domaine Active Directory comme service d’annuaire pour Windows Server 2003, Windows Server 2008, Windows Server 2012 et les réseaux Windows Server 2012 R2. Les services de domaine Active Directory servent également de base pour la création de l’infrastructure de sécurité de Skype entreprise Server. L’objectif de cette section est de décrire la façon dont Skype entreprise Server utilise les services de domaine Active Directory (AD FS) pour créer un environnement digne de confiance pour la messagerie instantanée, les conférences Web, les médias et la voix. Pour plus d’informations sur la préparation de votre environnement pour les services de domaine Active Directory, voir [Installer Skype entreprise Server](../../deploy/install/install.md) dans la documentation de déploiement. Pour plus d’informations sur le rôle des services de domaine Active Directory dans les réseaux Windows Server, voir la documentation relative à la version du système d’exploitation que vous utilisez.
  
Skype entreprise Server utilise les services de domaine Active Directory pour stocker les éléments suivants :
  
- Paramètres globaux pour lesquels tous les serveurs exécutant Skype entreprise Server dans une forêt nécessitent.
    
- Des informations de service identifiant les rôles de tous les serveurs exécutant Skype entreprise Server dans une forêt.
    
- Certains paramètres utilisateur.
    
## <a name="active-directory-infrastructure"></a>Infrastructure Active Directory

Les exigences en matière d’infrastructure pour Active Directory sont les suivantes :
  
- Systèmes d’exploitation requis pour les contrôleurs de domaine
    
- Exigences de niveau fonctionnel de domaine et de forêt
    
- Exigences de domaine de catalogue global
    
Pour plus d’informations, reportez-vous à [configuration environnementale requise pour Skype entreprise server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [configuration serveur requise pour skype entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
## <a name="universal-groups"></a>Groupes universels

Lors de la préparation de la forêt, Skype entreprise Server crée divers groupes universelles dans les services de domaine Active Directory (AD FS) qui ont l’autorisation d’accéder à des services globaux et de les gérer. Ces groupes universels incluent :
  
- **Groupes administratifs**. Ces groupes définissent les rôles d’administrateur fondamentaux pour un réseau Skype entreprise Server. Lors de la préparation de la forêt, ces groupes d’administrateurs sont ajoutés aux groupes d’infrastructure de Skype entreprise Server.
    
- **Groupes de service**. Il s’agit des comptes de service nécessaires pour accéder aux différents services proposés par Skype entreprise Server.
    
- **Groupes d’infrastructure**. Ces groupes autorisent l’accès à des zones spécifiques de l’infrastructure du serveur Skype entreprise. Ils fonctionnent comme des composants de groupes administratifs et vous ne devez pas les modifier ni leur ajouter directement des utilisateurs. Lors de la préparation de la forêt, des groupes de service et d’administration spécifiques sont ajoutés aux groupes d’infrastructure appropriés.
    
Pour plus d’informations sur les groupes universels spécifiques créés lors de la préparation d’AD pour Skype entreprise Server, ainsi que les groupes de services et d’administration qui sont ajoutés aux groupes d’infrastructure, voir [modifications apportées par la préparation de la forêt dans Skype entreprise Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) dans la documentation de déploiement.
  
> [!NOTE]
> Skype entreprise Server prend en charge les groupes universels dans Windows Server 2012 et les systèmes d’exploitation Windows Server 2003 pour les contrôleurs de domaine. Les membres de groupes universels peuvent inclure d’autres groupes et comptes provenant de n’importe quel domaine de l’arbre ou de la forêt de domaines et peuvent se voir attribuer des autorisations dans n’importe quel domaine également. La prise en charge des groupes universels, combinée avec la délégation d’administrateur, simplifie la gestion d’un déploiement de Skype entreprise Server. Par exemple, il n’est pas nécessaire d’ajouter un domaine à un autre domaine pour permettre à un administrateur de les gérer tous les deux. 
  
## <a name="role-based-access-control"></a>Contrôle d’accès basé sur un rôle

En plus de créer des groupes de service et d’administration universels et d’ajouter des groupes de service et d’administration aux groupes universels appropriés, la préparation de forêt crée également des groupes de Contrôle d’accès basé sur un rôle (RBAC). Pour plus d’informations sur les groupes RBAC spécifiques créés par la préparation de la forêt, voir [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) dans la documentation de déploiement. Pour plus d’informations sur les groupes RBAC, voir [contrôle de contrôle d’accès basé sur les rôles (RBAC) pour Skype entreprise Server](role-based-access-control-rbac.md).
  
## <a name="access-control-entries-aces-and-inheritance"></a>Entrées de contrôle d’accès (ACE) et héritage

La préparation de la forêt crée des ACE privées et publiques et ajoute des ACE pour les groupes universels qu’elle crée. Il crée des entrées ACE privées spécifiques sur le conteneur de paramètres globaux utilisé par Skype entreprise Server. Ce conteneur est utilisé uniquement par Skype entreprise Server et réside dans le conteneur de configuration ou dans le conteneur système du domaine racine, en fonction de l’emplacement de stockage des paramètres globaux.
  
L’étape de préparation du domaine ajoute les entrées de contrôle d’accès (ACE) nécessaires aux groupes universels qui permettent d’héberger et de gérer les utilisateurs au sein du domaine. La préparation de domaine crée des ACE à la racine du domaine et dans trois conteneurs intégrés : Utilisateur, Ordinateurs et Contrôleurs de domaine.
  
Pour plus d’informations sur les ACE publiques créées et ajoutées par la préparation de la forêt et la préparation du domaine, voir [modifications apportées par la préparation de la forêt dans Skype entreprise Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) et [modifications apportées par la préparation du domaine dans Skype entreprise Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md) dans la documentation de déploiement.
  
Les organisations verrouillent souvent les services de domaine Active Directory (AD DS) pour réduire les risques liés à la sécurité. Toutefois, un environnement Active Directory verrouillé peut limiter les autorisations requises par Skype entreprise Server. Ceci peut inclure la suppression des ACE des conteneurs et des unités d’organisation (OU) et la désactivation de l’héritage des autorisations sur les objets Utilisateur, Contact, InetOrgPerson ou Ordinateur. Dans un environnement Active Directory verrouillé, les autorisations doivent être définies manuellement sur les conteneurs et les unités d’organisation qui en ont besoin.
  
## <a name="server-information"></a>Informations du serveur

Au cours de l’activation, Skype entreprise Server publie les informations du serveur aux trois emplacements suivants dans les services de domaine Active Directory (AD FS) :
  
- Un point de connexion de service (SCP) sur chaque objet d’ordinateur Active Directory correspondant à un ordinateur physique sur lequel est installé Skype entreprise Server.
    
- Les objets Serveur créés dans le conteneur de la classe **msRTCSIP-Pools**.
    
- Serveurs de confiance spécifiés dans le générateur de topologie.
    
## <a name="service-connection-points"></a>Points de connexion de service

Chaque objet Skype entreprise Server dans les services de domaine Active Directory (AD FS) possède un SCP appelé services RTC, qui à son tour contient un certain nombre d’attributs identifiant chaque ordinateur et spécifiant les services qu’il fournit. Entre les attributs SCP plus importants sont *servicednsname* , *serviceDNSNameType* , *serviceClassName* et *serviceBindingInformation* . Les applications de gestion des actifs tiers peuvent récupérer les informations du serveur sur un déploiement en émettant des requêtes concernant ces données et d’autres attributs de points de connexion de service.
  
## <a name="active-directory-server-objects"></a>Objets serveur Active Directory

Chaque rôle du serveur Skype entreprise Server possède un objet Active Directory correspondant dont les attributs définissent les services fournis par ce rôle. Par ailleurs, lorsqu’un serveur Standard Edition Server est activé ou qu’un pool Enterprise Edition est créé, Skype entreprise Server crée un nouvel objet de **pool msRTCSIP** dans le conteneur **msRTCSIP-pools** . La classe **msRTCSIP-Pool ** spécifie le nom de domaine complet (FQDN) du pool, ainsi que l’association entre les composants frontaux et principaux du pool. (Un serveur Standard Edition Server est considéré comme une réserve logique dont les extrémités avant et arrière sont colocalisées sur un seul ordinateur.)
  
## <a name="trusted-servers"></a>Serveurs approuvés

Dans Skype entreprise Server, les serveurs de confiance sont ceux spécifiés lors de l’exécution du générateur de topologie et de la publication de votre topologie. La topologie publiée, y compris toutes les informations du serveur, est enregistrée dans le magasin central de gestion. Seuls les serveurs définis dans le magasin central de gestion sont approuvés. Dans Skype entreprise Server, un serveur approuvé est l’un des critères suivants :
  
- Le nom de domaine complet (FQDN) du serveur se trouve dans la topologie enregistrée dans le magasin central de gestion.
    
- Le serveur présente un certificat valide d’une autorité de certification approuvée. Pour plus d’informations, reportez-vous à [configuration environnementale requise pour Skype entreprise server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [Configuration système requise pour skype entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
Si l’un de ces critères est manquant, le serveur n’est pas approuvé et la connexion avec celui-ci est refusée. Cette condition préalable évite qu’un serveur malveillant tente de prendre le contrôle de FQDN d’un serveur valide.
  
Par ailleurs, pour permettre aux déploiements de Microsoft Office Communications Server 2007 R2 et de Microsoft Office Communications Server 2007 de communiquer avec des serveurs Skype entreprise Server, Skype entreprise Server crée des conteneurs lors de la préparation de la forêt pour les listes de serveurs approuvés pour les versions précédentes. Le tableau suivant décrit les conteneurs créés pour permettre la compatibilité avec les déploiements précédents.
  
**Listes de serveurs approuvés et leurs conteneurs Active Directory pour la compatibilité avec les versions précédentes**

|**Liste des serveurs approuvés**|**Conteneur Active Directory**|
|:-----|:-----|
|Serveurs Standard Edition et serveurs frontaux du pool d’entreprise  <br/> |RTC Service/Paramètres globaux  <br/> |
|Serveurs de conférence  <br/> |RTC Service/MCU approuvés  <br/> |
|Serveurs de composants Web  <br/> |RTC Service/TrustedWebComponentsServers  <br/> |
|Serveurs de médiation et serveurs Communicator Web Access, serveur d’application, serveur d’inscriptions avec QoE, service de conférence A/V (également serveurs SIP tiers)  <br/> |RTC Service/Services approuvés  <br/> |
|Serveurs proxy  <br/> |Skype entreprise Server ne prend pas en charge la compatibilité descendante pour les serveurs proxy  <br/> |
   

## <a name="see-also"></a>Voir aussi

[Préparer Active Directory pour Skype entreprise Server](../../deploy/install/prepare-active-directory.md)
