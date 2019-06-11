---
title: 'Lync Server 2013 : Planification du contrôle d’accès basé sur un rôle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1771eb906685294e588e0c67b1fa8fb1f67a8b6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a>Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2015-01-27_

Pour vous permettre de déléguer des tâches administratives tout en préservant la sécurité, Lync Server 2013 offre le contrôle d’accès basé sur les rôles (RBAC). Avec le RBAC, le privilège administratif est accordé en attribuant aux utilisateurs des rôles d’administration. Lync Server 2013 inclut un ensemble étendu de rôles d’administrateur intégrés, et vous permet également de créer de nouveaux rôles et de spécifier une liste personnalisée d’applets de construction pour chaque nouveau rôle. Vous pouvez également ajouter des scripts d’applets de commande aux tâches autorisées des rôles RBAC prédéfinis et personnalisés.

<div>

## <a name="better-server-security-and-centralization"></a>Meilleure sécurité serveur et centralisation

Le RBAC, l’accès et l’autorisation sont basés précisément sur le rôle de serveur Lync de l’utilisateur. Cela permet de recourir à la sécurité de «privilèges minimum», en accordant aux administrateurs et aux utilisateurs uniquement les droits nécessaires à leur travail.

<div>


> [!IMPORTANT]  
> Les restrictions RBAC fonctionnent uniquement pour les administrateurs travaillant à distance à l’aide du panneau de configuration de Lync Server ou de Lync Server Management Shell. Un utilisateur assis sur un serveur exécutant Lync Server n’est pas limité par le RBAC. Par conséquent, la sécurité physique de votre serveur Lync est importante pour préserver les restrictions RBAC.



</div>

</div>

<div>

## <a name="roles-and-scope"></a>Rôles et étendue

Dans le RBAC, un *rôle* est activé pour utiliser une liste de cmdlets, conçue pour être utile à un certain type d’administrateur ou de technicien. Une *étendue* est le jeu d’objets sur lequel les applets de action définis dans un rôle peuvent opérer. Les objets concernés par une étendue peuvent être des comptes d’utilisateurs (regroupés par unité d’organisation) ou des serveurs (regroupés par site).

Le tableau suivant répertorie les rôles prédéfinis dans Lync Server et offre une vue d’ensemble des types de tâches que vous pouvez effectuer. La quatrième colonne indique le rôle Microsoft Exchange Server similaire pour chaque rôle serveur Lync, s’il en existe une.

### <a name="predefined-administrative-roles"></a>Rôles d’administration prédéfinis

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rôle</th>
<th>Tâches autorisées</th>
<th>Groupe Active Directory sous-jacent</th>
<th>Équivalent Exchange</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CsAdministrator</p></td>
<td><p>Peut effectuer toutes les tâches administratives et modifier tous les paramètres, y compris la création de rôles et l’attribution d’utilisateurs aux rôles. Peut développer un déploiement en ajoutant de nouveaux sites, groupes et services.</p></td>
<td><p>CSAdministrator</p></td>
<td><p>Gestion de l’Organisation</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>Possibilité d’activer et de désactiver des utilisateurs pour Lync Server, de déplacer des utilisateurs et d’affecter des stratégies existantes aux utilisateurs. Impossible de modifier les stratégies.</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>Destinataires du courrier</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>Peut créer, configurer et gérer les paramètres et les stratégies relatives à la voix.</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="even">
<td><p>CsServerAdministrator</p></td>
<td><p>Peut gérer, surveiller et résoudre les problèmes liés aux serveurs et services. Peut empêcher de nouvelles connexions aux serveurs, d’arrêter et de démarrer des services et d’appliquer des mises à jour logicielles. Ne peut pas apporter de modifications avec un impact sur la configuration globale.</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>Gestion du serveur</p></td>
</tr>
<tr class="odd">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>Peut afficher le déploiement, y compris des informations sur l’utilisateur et le serveur, afin d’analyser l’intégrité du déploiement.</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>Gestion de l’organisation en affichage seul</p></td>
</tr>
<tr class="even">
<td><p>CsHelpDesk</p></td>
<td><p>Peut afficher le déploiement, y compris les propriétés et les stratégies de l’utilisateur. Peut exécuter des tâches de résolution des problèmes spécifiques. Impossible de modifier les propriétés de l’utilisateur ou les stratégies, la configuration du serveur ou les services.</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>Support technique</p></td>
</tr>
<tr class="odd">
<td><p>CsArchivingAdministrator</p></td>
<td><p>Peut modifier la configuration et les stratégies d’archivage.</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>Gestion de la rétention, conservation légale</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>Peut gérer la configuration de l’application Response Group dans un site.</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="odd">
<td><p>CsLocationAdministrator</p></td>
<td><p>Niveau de droits le plus faible pour une gestion améliorée de 9-1-1 (E9-1-1), y compris la création d’emplacements E9-1-1 Ce rôle est toujours affecté avec une étendue globale.</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupManager</p></td>
<td><p>Peut gérer des groupes de réponse spécifiques.</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="odd">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>Peut gérer la fonctionnalité de conversation permanente et des salles de conversation permanentes spécifiques.</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>Non applicable</p></td>
</tr>
</tbody>
</table>


