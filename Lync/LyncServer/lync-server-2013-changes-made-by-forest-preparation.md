---
title: Modifications effectuées par la préparation de la forêt dans Lync Server 2013
TOCTitle: Modifications effectuées par la préparation de la forêt dans Lync Server 2013
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425791(v=OCS.15)
ms:contentKeyID: 49296740
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modifications effectuées par la préparation de la forêt dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Cette section décrit les paramètres globaux, les objets et les groupes de services universels et d’administration créés pendant la préparation de la forêt.

## Paramètres globaux et objets Active Directory

Si vous stockez des paramètres globaux dans un conteneur de configuration (comme c’est le cas pour tous les nouveaux déploiements de Lync Server 2013), la préparation de la forêt utilise le conteneur de services existant et ajoute un objet **RTC Service** sous l’objet Configuration\\Services. Sous l’objet RTC Service, la préparation de la forêt ajoute un objet **Paramètres globaux** de type msRTCSIP-GlobalContainer. Cet objet contient tous les paramètres qui s’appliquent au déploiement Lync Server. Si vous choisissez de stocker les paramètres globaux dans le conteneur système, la préparation de la forêt ajoute un conteneur Microsoft sous le conteneur système du domaine racine et un nouvel objet RTC Service sous l’objet System\\Microsoft.

La préparation de la forêt ajoute également un nouvel objet **msRTCSIP-Domain** pour le domaine racine dans lequel la procédure est exécutée.

## Groupes de services universels et d’administration Active Directory

La préparation de la forêt crée des groupes universels basés sur le domaine que vous spécifiez et ajoute des entrées de contrôle d’accès (ACE) pour ces groupes. Cette étape crée les groupes universels dans les conteneurs d’utilisateurs du domaine que vous spécifiez.

Les groupes universels permettent aux administrateurs d’accéder aux services et aux paramètres globaux et de les gérer. La préparation de la forêt ajoute les types de groupes universels suivants :

  - **Groupes d’administration** : ces groupes définissent les rôles d’administrateur sur un réseau Lync Server.

  - **Groupes d’infrastructure** : ces groupes permettent d’accéder à des zones spécifiques de l’infrastructure Lync Server. Ils fonctionnent comme composants des groupes d’administration. Vous ne devez pas modifier ces groupes ni leur ajouter directement des utilisateurs.

  - **Groupes de services** : ces groupes sont des comptes de services requis pour accéder à différents services Lync Server.

Le tableau suivant présente les groupes d’administration.

### Groupes d’administration créés lors de la préparation de la forêt

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
<td><p>Permet à ses membres de gérer les paramètres de serveurs et de pools, notamment tous les rôles de serveurs, les paramètres globaux et les utilisateurs.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Permet à ses membres de gérer les paramètres utilisateur et de transférer des utilisateurs d’un serveur ou pool à un autre.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>Permet à ses membres d’accéder en lecture aux paramètres de serveur, de pool et d’utilisateur.</p></td>
</tr>
</tbody>
</table>


Le tableau suivant présente les groupes d’infrastructure.

### Groupes d’infrastructure créés lors de la préparation de la forêt

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
<td><p>Permet d’accéder en écriture aux objets de paramètres globaux pour Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalGlobalReadOnlyGroup</p></td>
<td><p>Permet d’accéder en lecture seule aux objets de paramètres globaux pour Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Permet d’accéder en lecture seule aux paramètres utilisateur Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Permet d’accéder en lecture seule aux paramètres Lync Server. Ce groupe n’a pas accès aux paramètres de niveau pool, mais uniquement aux paramètres spécifiques à un serveur donné.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>Permet d’accéder en lecture seule à la configuration Lync Server. Ce groupe est placé dans le groupe Administrateurs locaux des Survivable Branch Appliances au cours de l’installation.</p></td>
</tr>
</tbody>
</table>


Le tableau suivant présente les groupes de services.

### Groupes de services créés lors de la préparation de la forêt

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
<td><p>Comprend les comptes de service utilisés pour exécuter le serveur frontal et les serveurs Standard Edition. Ce groupe permet d’accéder en lecture/écriture aux paramètres globaux de Lync Server et aux objets utilisateur Active Directory.</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>Comprend les comptes de service utilisés pour exécuter les serveurs de conférence A/V, les services web, le serveur de médiation, le serveur d’archivage et le serveur de surveillance.</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>Comprend les comptes de service utilisés pour exécuter les serveurs Edge Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>Inclut les serveurs en mesure de participer à la réplication du magasin central de gestionLync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>Permet d’accéder en lecture seule aux paramètres Lync Server, mais autorise la configuration de l’installation d’un déploiement Survivable Branch Server et Survivable Branch Appliance.</p></td>
</tr>
</tbody>
</table>


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

Pour plus d’informations sur les rôles RBAC et les tâches que chaque rôle est autorisé à effectuer, voir [Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) dans la documentation de planification.

La préparation de la forêt crée des entrées de contrôle d’accès privées et publiques. Elle crée des entrées de contrôle d’accès privées sur le conteneur de paramètres globaux utilisé par Lync Server. Ce conteneur est utilisé uniquement par Lync Server. Il se trouve dans le conteneur Configuration ou le conteneur System du domaine racine, selon les options que vous spécifiez. Le tableau suivant répertorie les entrées de contrôle d’accès publiques créées par la préparation de la forêt.

### Entrées de contrôle d’accès publiques créées par la préparation de la forêt

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Entrée de contrôle d’accès</th>
<th>RTCUniversalGlobalReadOnlyGroup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lire le conteneur système du domaine racine (non héritée)<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>Lire le conteneur DisplaySpecifiers de la configuration (non héritée)</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> <strong>*</strong>Les entrées de contrôle d’accès qui ne sont pas héritées ne permettent pas d’accéder aux objets enfants qui figurent dans ces conteneurs. *Les entrées de contrôle d’accès qui sont héritées permettent d’accéder aux objets enfants qui figurent dans ces conteneurs.

La préparation de la forêt exécute les tâches suivantes sur le conteneur de configuration, sous le contexte d’affectation de noms de la configuration :

  - Ajoute une entrée **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** pour la page **RTC property** sous les attributs adminContextMenu et adminPropertyPages du spécificateur d’affichage de la langue pour les objets User, Contact et InetOrgPersons (par exemple, CN=user-Display,CN=409,CN=DisplaySpecifiers).

  - Ajoute un objet **RTCPropertySet** de type **controlAccessRight** sous **Extended-Rights** qui s’applique aux classes User et Contact.

  - Ajoute un objet **RTCUserSearchPropertySet** de type **controlAccessRight** sous **Extended-Rights** qui s’applique aux classes User, Contact, OU et DomainDNS.

  - Ajoute **msRTCSIP-PrimaryUserAddress** sous l’attribut **extraColumns** de chaque spécificateur d’affichage des unités d’organisation de la langue (CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers, par exemple) et copie des valeurs de l’attribut **extraColumns** de l’affichage par défaut (CN=default-Display, CN=409,CN=DisplaySpecifiers, par exemple).

  - Ajoute les attributs de filtrage **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** et **msRTCSIP-UserEnabled** sous l’attribut **attributeDisplayNames** de chaque spécificateur d’affichage de la langue pour les objets User, Contact et InetOrgPerson (par exemple, en anglais : CN=user-Display,CN=409,CN=DisplaySpecifiers).

