---
title: Modifications apportées par la préparation de la forêt dans Skype pour Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: Cette section décrit les paramètres globaux et les objets et les groupes universels de service et d’administration qui sont créés par l’étape de préparation de forêt.
ms.openlocfilehash: 3e37948cae33412ac028d5190c780d6bee5aeeb2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Modifications apportées par la préparation de la forêt dans Skype pour Business Server
 
Cette section décrit les paramètres globaux et les objets et les groupes universels de service et d’administration qui sont créés par l’étape de préparation de forêt.
  
## <a name="active-directory-global-settings-and-objects"></a>Les objets et les paramètres globaux d’active Directory

Si vous stockez des paramètres globaux dans le conteneur Configuration (comme c’est le cas pour tous les nouveaux Skype pour les déploiements de serveur d’entreprise), préparation de la forêt utilise le conteneur de Services existant et ajoute un objet de **Service RTC** sous la Configuration\Services objet. Sous l’objet de Service RTC, préparation de la forêt ajoute un objet de **Paramètres globaux** de type msRTCSIP-GlobalContainer. L’objet paramètres globaux conserve tous les paramètres qui s’appliquent à la Skype pour le déploiement du serveur de l’entreprise. Si vous stockez des paramètres globaux dans le conteneur système, préparation de la forêt utilise un conteneur de Microsoft sous le conteneur système de domaine racine et un objet de Service RTC sous l’objet System\Microsoft.
  
Préparation de la forêt ajoute également un nouvel objet **MsRTCSIP-domaine** pour le domaine racine dans lequel la procédure est exécutée.
  
## <a name="active-directory-universal-service-and-administration-groups"></a>Service universel de Active Directory et les groupes d’Administration

Préparation de la forêt crée des groupes universels en fonction du domaine que vous spécifiez et ajoute les entrées de contrôle d’accès (ACE) pour ces groupes. Cette étape crée les groupes universels dans les conteneurs d’utilisateurs du domaine que vous spécifiez. 
  
Les groupes universels permettent aux administrateurs d’accéder et de gérer les paramètres globaux et les services. Préparation de la forêt ajoute les types suivants de groupes universels :
  
- **Groupes d’administration** Ces groupes définissent les rôles d’administrateur pour un Skype pour réseau Business Server.
    
- **Groupes d’infrastructure** Ces groupes des droits d’accéder à des zones spécifiques de la Skype pour infrastructure de serveur d’entreprise. Ils fonctionnent en tant que composants des groupes d’administration. Vous ne devez pas modifier ces groupes ou ajouter des utilisateurs directement.
    
- **Groupes de service** Ces groupes sont des comptes de service qui sont nécessaires pour accéder aux différents Skype pour les services de serveur d’entreprise.
    
Le tableau suivant décrit les groupes d’administration.
  
**Groupes d’administration créés au cours de la préparation de la forêt**

|**Groupe d’administration**|**Description**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |Permet aux membres de gérer le serveur et les paramètres du pool, y compris tous les rôles serveur, les paramètres globaux et les utilisateurs.  <br/> |
|RTCUniversalUserAdmins  <br/> |Permet aux membres de gérer les paramètres utilisateur et de déplacer des utilisateurs d’un serveur ou un pool à un autre.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |Permet aux membres de lire les paramètres du serveur, pool et utilisateur.  <br/> |
   
Le tableau suivant décrit les groupes de l’infrastructure.
  
**Groupes d’infrastructure créés au cours de la préparation de la forêt**

|**Groupe d’infrastructure**|**Description**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Accorde l’accès en écriture aux objets de paramètre global pour Skype pour Business Server.  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Accorde l’accès en lecture seule pour les objets de paramètre global pour Skype pour Business Server.  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Accorde l’accès en lecture seule à Skype pour les paramètres d’utilisateur de serveur de l’entreprise.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Accorde l’accès en lecture seule à Skype pour les paramètres de serveur de l’entreprise. Ce groupe n’a pas d’accès aux paramètres au niveau du pool, uniquement pour les paramètres spécifiques à un serveur individuel.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Autorise l’accès en lecture seule Skype pour la configuration du serveur de l’entreprise et sont placés dans le groupe des administrateurs locaux des appareils survivable branch lors de l’installation.  <br/> |
   
Le tableau suivant décrit les groupes de services.
  
**Groupes de service créés au cours de la préparation de la forêt**