Tous les rôles prédéfinis fournis dans Lync Server ont une étendue globale. Pour suivre les pratiques de gestion des privilèges minimum, vous ne devez pas affecter des utilisateurs aux rôles avec l’étendue globale s’ils ne peuvent gérer qu’un ensemble limité de serveurs ou d’utilisateurs. Pour ce faire, vous pouvez créer des rôles basés sur un rôle existant, mais avec une étendue plus limitée.

<div>

## <a name="creating-a-scoped-role"></a>Création d’un rôle à l’étendue

Lorsque vous créez un rôle avec une étendue limitée (un rôle étendu), vous spécifiez l’étendue, ainsi que le rôle existant sur lequel elle est basée, et le groupe Active Directory doit être affecté au rôle. Le groupe Active Directory que vous spécifiez doit déjà être créé. L’applet de commande suivante est un exemple de création d’un rôle qui dispose des autorisations de l’un des rôles d’administration prédéfinis, mais avec une étendue limitée. Il crée un nouveau rôle appelé `Site01 Server Administrators`. Le rôle est doté des capacités du rôle CsServerAdministrator prédéfini, mais uniquement pour les serveurs situés dans le site Site01. Pour que cette applet de action fonctionne, le site Site01 doit déjà être défini et un groupe de sécurité `Site01 Server Administrators` universelle nommé doit déjà exister.

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

Après l’exécution de cette cmdlet, tous les utilisateurs membres du `Site01 Server Administrators` groupe disposent de privilèges d’administrateur serveur pour les serveurs dans Site01. De plus, tous les utilisateurs ajoutés par le biais de ce groupe de sécurité universelle disposent également des privilèges de ce rôle. Notez que le rôle lui-même et le groupe de sécurité universel auquel il est affecté sont `Site01 Server Administrators`appelés.

Dans l’exemple suivant, la portée utilisateur est limitée au lieu de l’étendue du serveur. Il crée un `Sales Users Administrator` rôle pour gérer les comptes d’utilisateur dans l’unité d’organisation ventes. Le groupe de sécurité universelle SalesUsersAdministrator doit déjà être créé pour que cette applet de action fonctionne.

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a>Création d’un nouveau rôle

Pour créer un rôle ayant accès à un ensemble d’applets de fonction qui ne figurent pas dans l’un des rôles prédéfinis, ou à un ensemble de scripts ou de modules, vous commencez par utiliser l’un des rôles prédéfinis en tant que modèle. Notez que les scripts et les modules que vous pouvez exécuter doivent être stockés dans les emplacements suivants:

  - Le chemin d’accès au module Lync, qui est par\\défaut C\\: Program\\files Fichiers communs Microsoft\\Lync\\Server 2013 modules Lync

  - Le chemin d’accès du script utilisateur, qui est par\\défaut C\\: fichiers\\programme fichiers communs Microsoft\\Lync Server 2013 Adminscripts

