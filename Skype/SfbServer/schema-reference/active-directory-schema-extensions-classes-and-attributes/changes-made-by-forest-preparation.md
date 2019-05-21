---
title: Modifications apportées par la préparation de la forêt dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: Cette section décrit les paramètres globaux et les objets, ainsi que les groupes de services et d’administration universels créés par l’étape de préparation de la forêt.
ms.openlocfilehash: ece4a9bd1db5f43b52a96265dee41ee3a0a30b22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296699"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Modifications apportées par la préparation de la forêt dans Skype entreprise Server

Cette section décrit les paramètres globaux et les objets, ainsi que les groupes de services et d’administration universels créés par l’étape de préparation de la forêt.

## <a name="active-directory-global-settings-and-objects"></a>Paramètres globaux et objets Active Directory

Si vous stockez des paramètres globaux dans le conteneur de configuration (comme dans le cas d’un nouveau déploiement de Skype entreprise Server), la préparation de la forêt utilise le conteneur services existants et ajoute un objet **Service RTC** sous le Configuration\Services objet. Sous l’objet RTC service, la préparation de la forêt ajoute un objet de **paramètres globaux** de type MsRTCSIP-GlobalContainer. L’objet paramètres globaux contient tous les paramètres qui s’appliquent au déploiement de Skype entreprise Server. Si vous stockez des paramètres globaux dans le conteneur système, la préparation de la forêt utilise un conteneur Microsoft sous le conteneur système du domaine racine et un objet service RTC sous l’objet System\Microsoft.

La préparation de la forêt ajoute également un nouvel objet **msRTCSIP-Domain** pour le domaine racine dans lequel la procédure est exécutée.

## <a name="active-directory-universal-service-and-administration-groups"></a>Service universel et groupes d’administration Active Directory

La préparation de la forêt crée des groupes universels en fonction du domaine que vous spécifiez et ajoute des entrées de contrôle d’accès (ACE) pour ces groupes. Cette étape permet de créer des groupes universels dans les conteneurs d’utilisateurs du domaine que vous spécifiez.

Les groupes universels permettent aux administrateurs d’accéder aux paramètres globaux et de gérer ces derniers. La préparation de la forêt ajoute les types suivants de groupes universels:

- **Groupes d’administration** Ces groupes définissent des rôles d’administrateur pour un réseau Skype entreprise Server.

- **Groupes d’infrastructure** Ces groupes autorisent l’accès à des zones spécifiques de l’infrastructure du serveur Skype entreprise. Ils fonctionnent en tant que composants de groupes d’administration. Vous ne devez pas modifier ces groupes ni y ajouter des utilisateurs directement.

- **Groupes de services** Il s’agit des comptes de service nécessaires pour accéder à différents services Skype entreprise Server.

Le tableau suivant décrit les groupes d’administration.

**Groupes d’administration créés lors de la préparation de la forêt**

|**Groupe d’administration**|**Description**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |Permet aux membres de gérer les paramètres du serveur et du pool, y compris tous les rôles de serveur, les paramètres globaux et les utilisateurs.  <br/> |
|RTCUniversalUserAdmins  <br/> |Permet aux membres de gérer les paramètres utilisateur et de déplacer les utilisateurs d’un serveur ou d’un pool vers un autre.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |Permet aux membres de lire les paramètres du serveur, du pool et de l’utilisateur.  <br/> |

Le tableau suivant décrit les groupes d’infrastructure.

**Groupes d’infrastructure créés lors de la préparation de la forêt**

|**Groupe d’infrastructure**|**Description**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Octroie l’accès en écriture aux objets de paramètres globaux pour Skype entreprise Server.  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Octroie un accès en lecture seule aux objets de paramètres globaux pour Skype entreprise Server.  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Octroie un accès en lecture seule aux paramètres utilisateur de Skype entreprise Server.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Octroie un accès en lecture seule aux paramètres de Skype entreprise Server. Ce groupe n’a pas accès aux paramètres de niveau de regroupement, uniquement aux paramètres spécifiques à un serveur individuel.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Octroie un accès en lecture seule à la configuration de Skype entreprise Server et est placé dans le groupe administrateurs locaux des appareils de branchement survivables lors de l’installation.  <br/> |

Le tableau suivant décrit les groupes de services.

**Groupes de services créés lors de la préparation de la forêt**