|**Groupe de services**|**Description**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Inclut les comptes de service utilisés pour exécuter le serveur frontal et les serveurs Standard Edition Server. Ce groupe permet de serveurs d’accéder en lecture/écriture à Skype pour les paramètres globaux du serveur d’entreprise et des objets utilisateur Active Directory.  <br/> |
|RTCComponentUniversalServices  <br/> |Inclut les comptes de service utilisés pour exécuter les A / V Conferencing serveurs, Services Web, serveur de médiation, d’archivage et Monitoring Server.  <br/> |
|RTCProxyUniversalServices  <br/> |Inclut les comptes de service utilisés pour exécuter Skype serveur Edge des serveurs d’entreprise.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Comprend des serveurs pouvant participer dans Skype pour la réplication de magasin de gestion centrale de serveur.  <br/> |
|RTCSBAUniversalServices  <br/> |Autorise l’accès en lecture seule Skype pour les paramètres de serveur de l’entreprise, mais permet la configuration de l’installation d’un serveur de succursale survivable et un déploiement survivable branch.  <br/> |
   
Préparation de la forêt puis ajoute les groupes d’administration et de service aux groupes appropriés d’infrastructure, comme suit :
  
- RTCUniversalServerAdmins est ajouté à RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.
    
- RTCUniversalUserAdmins est ajouté en tant que membre de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.
    
- RTCHSUniversalServices, RTCComponentUniversalServices et RTCUniversalReadOnlyAdmins sont ajoutées en tant que membres de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.
    
Préparation de la forêt crée également les groupes de contrôle (RBAC) accès basé sur les rôles suivants :
  
- CSAdministrator
    
- CSArchivingAdministrator
    
- CSHelpDesk
    
- CSLocationAdministrator
    
- CSResponseGroupAdministrator
    
- CSServerAdministrator
    
- CSUserAdministrator
    
- CSViewOnlyAdministrator
    
- CSVoiceAdministrator
    
- CsPersistentChatAdministator
    
- CsResponseGroupManager
    
Pour plus d’informations sur les tâches autorisées pour chaque et les rôles RBAC, consultez [contrôle d’accès basée sur les rôles](http://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) dans la documentation de planification.
  
Préparation de la forêt crée des ACE publics et privés. Il crée des ACE privé sur le conteneur Paramètres globaux utilisé par Skype pour Business Server. Ce conteneur est utilisé uniquement par Skype pour Business Server et se trouve dans le conteneur Configuration ou le conteneur système dans le domaine racine, selon où vous stockez les paramètres globaux. Les ACE publics créés en préparation de la forêt sont répertoriés dans le tableau suivant.
  
**ACE publics créés en préparation de la forêt**

|**ACE**|**RTCUniversalGlobalReadOnlyGroup**|
|:-----|:-----|
|Lire le domaine racine de conteneur système (non hérité)**\*** <br/> |X  <br/> |
|Conteneur de DisplaySpecifiers de la Configuration de la lecture (non hérité)  <br/> |X  <br/> |
   
> [!NOTE]
> **\***Les entrées qui ne sont pas héritées n’accordent pas d’accès aux objets enfants dans ces conteneurs. Les ACE sont héritées accordent l’accès aux objets enfants dans ces conteneurs. 
  
Sur le conteneur de Configuration, dans le contexte d’appellation de Configuration, préparation de la forêt exécute les tâches suivantes :
  
- Ajoute une entrée **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** pour la page de **propriété RTC** sous l’adminContextMenu et d’adminPropertyPages des attributs du langage affichent spécificateur pour les utilisateurs, les contacts et InetOrgPersons (par exemple, CN = user-Display, CN = 409, CN = DisplaySpecifiers).
    
- Ajoute un objet **RTCPropertySet** de type **controlAccessRight** sous l' **Étendue des droits** qui s’applique aux classes utilisateur et Contact.
    
- Ajoute un objet **RTCUserSearchPropertySet** de type **controlAccessRight** dans l' **Étendue des droits** qui s’applique aux classes utilisateur, Contact, unité d’organisation et DomainDNS.
    
- Ajoute **msRTCSIP-PrimaryUserAddress** sous l’attribut **extraColumns** de chaque spécificateur d’affichage de l’unité d’organisation (UO) langue (par exemple, CN = organizationalUnit-Display, CN = 409, CN = DisplaySpecifiers) et copie les valeurs de la attribut **extraColumns** de l’affichage par défaut (par exemple, CN = l’affichage par défaut, CN = 409, CN = DisplaySpecifiers).
    
- Ajoute **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**et **msRTCSIP-UserEnabled** filtrage d’attributs sous l’attribut **attributeDisplayNames** de chaque langue d’affichage spécificateur pour les utilisateurs, les Contacts, et les objets InetOrgPerson (par exemple, en anglais : CN = user-Display, CN = 409, CN = DisplaySpecifiers).
    

