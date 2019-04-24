---
title: Modifications apportées par la préparation de la forêt dans Skype pour Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: Cette section décrit les paramètres globaux et les objets et les groupes universels de service et d’administration qui sont créés à l’étape de préparation de la forêt.
ms.openlocfilehash: 27b8e183f4c76c7c5db71af1422ba9185206632a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213423"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Modifications apportées par la préparation de la forêt dans Skype pour Business Server

Cette section décrit les paramètres globaux et les objets et les groupes universels de service et d’administration qui sont créés à l’étape de préparation de la forêt.

## <a name="active-directory-global-settings-and-objects"></a>Objets et paramètres globaux active Directory

Si vous stockez les paramètres globaux dans le conteneur de Configuration (comme c’est le cas pour toutes les nouvelles Skype pour les déploiements de serveur d’entreprise), la préparation de la forêt utilise le conteneur Services existant et ajoute un objet **Service RTC** sous le Configuration\Services objet. Sous l’objet Service RTC, la préparation de la forêt ajoute un objet **Global Settings** de type msRTCSIP-GlobalContainer. L’objet global settings conserve tous les paramètres qui s’appliquent à la Skype pour le déploiement de serveur d’entreprise. Si vous stockez les paramètres globaux dans le conteneur système, préparation de la forêt utilise un conteneur Microsoft sous le conteneur système du domaine racine et un objet Service RTC sous l’objet System\Microsoft.

Préparation de la forêt ajoute également un nouvel objet **msRTCSIP-Domain** pour le domaine racine dans lequel la procédure est exécutée.

## <a name="active-directory-universal-service-and-administration-groups"></a>Services universels Active Directory et les groupes d’Administration

Préparation de la forêt crée des groupes universels basés sur le domaine que vous spécifiez et ajoute les entrées de contrôle d’accès (ACE) pour ces groupes. Cette étape crée les groupes universels dans les conteneurs utilisateurs du domaine que vous spécifiez.

Groupes universels permettent aux administrateurs d’accéder et de gérer les services et les paramètres globaux. Préparation de la forêt ajoute les types de groupes universels suivants :

- **Groupes d’administration** Ces groupes définissent les rôles d’administrateur pour un Skype pour réseau Business Server.

- **Groupes d’infrastructure** Ces groupes accordent des autorisations pour accéder à des zones spécifiques de le Skype pour l’infrastructure de serveur d’entreprise. Ils fonctionnent comme des composants de groupes d’administration. Vous ne devez pas modifier ces groupes ou ajouter des utilisateurs directement.

- **Groupes de services** Ces groupes sont des comptes de service qui sont nécessaires pour accéder à diverses Skype pour les services Business Server.

Le tableau suivant décrit les groupes d’administration.

**Groupes d’administration créés pendant la préparation de la forêt**

|**Groupe d’administration**|**Description**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |Permet à ses membres gérer les utilisateurs et les paramètres du pool, y compris tous les rôles serveur, paramètres globaux et server.  <br/> |
|RTCUniversalUserAdmins  <br/> |Permet à ses membres gérer les paramètres utilisateur et de déplacer les utilisateurs d’un serveur ou pool à un autre.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |Permet à ses membres pour la lecture des paramètres de serveur, pool et utilisateur.  <br/> |

Le tableau suivant décrit les groupes d’infrastructure.

**Groupes d’infrastructure créés pendant la préparation de la forêt**

|**Groupe d’infrastructure**|**Description**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Accorde l’accès en écriture aux objets de paramètres globaux pour Skype pour Business Server.  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Permet d’accéder en lecture seule aux objets de paramètres globaux pour Skype pour Business Server.  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Permet d’accéder en lecture seule aux Skype pour les paramètres utilisateur Business Server.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Permet d’accéder en lecture seule aux Skype pour les paramètres du serveur d’entreprise. Ce groupe n’a pas accès aux paramètres au niveau du pool, uniquement pour les paramètres spécifiques à un serveur individuel.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Accorde l’accès en lecture seule à Skype pour la configuration du serveur d’entreprise et sont placés dans le groupe d’administrateurs locaux du survivable branch appliance pendant l’installation.  <br/> |

Le tableau suivant décrit les groupes de services.

**Groupes de services créés pendant la préparation de la forêt**