|**Groupe de services**|**Description**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Inclut les comptes de service utilisés pour exécuter les serveurs front-end Server et Standard Edition. Ce groupe permet à un serveur en lecture/écriture d’accéder aux paramètres globaux de Skype entreprise Server et aux objets utilisateurs Active Directory.  <br/> |
|RTCComponentUniversalServices  <br/> |Inclut les comptes de service utilisés pour exécuter des serveurs de conférence A/V, des services Web, un serveur de médiation, un serveur d’archivage et un serveur de surveillance.  <br/> |
|RTCProxyUniversalServices  <br/> |Inclut les comptes de service utilisés pour exécuter des serveurs Edge Skype entreprise Server.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Inclut les serveurs qui peuvent participer à la réplication du Windows Store de la gestion centrale de Skype entreprise Server.  <br/> |
|RTCSBAUniversalServices  <br/> |Octroie un accès en lecture seule aux paramètres du serveur Skype entreprise, mais permet une configuration pour l’installation d’un serveur de succursales survivant et du déploiement d’une application de branchement plus survivant.  <br/> |

La préparation de la forêt ajoute ensuite des groupes de services et d’administration aux groupes d’infrastructure appropriés, comme suit:

- RTCUniversalServerAdmins est ajouté à RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.

- RTCUniversalUserAdmins est ajouté en tant que membre de RTCUniversalGlobalReadOnlyGroup, de RTCUniversalServerReadOnlyGroup et d’RTCUniversalUserReadOnlyGroup.

- RTCHSUniversalServices, RTCComponentUniversalServices et RTCUniversalReadOnlyAdmins sont ajoutés en tant que membres de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.

La préparation de la forêt crée également les groupes de contrôle d’accès basés sur les rôles suivants:

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

Pour plus d’informations sur les rôles RBAC et les tâches qui leur sont autorisées, voir [contrôle d’accès basé sur un rôle](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) dans la documentation de planification.

La préparation de la forêt crée des entrées ACE privées et publiques. Il crée des ACE privées sur le conteneur de paramètres globaux utilisé par Skype entreprise Server. Ce conteneur est utilisé uniquement par Skype entreprise Server et réside dans le conteneur de configuration ou dans le conteneur système du domaine racine, en fonction de l’emplacement de stockage des paramètres globaux. Les ACE publiques créées par une préparation de forêt sont répertoriées dans le tableau suivant.

**ACE publiques créées par une préparation de forêt**


| **MAILLOTS**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| Lire le conteneur système du domaine racine (non hérité)**\\**\* <br/>        | X  <br/>                            |
| Lecture du conteneur de configuration de DisplaySpecifiers (non hérité)  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>* Les ACE qui ne sont pas héritées n’accordent pas l’accès aux objets enfants sous ces conteneurs. Les As héritent d’octroyer l’accès à des objets enfants sous ces conteneurs.

Dans le conteneur Configuration, sous le contexte d’appellation de configuration, la préparation de la forêt effectue les tâches suivantes:

- Ajoute une entrée **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** pour la page de **Propriétés RTC** sous les attributs adminContextMenu et adminPropertyPages du spécificateur d’affichage de langue pour les utilisateurs, les contacts et les inetOrgPersons (par exemple, CN = user-Display, CN = 409, CN = DisplaySpecifiers).

- Ajoute un objet **RTCPropertySet** de type **ControlAccessRight** sous **droits étendus** qui s’appliquent aux classes d’utilisateur et de contact.

- Ajoute un objet **RTCUserSearchPropertySet** de type **ControlAccessRight** sous **privilèges étendus** qui s’applique aux classes utilisateur, contact, UO et domainDNS.

- Ajoute **msRTCSIP-PrimaryUserAddress** sous l’attribut **extraColumns** de chaque spécificateur d’affichage de l’unité d’organisation (UO) Language (par exemple, CN = ORGANIZATIONALUNIT-Display, CN = 409, CN = DisplaySpecifiers) et copie les valeurs du **extraColumnsx** xxxxxxxxx XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX

- Ajoute les attributs de filtre **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**et **msRTCSIP-UserEnabled** sous l’attribut **attributeDisplayNames** de chaque spécificateur d’affichage de langue pour les utilisateurs, les contacts, et les objets InetOrgPerson (par exemple, en anglais: CN = user-Display, CN = 409, CN = DisplaySpecifiers).


