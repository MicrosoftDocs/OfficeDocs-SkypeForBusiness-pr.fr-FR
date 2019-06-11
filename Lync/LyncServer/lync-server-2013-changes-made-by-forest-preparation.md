---
title: 'Lync Server 2013: modifications apportées par la préparation de la forêt'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef94ea82f31871cf90939aa25a130903f15ef756
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a>Modifications apportées par la préparation de la forêt dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-30_

Cette section décrit les paramètres globaux et les objets, ainsi que les groupes de services et d’administration universels créés par l’étape de préparation de la forêt.

<div>

## <a name="active-directory-global-settings-and-objects"></a>Paramètres globaux et objets Active Directory

Si vous stockez des paramètres globaux dans le conteneur de configuration (comme pour tous les nouveaux déploiements de Lync Server 2013), la préparation de la forêt utilise le conteneur services existants et ajoute un\\objet **Service RTC** sous les services de configuration. objet. Sous l’objet RTC service, la préparation de la forêt ajoute un objet de **paramètres globaux** de type MsRTCSIP-GlobalContainer. L’objet paramètres globaux contient tous les paramètres qui s’appliquent au déploiement de Lync Server. Si vous stockez des paramètres globaux dans le conteneur système, la préparation de la forêt utilise un conteneur Microsoft sous le conteneur système du domaine racine et\\un objet service RTC sous l’objet Microsoft système.

La préparation de la forêt ajoute également un nouvel objet **msRTCSIP-Domain** pour le domaine racine dans lequel la procédure est exécutée.

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a>Service universel et groupes d’administration Active Directory

La préparation de la forêt crée des groupes universels en fonction du domaine que vous spécifiez et ajoute des entrées de contrôle d’accès (ACE) pour ces groupes. Cette étape permet de créer des groupes universels dans les conteneurs d’utilisateurs du domaine que vous spécifiez.

Les groupes universels permettent aux administrateurs d’accéder aux paramètres globaux et de gérer ces derniers. La préparation de la forêt ajoute les types suivants de groupes universels:

  - **Groupes d’administration**   ces groupes définissent des rôles d’administrateur pour un réseau Lync Server.

  - **Groupes d’infrastructure**   ces groupes fournissent l’autorisation d’accéder à des zones spécifiques de l’infrastructure du serveur Lync. Ils fonctionnent en tant que composants de groupes d’administration. Vous ne devez pas modifier ces groupes ni y ajouter des utilisateurs directement.

  - **Services les groupes**   sont des comptes de service nécessaires pour accéder à différents services Lync Server.

Le tableau suivant décrit les groupes d’administration.

### <a name="administrative-groups-created-during-forest-preparation"></a>Groupes d’administration créés lors de la préparation de la forêt

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Groupe d’administration</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Permet aux membres de gérer les paramètres du serveur et du pool, y compris tous les rôles de serveur, les paramètres globaux et les utilisateurs.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Permet aux membres de gérer les paramètres utilisateur et de déplacer les utilisateurs d’un serveur ou d’un pool vers un autre.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>Permet aux membres de lire les paramètres du serveur, du pool et de l’utilisateur.</p></td>
</tr>
</tbody>
</table>


Le tableau suivant décrit les groupes d’infrastructure.

### <a name="infrastructure-groups-created-during-forest-preparation"></a>Groupes d’infrastructure créés lors de la préparation de la forêt

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Groupe d’infrastructure</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalGlobalWriteGroup</p></td>
<td><p>Accorde l’accès en écriture aux objets de paramètres globaux de Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalGlobalReadOnlyGroup</p></td>
<td><p>Octroie un accès en lecture seule aux objets de paramètres globaux pour Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Octroie un accès en lecture seule aux paramètres utilisateur de Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Octroie un accès en lecture seule aux paramètres du serveur Lync. Ce groupe n’a pas accès aux paramètres de niveau de regroupement, uniquement aux paramètres spécifiques à un serveur individuel.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>Octroie un accès en lecture seule à la configuration du serveur Lync et est placé dans le groupe administrateurs locaux des appareils de succursales survivables au cours de l’installation.</p></td>
</tr>
</tbody>
</table>


