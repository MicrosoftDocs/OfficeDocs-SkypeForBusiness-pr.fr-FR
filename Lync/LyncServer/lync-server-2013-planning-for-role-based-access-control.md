---
title: 'Lync Server 2013 : planification du contrôle d’accès basé sur un rôle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d88353019a266fbb094df8808faa4543e31bf562
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a>Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-01-27_

Pour vous permettre de déléguer des tâches administratives tout en conservant des normes de sécurité élevées, Lync Server 2013 offre un contrôle d’accès basé sur un rôle (RBAC). Avec le contrôle d’accès basé sur un rôle, le privilège administratif est accordé en affectant des rôles d’administrateur aux utilisateurs. Lync Server 2013 inclut un ensemble complet de rôles administratifs intégrés, et vous permet également de créer de nouveaux rôles et de spécifier une liste personnalisée d’applets de commande pour chaque nouveau rôle. Vous pouvez aussi ajouter des scripts d’applets de commande aux tâches autorisées des rôles RBAC prédéfinis et personnalisés.

<div>

## <a name="better-server-security-and-centralization"></a>Centralisation et sécurité du serveur améliorées

Avec RBAC, l’accès et l’autorisation sont basés précisément sur le rôle Lync Server d’un utilisateur. Cela permet la mise en œuvre de la pratique de sécurité du « privilège minimum », qui accorde aux administrateurs et aux utilisateurs uniquement les droits nécessaires à la réalisation de leur travail.

<div>


> [!IMPORTANT]  
> Les restrictions RBAC fonctionnent uniquement sur les administrateurs travaillant à distance, à l’aide du panneau de configuration Lync Server ou de Lync Server Management Shell. Un utilisateur se trouvant sur un serveur exécutant Lync Server n’est pas limité par RBAC. Par conséquent, la sécurité physique de votre serveur Lync Server est importante pour conserver les restrictions RBAC.



</div>

</div>

<div>

## <a name="roles-and-scope"></a>Rôles et étendue

Dans le cadre de RBAC, un *rôle* est autorisé à utiliser une liste d’applets de commande conçues pour rendre service à un certain type d’administrateur ou de technicien. Une *étendue* est l’ensemble d’objets que peuvent exploiter les applets de commande définies dans un rôle. Les objets couverts par l’étendue peuvent être des comptes d’utilisateurs (regroupés par unité d’organisation) ou des serveurs (regroupés par site).

Le tableau suivant répertorie les rôles prédéfinis dans Lync Server et offre une vue d’ensemble des types de tâches que chaque peut effectuer. La quatrième colonne indique le rôle Microsoft Exchange Server similaire pour chaque rôle Lync Server, s’il en existe un.

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
<th>Role</th>
<th>Tâches autorisées</th>
<th>Groupe Active Directory sous-jacent</th>
<th>Équivalent Exchange</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CsAdministrator</p></td>
<td><p>Permet d’effectuer toutes les tâches d’administration et de modifier tous les paramètres, y compris la création de rôles et l’affectation d’utilisateurs aux rôles. Permet de développer un déploiement en ajoutant de nouveaux sites, pools et services.</p></td>
<td><p>CSAdministrator</p></td>
<td><p>Organization Management</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>Peut activer et désactiver des utilisateurs pour Lync Server, déplacer des utilisateurs et affecter des stratégies existantes aux utilisateurs. Ne permet pas de modifier des stratégies.</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>Mail Recipients</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>Permet de créer, configurer et gérer les stratégies et les paramètres liés à la voix.</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>Non applicable.</p></td>
</tr>
<tr class="even">
<td><p>CsServerAdministrator</p></td>
<td><p>Permet de gérer, surveiller et dépanner des serveurs et des services. Permet d’empêcher de nouvelles connexions aux serveurs, d’arrêter et de démarrer des services, et d’appliquer des mises à jour logicielles. Ne permet pas d’effectuer des modifications ayant un impact de configuration global.</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>Server Management</p></td>
</tr>
<tr class="odd">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>Permet de visualiser le déploiement, notamment les informations d’utilisateur et de serveur, afin de surveiller l’état du déploiement.</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>View-Only Organization Management</p></td>
</tr>
<tr class="even">
<td><p>CsHelpDesk</p></td>
<td><p>Permet d’afficher le déploiement, notamment les stratégies et les propriétés d’utilisateurs. Permet d’exécuter des tâches de dépannage spécifiques. Ne permet pas de modifier les stratégies et les propriétés d’utilisateurs, la configuration du serveur ou les services.</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>Centre</p></td>
</tr>
<tr class="odd">
<td><p>CsArchivingAdministrator</p></td>
<td><p>Permet de modifier les stratégies et la configuration de l’archivage.</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>Retention Management, Legal Hold</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>Permet de gérer la configuration de l’application Response Group dans un site.</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="odd">
<td><p>CsLocationAdministrator</p></td>
<td><p>Niveau de droits le plus bas pour la gestion Enhanced 9-1-1 (E9-1-1), y compris la création d’identificateurs réseau et d’emplacements E9-1-1, ainsi que leur association entre eux. Ce rôle est toujours affecté avec une étendue globale.</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupManager</p></td>
<td><p>Permet de gérer des groupes Response Group spécifiques.</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="odd">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>Permet de gérer la fonctionnalité Conversation permanente, ainsi que des salles de conversation permanente.</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>Non applicable</p></td>
</tr>
</tbody>
</table>


