---
title: Modifications apportées par la préparation de la forêt dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: Cette section décrit les paramètres globaux, les objets et les groupes de services universels et d’administration créés pendant la préparation de la forêt.
ms.openlocfilehash: c21e6dfac6cd3b6a9bb3c0b6b040138e6d8f8a52
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613994"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Modifications apportées par la préparation de la forêt dans Skype Entreprise Server

Cette section décrit les paramètres globaux, les objets et les groupes de services universels et d’administration créés pendant la préparation de la forêt.

## <a name="active-directory-global-settings-and-objects"></a>Paramètres globaux et objets Active Directory

Si vous stockez les paramètres globaux dans le conteneur de configuration (comme c’est le cas pour tous les nouveaux déploiements Skype Entreprise Server), la préparation de la forêt utilise le conteneur services existant et ajoute un objet **RTC Service** sous l’objet Configuration\Services. Sous l’objet RTC Service, la préparation de la forêt ajoute un objet **Paramètres globaux** de type msRTCSIP-GlobalContainer. L’objet de paramètres globaux contient tous les paramètres qui s’appliquent au Skype Entreprise Server déploiement. Si vous choisissez de stocker les paramètres globaux dans le conteneur système, la préparation de la forêt ajoute un conteneur Microsoft sous le conteneur système du domaine racine et un nouvel objet RTC Service sous l’objet System\Microsoft.

La préparation de la forêt ajoute également un nouvel objet **msRTCSIP-Domain** pour le domaine racine dans lequel la procédure est exécutée.

## <a name="active-directory-universal-service-and-administration-groups"></a>Groupes de services universels et d’administration Active Directory

La préparation de la forêt crée des groupes universels basés sur le domaine que vous spécifiez et ajoute des entrées de contrôle d’accès (ACE) pour ces groupes. Cette étape crée les groupes universels dans les conteneurs d’utilisateurs du domaine que vous spécifiez.

Les groupes universels permettent aux administrateurs d’accéder aux services et aux paramètres globaux et de les gérer. La préparation de la forêt ajoute les types de groupes universels suivants :

- **Groupes d’administration** Ces groupes définissent les rôles d’administrateur pour Skype Entreprise Server réseau.

- **Groupes d’infrastructure** Ces groupes permettent d’accéder à des zones spécifiques de l’infrastructure Skype Entreprise Server’infrastructure. Ils fonctionnent comme composants des groupes d’administration. Vous ne devez pas modifier ces groupes ni leur ajouter directement des utilisateurs.

- **Groupes de services** Ces groupes sont des comptes de service requis pour accéder à différents services Skype Entreprise Server services.

Le tableau suivant présente les groupes d’administration.

**Groupes d’administration créés lors de la préparation de la forêt**

|**Groupe d’administration**|**Description**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |Permet à ses membres de gérer les paramètres de serveurs et de pools, notamment tous les rôles de serveurs, les paramètres globaux et les utilisateurs.  <br/> |
|RTCUniversalUserAdmins  <br/> |Permet à ses membres de gérer les paramètres utilisateur et de transférer des utilisateurs d’un serveur ou pool à un autre.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |Permet à ses membres d’accéder en lecture aux paramètres de serveur, de pool et d’utilisateur.  <br/> |

Le tableau suivant présente les groupes d’infrastructure.

**Groupes d’infrastructure créés lors de la préparation de la forêt**

|**Groupe d’infrastructure**|**Description**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Accorde l’accès en écriture aux objets de paramètre global pour Skype Entreprise Server.  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Accorde un accès en lecture seule aux objets de paramètre global pour Skype Entreprise Server.  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Accorde un accès en lecture seule Skype Entreprise Server paramètres utilisateur.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Accorde un accès en lecture seule Skype Entreprise Server paramètres. Ce groupe n’a pas accès aux paramètres de niveau pool, mais uniquement aux paramètres spécifiques à un serveur donné.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Accorde un accès en lecture seule à Skype Entreprise Server configuration et est placé dans le groupe Administrateurs locaux des survivable Branch Appliances lors de l’installation.  <br/> |

Le tableau suivant présente les groupes de services.

**Groupes de services créés lors de la préparation de la forêt**

