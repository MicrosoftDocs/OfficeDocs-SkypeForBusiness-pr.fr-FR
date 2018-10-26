---
title: 'Lync Server 2013 : Planification du contrôle d’accès basé sur un rôle'
TOCTitle: Planification du contrôle d’accès basé sur un rôle (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425917(v=OCS.15)
ms:contentKeyID: 49297007
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Pour vous permettre de déléguer des tâches d’administration tout en maintenant des niveaux de sécurité élevés, Lync Server 2013 propose le contrôle d’accès basé sur un rôle (RBAC). Avec le contrôle d’accès basé sur un rôle, le privilège administratif est accordé en affectant des rôles d’administrateur aux utilisateurs. Lync Server 2013 intègre un large éventail de rôles d’administrateur et permet également de créer de nouveaux rôles et de spécifier une liste personnalisée d’applets de commande pour chaque nouveau rôle. Vous pouvez aussi ajouter des scripts d’applets de commande aux tâches autorisées des rôles RBAC prédéfinis et personnalisés.

## Centralisation et sécurité du serveur améliorées

Avec le contrôle d’accès basé sur un rôle (RBAC), l’accès et l’autorisation sont basés précisément sur le rôle Lync Server de l’utilisateur. Cela permet la mise en œuvre de la pratique de sécurité du « privilège minimum », qui accorde aux administrateurs et aux utilisateurs uniquement les droits nécessaires à la réalisation de leur travail.

> [!IMPORTANT]  
> Les restrictions RBAC s’appliquent uniquement aux administrateurs qui travaillent à distance, en utilisant soit le Panneau de configuration Lync Server, soit Lync Server Management Shell. Un utilisateur qui travaille sur un serveur exécutant Lync Server n’est pas limité par RBAC. Par conséquent, la sécurité physique de Lync Server est essentielle à la préservation des restrictions RBAC.

## Rôles et étendue

Dans le cadre de RBAC, un *rôle* est autorisé à utiliser une liste d’applets de commande conçues pour rendre service à un certain type d’administrateur ou de technicien. Une *étendue* est l’ensemble d’objets que peuvent exploiter les applets de commande définies dans un rôle. Les objets couverts par l’étendue peuvent être des comptes d’utilisateurs (regroupés par unité d’organisation) ou des serveurs (regroupés par site).

Le tableau ci-dessous répertorie les rôles prédéfinis dans Lync Server et fournit une vue d’ensemble générale des types de tâches que chacun peut réaliser. La quatrième colonne présente un rôle Microsoft Exchange Server équivalent à chaque rôle Lync Server existant.

### Rôles d’administration prédéfinis

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
<th>Groupe Active Directory sous-jacent</th>
<th>Équivalent Exchange</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CsAdministrator</p></td>
<td><p>Permet d’effectuer toutes les tâches d’administration et de modifier tous les paramètres, dont la création de rôles et l’affectation d’utilisateurs aux rôles. Permet de développer un déploiement en ajoutant de nouveaux sites, pools et services.</p></td>
<td><p>CSAdministrator</p></td>
<td><p>Organization Management</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>Permet d’activer et de désactiver des utilisateurs pour Lync Server, de déplacer des utilisateurs et d’affecter des stratégies existantes aux utilisateurs. Ne permet pas de modifier des stratégies.</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>Mail Recipients</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>Permet de créer, configurer et gérer les stratégies et les paramètres liés à la voix.</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="even">
<td><p>CsServerAdministrator</p></td>
<td><p>Permet de gérer et de surveiller les serveurs et les services, d’identifier leurs problèmes et de les résoudre. Permet d’empêcher de nouvelles connexions aux serveurs, d’arrêter et de démarrer des services et d’appliquer des mises à jour logicielles. Ne permet pas d’effectuer des modifications ayant un impact de configuration global.</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>Server Management</p></td>
</tr>
<tr class="odd">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>Permet de visualiser le déploiement, notamment les informations d’utilisateur et de serveur afin de surveiller l’état du déploiement.</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>View-Only Organization Management</p></td>
</tr>
<tr class="even">
<td><p>CsHelpDesk</p></td>
<td><p>Permet d’afficher le déploiement, notamment les stratégies et les propriétés d’utilisateurs. Permet d’exécuter des tâches d’identification et de résolution des problèmes spécifiques. Ne permet pas de modifier les stratégies et les propriétés d’utilisateurs, la configuration du serveur ou les services.</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>HelpDesk</p></td>
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
<td><p>Niveau de droits le plus bas pour la gestion Enhanced 9-1-1 (E9-1-1), dont la création d’identificateurs réseau et d’emplacements E9-1-1, ainsi que leur association entre eux. Ce rôle est toujours affecté avec une étendue globale.</p></td>
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
<tr class="even">
<td><p>CsAdministrator</p></td>
<td><p>Permet d’effectuer toutes les tâches d’administration et de modifier tous les paramètres, dont la création de rôles et l’affectation d’utilisateurs aux rôles. Permet de développer un déploiement en ajoutant de nouveaux sites, pools et services.</p></td>
<td><p>CSAdministrator</p></td>
<td><p>Organization Management</p></td>
</tr>
<tr class="odd">
<td><p>CsUserAdministrator</p></td>
<td><p>Permet d’activer et de désactiver des utilisateurs pour Lync Server, de déplacer des utilisateurs et d’affecter des stratégies existantes aux utilisateurs. Ne permet pas de modifier des stratégies.</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>Mail Recipients</p></td>
</tr>
<tr class="even">
<td><p>CsVoiceAdministrator</p></td>
<td><p>Permet de créer, configurer et gérer les stratégies et les paramètres liés à la voix.</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="odd">
<td><p>CsServerAdministrator</p></td>
<td><p>Permet de gérer et de surveiller les serveurs et les services, d’identifier leurs problèmes et de les résoudre. Permet d’empêcher de nouvelles connexions aux serveurs, d’arrêter et de démarrer des services et d’appliquer des mises à jour logicielles. Ne permet pas d’effectuer des modifications ayant un impact de configuration global.</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>Server Management</p></td>
</tr>
<tr class="even">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>Permet de visualiser le déploiement, notamment les informations d’utilisateur et de serveur afin de surveiller l’état du déploiement.</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>View-Only Organization Management</p></td>
</tr>
<tr class="odd">
<td><p>CsHelpDesk</p></td>
<td><p>Permet d’afficher le déploiement, notamment les stratégies et les propriétés d’utilisateurs. Permet d’exécuter des tâches d’identification et de résolution des problèmes spécifiques. Ne permet pas de modifier les stratégies et les propriétés d’utilisateurs, la configuration du serveur ou les services.</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>HelpDesk</p></td>
</tr>
<tr class="even">
<td><p>CsArchivingAdministrator</p></td>
<td><p>Permet de modifier les stratégies et la configuration de l’archivage.</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>Retention Management, Legal Hold</p></td>
</tr>
<tr class="odd">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>Permet de gérer la configuration de l’application Response Group dans un site.</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="even">
<td><p>CsLocationAdministrator</p></td>
<td><p>Niveau de droits le plus bas pour la gestion Enhanced 9-1-1 (E9-1-1), dont la création d’identificateurs réseau et d’emplacements E9-1-1, ainsi que leur association entre eux. Ce rôle est toujours affecté avec une étendue globale.</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="odd">
<td><p>CsResponseGroupManager</p></td>
<td><p>Permet de gérer des groupes Response Group spécifiques.</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="even">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>Permet de gérer la fonctionnalité Conversation permanente, ainsi que des salles de conversation permanente.</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>Non applicable</p></td>
</tr>
</tbody>
</table>


Tous les rôles prédéfinis fournis avec Lync Server ont une étendue globale. Pour respecter les pratiques du « privilège minimum », vous ne devez pas affecter d’utilisateurs à des rôles ayant une étendue globale s’ils doivent uniquement administrer un groupe limité de serveurs ou d’utilisateurs. Pour ce faire, vous pouvez créer des rôles basés sur un rôle existant, mais avec une étendue plus limitée.

## Création d’un rôle inclus dans une étendue

Quand vous créez un rôle ayant une étendue limitée (rôle inclus dans une étendue), vous spécifiez l’étendue et le rôle existant sur lequel il est basé, mais aussi le groupe Active Directory auquel le rôle est affecté. Le groupe Active Directory que vous spécifiez doit déjà être créé. L’applet de commande suivante est un exemple de création d’un rôle ayant les privilèges de l’un des rôles d’administrateur prédéfinis, mais dont l’étendue est limitée. Il crée un nouveau rôle appelé `Site01 Server Administrators`. Le rôle a les capacités du rôle CsServerAdministrator prédéfini, mais seulement pour les serveurs situés dans le site Site01. Pour que cette applet de commande fonctionne, le site Site01 doit déjà être défini et un groupe de sécurité universel appelé `Site01 Server Administrators` doit déjà exister.

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

Une fois que cette applet de commande a été exécutée, tous les utilisateurs qui sont membres du groupe `Site01 Server Administrators` disposent des privilèges d’administrateur du serveur pour les serveurs du site Site01. En outre, tous les utilisateurs qui seront par la suite ajoutés à ce groupe de sécurité obtiendront aussi les privilèges liés à ce rôle. Veuillez noter que le rôle et le groupe de sécurité universel auquel il est affecté sont appelés `Site01 Server Administrators`.

L’exemple suivant limite l’étendue d’utilisateur au lieu de l’étendue du serveur. Il crée un rôle `Sales Users Administrator` permettant d’administrer les comptes d’utilisateurs dans l’unité d’organisation Sales (Ventes). Le groupe de sécurité universel SalesUsersAdministrator doit déjà être créé pour que cette applet de commande fonctionne.

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

## Création d’un rôle

Pour créer un rôle ayant accès à un ensemble d’applets de commande non inclus dans l’un des rôles prédéfinis, ou à un ensemble de scripts ou de modules, vous devez encore une fois commencer par utiliser l’un des rôles prédéfinis comme modèle. Notez que les scripts et les modules que les rôles sont tenus d’exécuter doivent être stockés aux emplacements suivants :

  - Chemin d’accès au module Lync (par défaut : C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync)

  - Chemin d’accès au script utilisateur (par défaut : C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts)

Pour créer un rôle, vous devez utiliser l’applet de commande **New-CsAdminRole**. Avant d’exécuter **New-CsAdminRole** , vous devez d’abord créer le groupe de sécurité universel sous-jacent qui sera associé à ce rôle.

Les applets de commande suivantes servent d’exemple pour la création d’un rôle. Elles créent un type de rôle appelé `MyHelpDeskScriptRole`. Ce nouveau rôle offre les mêmes capacités que le rôle prédéfini CsHelpDesk avec en outre la possibilité d’exécuter les fonctions d’un script nommé « testscript ».

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

Pour que cette applet de commande fonctionne, vous devez d’abord avoir créé le groupe de sécurité universel MyHelpDeskScriptRole.

Après avoir exécuté cette applet de commande, vous pouvez directement affecter des utilisateurs à ce rôle (dans ce cas, ils ont une étendue globale) ou créer un rôle inclus dans une étendue basé sur ce rôle, comme expliqué dans Création d’un rôle inclus dans une étendue, plus haut dans ce document.

## Affectation de rôles aux utilisateurs

Chaque rôle Lync Server est associé à un groupe de sécurité universel Active Directory sous-jacent. Tous les utilisateurs que vous ajoutez au groupe sous-jacent héritent des capacités de ce rôle.

Les exemples des sections précédentes ont tous deux créé un nouveau rôle et lui ont affecté un groupe de sécurité universel existant. Pour affecter un rôle existant à un ou plusieurs utilisateurs, ajoutez ces utilisateurs au groupe associé au rôle. Vous pouvez ajouter des utilisateurs individuels et des groupes de sécurité universels à ces groupes.

Par exemple, le rôle **CsAdministrator** est automatiquement attribué au groupe de sécurité universel **CS Administrators** dans Active Directory. Ce groupe de sécurité universel est créé dans Active Directory au moment où vous déployez Lync Server. Pour accorder ce privilège à un utilisateur ou à un groupe, vous pouvez simplement l’ajouter au groupe **CS Administrators** .

Un utilisateur peut se voir affecter plusieurs rôles RBAC en étant ajouté aux groupes Active Directory sous-jacents qui correspondent à chaque rôle.

Veuillez noter que lorsque vous créez un rôle, les utilisateurs qui sont par la suite ajoutés au groupe Active Directory sous-jacent sont dotés des capacités de ce rôle

## Modification des capacités d’un rôle

Vous pouvez modifier la liste des applets de commande et des scripts qu’un rôle peut exécuter. Dans le cas des rôles personnalisés, vous pouvez modifier à la fois les applets de commande et les scripts. Dans le cas des rôles prédéfinis, vous pouvez modifier uniquement les scripts. Chaque applet de commande que vous tapez peut ajouter, supprimer ou remplacer des applets de commande ou des scripts.

Pour modifier un rôle, utilisez l’applet de commande **Set-CsAdminRole** . L’applet de commande suivante supprime un script du rôle.

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

## Planification pour RBAC

Pour chaque personne qui se voit attribuer des droits d’administration de tout type pour votre déploiement Lync Server, définissez exactement les tâches qu’elle doit effectuer, puis affectez-la à des rôles lui permettant de mener à bien ses tâches, mais qui offrent le minimum d’étendue et de privilèges. Si nécessaire, vous pouvez utiliser l’applet de commande **Set-CsAdminRole** pour créer un rôle associée aux seules applets de commande nécessaires à l’exécution des tâches de cette personne.

Les utilisateurs qui disposent du rôle CsAdministrator peuvent créer tous les types de rôles, dont les rôles basés sur CsAdministrator, et leur affecter des utilisateurs. La meilleure pratique consiste à affecter le rôle CsAdministrator à un très petit groupe d’utilisateurs approuvés.