Tous les rôles prédéfinis fournis dans Lync Server ont une étendue globale. Pour respecter les pratiques du « privilège minimum », vous ne devez pas affecter d’utilisateurs à des rôles ayant une étendue globale s’ils doivent uniquement administrer un groupe limité de serveurs ou d’utilisateurs. Pour ce faire, vous pouvez créer des rôles basés sur un rôle existant, mais avec une étendue plus limitée.

<div>

## <a name="creating-a-scoped-role"></a>Création d’un rôle inclus dans une étendue

Quand vous créez un rôle ayant une étendue limitée (rôle inclus dans une étendue), vous spécifiez l’étendue et le rôle existant sur lequel il est basé, mais aussi le groupe Active Directory auquel le rôle est affecté. Le groupe Active Directory que vous spécifiez doit déjà être créé. L’applet de commande suivante est un exemple de création d’un rôle ayant les privilèges de l’un des rôles d’administrateur prédéfinis, mais dont l’étendue est limitée. Il crée un rôle appelé `Site01 Server Administrators`. Le rôle a les capacités du rôle CsServerAdministrator prédéfini, mais seulement pour les serveurs situés dans le site Site01. Pour que cette applet de commande fonctionne, le site Site01 doit déjà être défini et un groupe de sécurité `Site01 Server Administrators` universel nommé doit déjà exister.

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

Une fois cette cmdlet exécutée, tous les utilisateurs membres du `Site01 Server Administrators` groupe disposent des privilèges d’administrateur de serveur pour les serveurs dans Site01. De plus, tous les utilisateurs qui sont ajoutés ultérieurement à ce groupe de sécurité universel obtiendront également les privilèges de ce rôle. Notez que le rôle lui-même et le groupe de sécurité universel auquel il est affecté sont `Site01 Server Administrators`appelés.

L’exemple suivant limite l’étendue d’utilisateur au lieu de l’étendue du serveur. Il crée un `Sales Users Administrator` rôle pour administrer les comptes d’utilisateur dans l’unité d’organisation Sales. Le groupe de sécurité universel SalesUsersAdministrator doit déjà être créé pour que cette cmdlet fonctionne.

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a>Création d’un rôle

Pour créer un rôle ayant accès à un ensemble d’applets de commande non inclus dans l’un des rôles prédéfinis, ou à un ensemble de scripts ou de modules, vous devez encore une fois commencer par utiliser l’un des rôles prédéfinis comme modèle. Notez que les scripts et les modules que les rôles sont tenus d’exécuter doivent être stockés aux emplacements suivants :

  - Le chemin d’accès au module Lync, par défaut C\\: Program\\Files Common\\Files Microsoft Lync Server\\2013\\modules Lync

  - Le chemin d’accès au script utilisateur, par défaut C\\: Program\\Files Common\\Files Microsoft Lync Server\\2013 Adminscripts

