---
title: Liste des tables de serveur de conversation permanente
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: Le schéma de base de données de conversation permanent est constitué par les tableaux suivants.
ms.openlocfilehash: d9a00095cb18e63cc29e16ae66e608127afad606
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-persistent-chat-server-tables"></a>Liste des tables de serveur de conversation permanente
 
Le schéma de base de données de conversation permanent est constitué par les tableaux suivants.
  
## <a name="active-directory-sync"></a>Synchronisation Active Directory

|**Table**|**Description**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |Contient les cookies en cours de la synchronisation de Lightweight Directory Access Protocol (LDAP). Chaque ligne correspond à un domaine Active Directory Domain Services serveur de Chat persistant est surveiller activement les modifications. (Uniquement les domaines Active Directory qui sont pertinents pour le serveur de conversation persistant sont représentées dans ce tableau.)  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Contient le groupe d’appartenance modifications (ajout et suppression de membres) qui n’ont pas encore été traitées par les étapes ultérieures de la synchronisation Active Directory et qui sont une des tables temporaires (avec table de tblADUpdates) qui est utilisé dans la première étape de la synchronisation Active Directory.  <br/> Modifications d’appartenance sont stockées, traitées, ou les deux, uniquement pour les groupes qui sont répertoriés dans la table tblPrincipal ou déjà ont des membres dans la liste.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Contient les modifications apportées aux Services de domaine Active Directory qui n’ont pas encore été traitée par les étapes ultérieures de la synchronisation Active Directory et est une des tables temporaires (avec le tableau tblPrincipalMemberDifference) qui est utilisé dans la première étape d’Active Directory Synchronisation.  <br/> Les modifications apportées à Active Directory sont stockées, traitées, ou les deux, uniquement pour les entités de sécurité qui figurent déjà dans la table tblPrincipal.  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |Contient des membres principaux.  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Contient les identités qui doivent être actualisés à partir d’Active Directory.  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |Contient les affiliations qui ne peuvent pas être actualisées pour une raison quelconque, généralement en raison d’erreurs d’accès Active Directory.  <br/> Cette table est uniquement à titre indicatif. Son contenu n’est pas utilisé.  <br/> Les identités avec les affiliations qui ne peuvent pas être actualisées correctement sont conservées dans la table tblPrincipalMeta et figurent encore une chance d’être actualisé.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Entités, les Affiliations, les nœuds, les étendues et les rôles

|**Table**|**Description**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |Contient les types principaux pour classer les nouveautés dans la table tblPrincipal. Cette table est statique. Il est défini lors de la création de la base de données et ne change pas.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |Contient toutes les entités de sécurité (utilisateurs, dossiers, groupes et ainsi de suite). Serveur de Chat persistant gère cette valeur sous forme de liste plate hétérogène. Plusieurs colonnes sont basés sur le type de chaque entité de sécurité.  <br/> La plupart de ces entités sont des copies mises en cache des objets stockés dans Active Directory. Création de la copie mise en cache dans l’entité de table de ces objets de Active Directory est appelé mise en service.  <br/> Certaines entités sont créées d’une manière plus agressive que d’autres, et certains objets Active Directory sont complètement ignorés.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Contient des affiliations principales qui décrivent les appartenances à des groupes de sécurité Active Directory, les conteneurs Active Directory et ainsi de suite.  <br/> |
|[tblNode](tblnode.md) <br/> |Contient le nœud de catégorie, comme géré dans le panneau de configuration.  <br/> |
|[tblRoleType](tblroletype.md) <br/> |Contient les types de rôles et leurs autorisations jeux. Cette table de choix est statique.  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |Contient les étendues affectées aux nœuds.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |Contient les rôles assignés à des nœuds.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |Contient les compléments enregistrés qui peuvent être associées à des nœuds.  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |Contient uniquement les codé en dur « Visibilité » et « Comportement » attributs qui sont utilisés dans la table tblNode.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |Contient les valeurs codées en dur « Visibilité » et « Comportement » attributs qui sont utilisés dans la table tblNode.  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>La prise en charge d’autre clients, les conversations et les invitations

|**Table**|**Description**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |Contient des invitations pour tous les utilisateurs mis en service dans le système pour tous les nœuds avec Auto inviter activé.  <br/> |
|[tblChat](tblchat.md) <br/> |Contient tous les messages de conversation.  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |Contient le dernier ID d’invitation qui a été généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |Contient le dernier ID de conversation qui a été généré (et utilisé dans la table tblChat) pour chaque utilisateur.  <br/> |
|[tblPreference](tblpreference.md) <br/> |Contient les préférences de l’utilisateur client (utilisés par les clients hérités uniquement).  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |Contient des jetons temporaires à des fins de transfert de fichier. Chaque fois qu’un fichier est téléchargé ou transférée, le service Chat persistant génère un jeton que le client utilise pour accéder au magasin de fichiers du service Web.  <br/> |
   
## <a name="server-support"></a>Prise en charge du serveur

|**Table**|**Description**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |Contient les serveurs actifs dans le pool de serveur de conversation persistant.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |Contient le verrou d’administrateur pour exécuter certaines commandes de l’administrateur. L’entrée système de révision dans la table tblSystemRevision est incrémentée après chaque libération du verrou.  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |Contient le numéro de la révision utilisé (avec le tableau tblAdminLock) pour garantir la cohérence entre plusieurs serveurs.  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |Contient des connexions de pair à pair en cours entre les services de conversation permanent.  <br/> |
|[tblConfig](tblconfig.md) <br/> |Contient la configuration non prise en charge serveur de Chat persistant.  <br/> |
   