Le tableau suivant décrit les groupes de services.

### <a name="service-groups-created-during-forest-preparation"></a>Groupes de services créés lors de la préparation de la forêt

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Groupe de services</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Inclut les comptes de service utilisés pour exécuter les serveurs front-end Server et Standard Edition. Ce groupe permet à un serveur en lecture/écriture de l’accès en lecture/écriture aux paramètres globaux et aux objets utilisateurs Active Directory de Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>Inclut les comptes de service utilisés pour exécuter des serveurs de conférence A/V, des services Web, un serveur de médiation, un serveur d’archivage et un serveur de surveillance.</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>Inclut les comptes de service utilisés pour exécuter les serveurs Edge de Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>Inclut les serveurs qui peuvent participer à la réplication du magasin de gestion central de Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>Octroie un accès en lecture seule aux paramètres du serveur Lync, mais permet une configuration pour l’installation d’un serveur de succursales survivant et du déploiement d’une unité de branchement plus survivant.</p></td>
</tr>
</tbody>
</table>


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

Pour plus d’informations sur les rôles RBAC et les tâches autorisées pour chacun, voir [planification du contrôle d’accès basé sur les rôles dans Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) dans la documentation de planification.

La préparation de la forêt crée des entrées ACE privées et publiques. Il crée des ACE privées sur le conteneur de paramètres globaux utilisé par Lync Server. Ce conteneur est utilisé uniquement par Lync Server et réside dans le conteneur de configuration ou dans le conteneur système du domaine racine, en fonction de l’emplacement de stockage des paramètres globaux. Les ACE publiques créées par une préparation de forêt sont répertoriées dans le tableau suivant.

### <a name="public-aces-created-by-forest-preparation"></a>ACE publiques créées par une préparation de forêt

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>MAILLOTS</th>
<th>RTCUniversalGlobalReadOnlyGroup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lire le conteneur système du domaine racine (non hérité)<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>Lecture du conteneur de configuration de DisplaySpecifiers (non hérité)</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>*</STRONG>Les ACE qui ne sont pas héritées n’accordent pas l’accès aux objets enfants sous ces conteneurs. Les As héritent d’octroyer l’accès à des objets enfants sous ces conteneurs.



</div>

Dans le conteneur Configuration, sous le contexte d’appellation de configuration, la préparation de la forêt effectue les tâches suivantes:

  - Ajoute une entrée **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** pour la page de **Propriétés RTC** sous les attributs adminContextMenu et adminPropertyPages du spécificateur d’affichage de langue pour les utilisateurs, les contacts et les inetOrgPersons (par exemple, CN = user-Display, CN = 409, CN = DisplaySpecifiers).

  - Ajoute un objet **RTCPropertySet** de type **ControlAccessRight** sous **droits étendus** qui s’appliquent aux classes d’utilisateur et de contact.

  - Ajoute un objet **RTCUserSearchPropertySet** de type **ControlAccessRight** sous **privilèges étendus** qui s’applique aux classes utilisateur, contact, UO et domainDNS.

  - Ajoute **msRTCSIP-PrimaryUserAddress** sous l’attribut **extraColumns** de chaque spécificateur d’affichage de l’unité d’organisation (UO) Language (par exemple, CN = ORGANIZATIONALUNIT-Display, CN = 409, CN = DisplaySpecifiers) et copie les valeurs du **extraColumnsx** xxxxxxxxx XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX

  - Ajoute les attributs de filtre **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**et **msRTCSIP-UserEnabled** sous l’attribut **attributeDisplayNames** de chaque spécificateur d’affichage de langue pour les utilisateurs, les contacts, et les objets InetOrgPerson (par exemple, en anglais: CN = user-Display, CN = 409, CN = DisplaySpecifiers).

</div>

</div>

<span> </span>

</div>

</div>

</div>