Pour créer un rôle, vous devez utiliser l’applet de commande **New-CsAdminRole**. Avant d’exécuter **New-CsAdminRole**, vous devez d’abord créer le groupe de sécurité universel sous-jacent qui sera associé à ce rôle.

Les applets de commande suivantes servent d’exemple pour la création d’un rôle. Ils créent un nouveau type de rôle `MyHelpDeskScriptRole`appelé. Ce nouveau rôle offre les mêmes capacités que le rôle prédéfini CsHelpDesk avec en outre la possibilité d’exécuter les fonctions d’un script nommé « testscript ».

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

Pour que cette applet de commande fonctionne, vous devez d’abord avoir créé le groupe de sécurité universel MyHelpDeskScriptRole.

Après avoir exécuté cette applet de commande, vous pouvez directement affecter des utilisateurs à ce rôle (dans ce cas, ils ont une étendue globale) ou créer un rôle inclus dans une étendue basé sur ce rôle, comme expliqué dans Création d’un rôle inclus dans une étendue, plus haut dans ce document.

</div>

<div>

## <a name="assigning-roles-to-users"></a>Affectation de rôles aux utilisateurs

Chaque rôle Lync Server est associé à un groupe de sécurité universel Active Directory sous-jacent. Tous les utilisateurs que vous ajoutez au groupe sous-jacent héritent des capacités de ce rôle.

Les exemples des sections précédentes ont créé un nouveau rôle et attribué un groupe de sécurité universel existant au nouveau rôle. Pour affecter un rôle existant à un ou plusieurs utilisateurs, ajoutez ces utilisateurs au groupe associé au rôle. Vous pouvez ajouter des utilisateurs individuels et des groupes de sécurité universels à ces groupes.

Par exemple, le rôle **CsAdministrator** est automatiquement accordé au groupe de sécurité universel **administrateurs CS** dans Active Directory. Ce groupe de sécurité universel est créé dans Active Directory lorsque vous déployez Lync Server. Pour accorder ce privilège à un utilisateur ou à un groupe, vous pouvez simplement l’ajouter au groupe **CS Administrators**.

Un utilisateur peut se voir affecter plusieurs rôles RBAC en étant ajouté aux groupes Active Directory sous-jacents qui correspondent à chaque rôle.

Veuillez noter que lorsque vous créez un rôle, les utilisateurs qui sont par la suite ajoutés au groupe Active Directory sous-jacent sont dotés des capacités de ce rôle

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a>Modification des capacités d’un rôle

Vous pouvez modifier la liste des applets de commande et des scripts qu’un rôle peut exécuter. Dans le cas des rôles personnalisés, vous pouvez modifier à la fois les applets de commande et les scripts. Dans le cas des rôles prédéfinis, vous pouvez modifier uniquement les scripts. Chaque applet de commande que vous tapez peut ajouter, supprimer ou remplacer des applets de commande ou des scripts.

Pour modifier un rôle, utilisez l’applet de commande **Set-CsAdminRole**. L’applet de commande suivante supprime un script du rôle.

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a>Planification pour RBAC

Pour chaque personne qui doit disposer de n’importe quel type de droits d’administration pour votre déploiement Lync Server, déterminez exactement les tâches qu’elles doivent effectuer, puis affectez-les aux rôles avec le privilège et l’étendue les moins appropriés pour leur travail. Si nécessaire, vous pouvez utiliser l’applet de commande **Set-CsAdminRole** pour créer un rôle associée aux seules applets de commande nécessaires à l’exécution des tâches de cette personne.

Les utilisateurs qui disposent du rôle CsAdministrator peuvent créer tous les types de rôles, y compris les rôles basés sur CsAdministrator, et leur affecter des utilisateurs. La meilleure pratique consiste à affecter le rôle CsAdministrator à un très petit groupe d’utilisateurs approuvés.

</div>

</div>

<span> </span>

</div>

</div>

</div>