|**Groupe de services**|**Description**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Inclut les comptes de service utilisés pour exécuter le serveur frontal et Édition Standard serveurs. Ce groupe permet aux serveurs d’accéder en lecture/écriture Skype Entreprise Server paramètres globaux et aux objets utilisateur Active Directory.  <br/> |
|RTCComponentUniversalServices  <br/> |Inclut les comptes de service utilisés pour exécuter les serveurs de conférence A/V, les services Web, le serveur de médiation, le serveur d’archivage et le serveur de surveillance.  <br/> |
|RTCProxyUniversalServices  <br/> |Inclut les comptes de service utilisés pour exécuter Skype Entreprise Server serveurs Edge.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Inclut les serveurs qui peuvent participer à la Skype Entreprise Server du magasin central de gestion.  <br/> |
|RTCSBAUniversalServices  <br/> |Accorde un accès en lecture seule aux paramètres de Skype Entreprise Server, mais permet la configuration de l’installation d’un serveur survivable Branch Server et d’un déploiement survivable Branch Appliance.  <br/> |

La préparation de la forêt ajoute ensuite des groupes de services et d’administration aux groupes d’infrastructure appropriés, comme suit :

- RTCUniversalServerAdmins est ajouté à RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.

- RTCUniversalUserAdmins est ajouté en tant que membre de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.

- RTCHSUniversalServices, RTCComponentUniversalServices et RTCUniversalReadOnlyAdmins sont ajoutés en tant que membres de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.

La préparation de forêt crée également les groupes de rôles RBAC (Contrôle d’accès basé sur un rôle) suivants :

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

Pour plus d’informations sur les rôles RBAC et les tâches que chaque rôle est autorisé à effectuer, voir [Role-Based Access Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) dans la documentation de planification.

La préparation de la forêt crée des ace privées et publiques. Il crée des ace privées sur le conteneur de paramètres globaux utilisé par Skype Entreprise Server. Ce conteneur est utilisé uniquement par Skype Entreprise Server et se trouve soit dans le conteneur Configuration, soit dans le conteneur Système dans le domaine racine, selon l’emplacement où vous stockez les paramètres globaux. Les ace publiques créées par la préparation de la forêt sont répertoriées dans le tableau suivant.

**Entrées de contrôle d’accès publiques créées par la préparation de la forêt**


| **moteur ACE**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| Lire le conteneur système du domaine racine (non hérité) **\\**\* <br/>        | X  <br/>                            |
| Lire le conteneur DisplaySpecifiers de configuration (non hérité)  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>*Les ace qui ne sont pas héritées n’accordent pas l’accès aux objets enfants sous ces conteneurs. *Les entrées de contrôle d’accès qui sont héritées permettent d’accéder aux objets enfants qui figurent dans ces conteneurs.

La préparation de la forêt exécute les tâches suivantes sur le conteneur de configuration, sous le contexte d’affectation de noms de la configuration :

- Ajoute une entrée **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** pour la page **RTC property** sous les attributs adminContextMenu et adminPropertyPages du spécificateur d’affichage de la langue pour les objets User, Contact et InetOrgPersons (par exemple, CN=user-Display,CN=409,CN=DisplaySpecifiers).

- Ajoute un objet **RTCPropertySet** de type **controlAccessRight** sous **Extended-Rights** qui s’applique aux classes User et Contact.

- Ajoute un objet **RTCUserSearchPropertySet** de type **controlAccessRight** sous **Extended-Rights** qui s’applique aux classes User, Contact, OU et DomainDNS.

- Ajoute **msRTCSIP-PrimaryUserAddress** sous l’attribut **extraColumns** de chaque spécificateur d’affichage des unités d’organisation de la langue (CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers, par exemple) et copie des valeurs de l’attribut **extraColumns** de l’affichage par défaut (CN=default-Display, CN=409,CN=DisplaySpecifiers, par exemple).

- Ajoute les attributs de filtrage **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** et **msRTCSIP-UserEnabled** sous l’attribut **attributeDisplayNames** de chaque spécificateur d’affichage de la langue pour les objets User, Contact et InetOrgPerson (par exemple, en anglais : CN=user-Display,CN=409,CN=DisplaySpecifiers).