|**Groupe de service**|**Description**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Inclut les comptes de service utilisés pour exécuter le serveur frontal et les serveurs Standard Edition Server. Ce groupe autorise serveurs l’accès en lecture/écriture à Skype pour les paramètres globaux du serveur d’entreprise et les objets utilisateur Active Directory.  <br/> |
|RTCComponentUniversalServices  <br/> |Inclut les comptes de service utilisés pour exécuter A / V Conferencing Servers, Services Web, serveur de médiation, le serveur d’archivage et le serveur de surveillance.  <br/> |
|RTCProxyUniversalServices  <br/> |Inclut les comptes de service utilisés pour exécuter Skype pour les serveurs de périphérie Business Server.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Inclut les serveurs qui peuvent participer à Skype pour la réplication de magasin Central de gestion de Business Server.  <br/> |
|RTCSBAUniversalServices  <br/> |Accorde l’accès en lecture seule à Skype pour les paramètres du serveur d’entreprise, mais autorise la configuration de l’installation d’un serveur survivable branch server déploiement et survivable branch appliance.  <br/> |

Préparation de la forêt puis ajoute les groupes de services et d’administration aux groupes d’infrastructure appropriés, comme suit :

- RTCUniversalServerAdmins est ajouté à RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.

- RTCUniversalUserAdmins est ajouté en tant que membre de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.

- RTCHSUniversalServices, RTCComponentUniversalServices et RTCUniversalReadOnlyAdmins sont ajoutés en tant que membres de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.

Préparation de la forêt crée également des groupes l’accès basé sur un rôle RBAC (contrôle) suivants :

- CSAdministrator

- CSArchivingAdministrator

- Est CSHelpDesk

- CSLocationAdministrator

- CSResponseGroupAdministrator

- CSServerAdministrator

- CSUserAdministrator

- CSViewOnlyAdministrator

- CSVoiceAdministrator

- CsPersistentChatAdministator

- CsResponseGroupManager

Pour plus d’informations sur les rôles RBAC et les tâches autorisées pour chacun, voir [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) dans la documentation de planification.

Préparation de la forêt crée ACE privée et publique. Il crée ACE privé sur le conteneur des paramètres globaux utilisé par Skype pour Business Server. Ce conteneur est utilisé uniquement par Skype pour Business Server et se trouve dans le conteneur de Configuration ou dans le conteneur système dans le domaine racine, en fonction de dans lequel vous stockez les paramètres globaux. ACE publics créés par la préparation de la forêt sont répertoriés dans le tableau suivant.

**ACE public créé par la préparation de la forêt**


| **ACE**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| Lire le conteneur système (non héritée) du domaine racine**\\**\* <br/>        | X  <br/>                            |
| Conteneur DisplaySpecifiers de la Configuration de lecture (non hérité)  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>* Les entrées ne sont pas héritées n’accordent pas d’accès à des objets enfants dans ces conteneurs. ACE héritées accorder l’accès à des objets enfants dans ces conteneurs.

Dans le conteneur de Configuration, sous le contexte d’appellation de Configuration, la préparation de la forêt exécute les tâches suivantes :

- Ajoute une entrée **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** pour la page de **la propriété RTC** sous les attributs et adminPropertyPages de la langue d’affichage spécificateur pour les utilisateurs, contacts et InetOrgPersons (par exemple, CN = user-Display, CN = 409, CN = DisplaySpecifiers).

- Ajoute un objet **RTCPropertySet** de type **controlAccessRight** sous **Extended-Rights** qui s’applique aux classes utilisateur et Contact.

- Ajoute un objet **RTCUserSearchPropertySet** de type **controlAccessRight** sous **Extended-Rights** qui s’applique aux classes utilisateur, Contact, OU et DomainDNS.

- Ajoute **msRTCSIP-PrimaryUserAddress** sous l’attribut **extraColumns** de chaque spécificateur d’affichage de l’unité d’organisation (UO) (par exemple, CN = organizationalUnit-Display, CN = 409, CN = DisplaySpecifiers) et copie des valeurs de la attribut **extraColumns** de l’affichage par défaut (par exemple, CN = default-Display, CN = 409, CN = DisplaySpecifiers).

- Ajoute **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**et **msRTCSIP-UserEnabled** en filtrant les attributs sous l’attribut **attributeDisplayNames** de chaque langue spécificateur pour les utilisateurs, Contacts, d’affichage et les objets InetOrgPerson (par exemple, en anglais : CN = user-Display, CN = 409, CN = DisplaySpecifiers).