Pour créer un nouveau rôle, vous devez utiliser l’applet **de nouvelle applet de nouveau-CsAdminRole** . Avant d’exécuter **New-CsAdminRole**, vous devez commencer par créer le groupe de sécurité universelle sous-jacent qui sera associé à ce rôle.

Les applets de commande suivantes constituent un exemple de création d’un nouveau rôle. Ils créent un nouveau type de rôle `MyHelpDeskScriptRole`appelé. Le nouveau rôle est doté des capacités du rôle CsHelpDesk prédéfini et peut également exécuter les fonctions dans un script appelé «TestScript».

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

Pour que cette applet de action fonctionne, vous devez commencer par créer le groupe de sécurité MyHelpDeskScriptRole.

Après l’exécution de cette cmdlet, vous pouvez attribuer des utilisateurs directement à ce rôle (auquel cas il s’agit d’une étendue globale), ou créer un rôle d’étendue en fonction de ce rôle, comme décrit dans la rubrique Création d’un rôle d’étendue, précédemment dans ce document.

</div>

<div>

## <a name="assigning-roles-to-users"></a>Attribution de rôles aux utilisateurs

Chaque rôle serveur Lync est associé à un groupe de sécurité universelle Active Directory sous-jacent. Tout utilisateur que vous ajoutez au groupe sous-jacent obtient les compétences de ce rôle.

Les exemples figurant dans les sections précédentes ont créé un nouveau rôle et ont attribué un groupe de sécurité universelle existant au nouveau rôle. Pour attribuer un rôle existant à un ou plusieurs utilisateurs, ajoutez ces utilisateurs au groupe associé au rôle. Vous pouvez ajouter des utilisateurs individuels et des groupes de sécurité universelle à ces groupes.

Par exemple, le rôle **CsAdministrator** est automatiquement accordé au groupe de sécurité universelle **administrateurs CS** dans Active Directory. Ce groupe de sécurité universel est créé dans Active Directory lorsque vous déployez Lync Server. Pour accorder ce privilège à un utilisateur ou à un groupe, vous pouvez simplement l’ajouter au groupe **administrateurs CS** .

Plusieurs rôles RBAC peuvent être attribués à un utilisateur en étant ajoutés aux groupes Active Directory sous-jacents correspondant à chaque rôle.

Notez que lorsque vous créez un rôle, les utilisateurs qui ont été ajoutés par la suite au groupe Active Directory sous-jacent tirent parti des capacités de ce rôle.

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a>Modification des capacités d’un rôle

Vous pouvez modifier la liste des cmdlets et des scripts qu’un rôle peut exécuter. Vous pouvez modifier les applets de souscription et les scripts que les rôles personnalisés peuvent exécuter, mais vous pouvez uniquement modifier les scripts pour les rôles prédéfinis. Chaque cmdlet que vous entrez peut ajouter, supprimer ou remplacer des cmdlets ou des scripts.

Pour modifier un rôle, utilisez l’applet **de cmdlet Set-CsAdminRole** . L’applet de commande suivante supprime un script du rôle.

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a>Planification de RBAC

Pour chaque personne qui doit être disposant de droits d’administration pour votre déploiement de Lync Server, envisagez les tâches que vous devez effectuer, puis affectez-les aux rôles possédant le moins de privilèges et d’étendue nécessaires pour leur travail. Le cas échéant, vous pouvez utiliser l’applet de cmdlet **Set-CsAdminRole** pour créer un nouveau rôle uniquement pour les applets de applet nécessaires aux tâches de cette personne.

Les utilisateurs disposant du rôle CsAdministrator peuvent créer tous types de rôles, y compris des rôles basés sur CsAdministrator, et leur affecter des utilisateurs. Il est recommandé d’affecter le rôle CsAdministrator à un très petit ensemble d’utilisateurs approuvés.

</div>

</div>

<span> </span>

</div>

</div>

</div>

