---
title: Liste des tables de serveur de conversation permanente
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: Le schéma de base de données de conversation permanente se compose des tableaux suivants.
ms.openlocfilehash: e0586776d13a9e958ba30a84e421e4cba92ba12c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763322"
---
# <a name="list-of-persistent-chat-server-tables"></a>Liste des tables de serveur de conversation permanente
 
Le schéma de base de données de conversation permanente se compose des tableaux suivants.
  
## <a name="active-directory-sync"></a>Synchronisation Active Directory

|**Table**|**Description**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |Contient les cookies de synchronisation LDAP (Lightweight Directory Access Protocol) actifs. Chaque ligne correspond à un domaine des services de domaine Active Directory que le serveur de conversation permanente surveille activement pour les modifications. (Seuls les domaines Active Directory pertinents pour le serveur de conversation permanente sont représentés dans ce tableau.)  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Contient les modifications d’appartenance aux groupes (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes de synchronisation Active Directory ultérieures et qui est l’une des tables temporaires (avec la table tblADUpdates) qui est utilisée lors de la première étape de la synchronisation Active Directory.  <br/> Les modifications d’appartenance sont stockées, traitées ou les deux, uniquement pour les groupes qui sont répertoriés dans la table tblPrincipal ou qui contiennent déjà des membres répertoriés dans cette dernière.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Contient les modifications apportées aux services de domaine Active Directory qui n’ont pas encore été traitées par les étapes de synchronisation Active Directory ultérieures et qui est l’une des tables temporaires (avec la table tblPrincipalMemberDifference) qui est utilisée lors de la première étape de la synchronisation Active Directory.  <br/> Les modifications apportées à Active Directory sont stockées, traitées ou les deux uniquement pour les principaux qui sont déjà répertoriés dans la table tblPrincipal.  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |Contient les appartenances de Principal.  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Contient les principaux qui doivent être actualisé à partir d’Active Directory.  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |Contient des affiliations qui n’ont pas pu être actualisées pour une raison quelconque, généralement en raison d’erreurs d’accès Active Directory.  <br/> Cette table est fournie uniquement à titre indicatif. Son contenu n’est pas utilisé.  <br/> Les principaux avec affiliations qui n’ont pas pu être correctement actualisés sont conservés dans la table tblPrincipalMeta et peuvent de nouveau être actualisés.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Principaux, affiliations, nœuds, étendues et rôles

|**Table**|**Description**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |Contient les types principaux qui permettent de catégoriser le contenu de la table tblPrincipal. Cette table est statique. Elle est configurée lors de la création de la base de données et n’est pas modifiée.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |Contient tous les principaux (utilisateurs, dossiers, groupes, etc.). Le serveur de conversation permanente gère cela comme une liste hétérogène plate. De nombreuses colonnes sont basées sur le type de chaque principal.  <br/> La plupart de ces principaux sont des copies mises en cache d’objets stockés dans Active Directory. La création de la copie mise en cache dans la table Principal de ces objets Active Directory est appelée approvisionnement.  <br/> Certains principaux sont créés de manière plus agressive que d’autres, et certains objets Active Directory sont complètement ignorés.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Contient les affiliations principales qui décrivent les appartenances aux groupes de sécurité Active Directory, aux conteneurs Active Directory, etc.  <br/> |
|[tblNode](tblnode.md) <br/> |Contient le nœud de catégorie, tel qu’il est géré dans le panneau de contrôle.  <br/> |
|[tblRoleType](tblroletype.md) <br/> |Contient des types de rôles et leurs jeux d’autorisations associées. Cette table de consultation est statique.  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |Contient des étendues assignées à des nœuds.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |Contient des rôles assignés à des nœuds.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |Contient les compléments inscrits qui peuvent être associés à des nœuds.  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |Contient uniquement les attributs « Visibilité » et « Comportement » codés en dur utilisés dans la table tblNode.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |Contient les valeurs des attributs codés en dur « Visibility » et « Behavior » utilisés dans la table tblNode.  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>Prises en charge des invitations, des conversations et d’autres clients

|**Table**|**Description**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |Contient les invitations de tous les utilisateurs mis en service dans le système pour tous les nœuds ayant la fonction d’invitation automatique activée.  <br/> |
|[tblChat](tblchat.md) <br/> |Contient tous les messages de conversations.  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |Contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |Contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.  <br/> |
|[tblPreference](tblpreference.md) <br/> |Contient les préférences du client utilisateur (utilisées par les clients hérités uniquement).  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |Contient des jetons temporaires pour le transfert de fichiers. Chaque fois qu’un fichier est téléchargé, le service de conversation permanente génère un jeton que le client utilise pour accéder au magasin de fichiers du service Web.  <br/> |
   
## <a name="server-support"></a>Prise en charge du serveur

|**Table**|**Description**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |Contient les serveurs actifs dans le pool de serveurs de conversation permanente.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |Contient le verrou d’administrateur permettant d’exécuter des commandes d’administrateur. L’entrée de révision du système dans la table tblSystemRevision est incrémentée après chaque libération de verrou.  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |Contient l’entrée du numéro de révision utilisée (avec la table tblAdminLock) pour harmoniser plusieurs serveurs administrateurs.  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |Contient les connexions pair à pair actuelles entre les services de conversation permanente.  <br/> |
|[tblConfig](tblconfig.md) <br/> |Contient la configuration non pris en compte du serveur de conversation permanente.  <br/> |
   

