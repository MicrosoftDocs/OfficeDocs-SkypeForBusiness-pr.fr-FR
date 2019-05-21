---
title: Liste des tables de serveur de conversation permanente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: Le schéma de base de données de chat permanent se compose des tables suivantes.
ms.openlocfilehash: 6a6c0bc2c2cc2d5e5ba59f9f636ed9cea2189bed
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295649"
---
# <a name="list-of-persistent-chat-server-tables"></a>Liste des tables de serveur de conversation permanente
 
Le schéma de base de données de chat permanent se compose des tables suivantes.
  
## <a name="active-directory-sync"></a>Synchronisation Active Directory

|**Table**|**Description**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |Contient les cookies de synchronisation LDAP (Lightweight Directory Access Protocol) actuels. Chaque ligne correspond à un domaine AD FS (Active Directory Domain Services), qui permet de surveiller activement le serveur de chat permanent. (Seuls les domaines Active Directory pertinents pour le serveur Chat permanent sont représentés dans ce tableau.)  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Contient des modifications d’appartenance au groupe (à la fois ajoutées et supprimées) qui n’ont pas encore été traitées par les étapes ultérieures de synchronisation Active Directory et qui est utilisée lors de la première étape de la synchronisation Active Directory.  <br/> Les modifications d’appartenance sont stockées, traitées, ou les deux, uniquement pour les groupes qui sont répertoriés dans la table tblPrincipal ou qui ont déjà des membres dans la liste.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Contient des modifications apportées aux services de domaine Active Directory (AD DS) qui n’ont pas encore été traitées par les étapes ultérieures de synchronisation Active Directory et qui est utilisée lors de la première étape d’Active Directory. Synchronisation.  <br/> Les modifications apportées à Active Directory sont stockées, traitées, ou les deux, uniquement pour les principaux figurant déjà dans la table tblPrincipal.  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |Contient des appartenances principales.  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Contient les principaux qui doivent être actualisés à partir d’Active Directory.  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |Contient des affiliations qui n’ont pas pu être actualisées pour une raison quelconque, généralement en raison d’erreurs d’accès à Active Directory.  <br/> Ce tableau est à des fins d’information uniquement. Son contenu n’est pas utilisé.  <br/> Les principaux dotés d’affiliations qui n’ont pas pu être actualisés correctement sont conservés dans la table tblPrincipalMeta et ont une nouvelle chance d’être actualisées.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Principaux, affiliations, nœuds, étendues et rôles

|**Table**|**Description**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |Contient des types de principaux pour classer ce qui se trouve dans la table tblPrincipal. Ce tableau est statique. Elle est configurée lors de la création de la base de données et n’est pas modifiée.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |Contient tous les principaux (utilisateurs, dossiers, groupes, etc.). Le serveur de chat permanent gère ce point comme une liste hétérogène plate. Différentes colonnes sont basées sur le type de chaque principal.  <br/> La plupart de ces éléments principaux sont des copies mises en cache d’objets stockés dans Active Directory. La création de la copie mise en cache dans la table principale de ces objets Active Directory est appelée mise en service.  <br/> Certains éléments principaux sont créés de manière plus agressive que d’autres, et certains objets Active Directory sont entièrement ignorés.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Contient des affiliations principales qui décrivent les appartenances aux groupes de sécurité Active Directory, aux conteneurs Active Directory, etc.  <br/> |
|[tblNode](tblnode.md) <br/> |Contient le nœud Category, tel qu’il est géré dans le panneau de configuration.  <br/> |
|[tblRoleType](tblroletype.md) <br/> |Contient des types de rôles et leurs jeux d’autorisations associés. Cette table de choix est statique.  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |Contient les étendues attribuées aux nœuds.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |Contient les rôles attribués aux nœuds.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |Contient les compléments enregistrés qui peuvent être associés à des nœuds.  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |Contient uniquement les attributs «Visibility» et «Behavior» en dur qui sont utilisés dans la table tblNode.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |Contient les valeurs des attributs de «visibilité» et de «comportement» en dur qui sont utilisés dans la table tblNode.  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>Invitations, discussions et autres clients pris en charge

|**Table**|**Description**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |Contient des invitations pour tous les utilisateurs approvisionnés du système pour tous les nœuds avec l’option d’invitation automatique activée.  <br/> |
|[tblChat](tblchat.md) <br/> |Contient tous les messages de discussion.  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |Contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |Contient le dernier ID de chat qui a été généré (et utilisé dans la table tblChat) pour chaque utilisateur.  <br/> |
|[tblPreference](tblpreference.md) <br/> |Contient les préférences client de l’utilisateur (utilisé par les clients hérités uniquement).  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |Contient des jetons temporaires aux fins de transfert de fichiers. Chaque fois qu’un fichier est chargé ou téléchargé, le service Chat permanent génère un jeton qu’utilise le client pour accéder au magasin de fichiers du service Web.  <br/> |
   
## <a name="server-support"></a>Prise en charge du serveur

|**Table**|**Description**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |Contient les serveurs actifs dans le pool de serveurs de chat permanent.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |Contient le verrouillage de l’administrateur pour exécuter des commandes d’administrateur. L’entrée de révision système dans la table tblSystemRevision est incrémentée après chaque libération du verrou.  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |Contient l’entrée du numéro de révision utilisée (en même temps que la table tblAdminLock) permettant de réaliser une cohérence entre plusieurs serveurs.  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |Contient des connexions d’égal à égal actuelles entre les services de chat permanents.  <br/> |
|[tblConfig](tblconfig.md) <br/> |Contient la configuration du serveur de chat permanent non prise en charge.  <br/> |
   

