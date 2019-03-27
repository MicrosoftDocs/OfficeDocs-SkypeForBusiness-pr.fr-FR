---
title: Liste des tables de serveur de conversation permanente
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: Le schéma de base de données de conversation permanente comprend les tables suivantes.
ms.openlocfilehash: e2ce24bb37c3ea4eaee0986f0243033ab4a8a18a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898542"
---
# <a name="list-of-persistent-chat-server-tables"></a>Liste des tables de serveur de conversation permanente
 
Le schéma de base de données de conversation permanente comprend les tables suivantes.
  
## <a name="active-directory-sync"></a>Synchronisation Active Directory

|**Table**|**Description**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |Contient les cookies de synchronisation Lightweight Directory Access Protocol (LDAP). Chaque ligne correspond à un domaine Active Directory Domain Services qui Persistent Chat Server surveillez les modifications. (Uniquement les domaines Active Directory qui sont pertinents pour le serveur de conversation permanente sont représentées dans ce tableau).  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Contient le groupe d’appartenance modifications (à la fois membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes ultérieures de la synchronisation Active Directory et qui est une des tables temporaires (avec tblADUpdates table) qui est utilisé dans la première étape de la synchronisation Active Directory.  <br/> Modifications d’appartenance sont stockées, traitées ou les deux, uniquement pour les groupes qui sont déjà répertoriés dans la table tblPrincipal ou qui ont des membres répertoriés.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Contient les modifications apportées aux Services de domaine Active Directory qui n’ont pas encore été traitées par les étapes ultérieures de la synchronisation Active Directory et est une des tables temporaires (avec la table tblPrincipalMemberDifference) qui est utilisé dans la première étape d’Active Directory Synchronisation.  <br/> Modifications apportées à Active Directory sont stockées, traitées ou les deux, uniquement pour les principaux qui est déjà répertoriés dans la table tblPrincipal.  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |Contient les appartenances des principaux.  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Contient les principaux qui doivent être actualisés à partir d’Active Directory.  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |Contient les affiliations qui n’a pas peuvent être actualisées pour une raison quelconque, généralement les erreurs d’accès Active Directory.  <br/> Ce tableau est uniquement à titre indicatif. Son contenu n’est pas utilisée.  <br/> Les principaux avec affiliations pas peuvent être correctement actualisées sont conservés dans la table tblPrincipalMeta et disposent d’être actualisés.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Principaux, Affiliations, nœuds, étendues et rôles

|**Table**|**Description**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |Contient les types principaux pour classer les nouveautés dans la table tblPrincipal. Ce tableau est statique. Il est configuré lors de la création de la base de données et ne change pas.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |Contient tous les principaux (utilisateurs, des dossiers, groupes et ainsi de suite). Serveur de conversation permanente gère cette valeur sous forme de liste plat hétérogène. Différentes colonnes sont basés sur le type de chaque entité de sécurité.  <br/> La plupart de ces entités sont des copies mises en cache d’objets stockés dans Active Directory. Création de la copie en cache dans l’entité de table de ces objets Active Directory est appelé mise en service.  <br/> Certains principaux sont créés de manière plus énergique que d’autres et certains objets Active Directory sont complètement ignorés.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Contient les affiliations principales qui décrivent l’appartenance dans les groupes de sécurité Active Directory, les conteneurs Active Directory et ainsi de suite.  <br/> |
|[tblNode](tblnode.md) <br/> |Contient le nœud de catégorie comme géré dans le panneau de configuration.  <br/> |
|[tblRoleType](tblroletype.md) <br/> |Contient les types de rôles et leurs autorisations jeux. Cette table de choix est statique.  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |Contient les étendues affectées aux nœuds.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |Contient les rôles affectés à des nœuds.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |Contient les compléments inscrits qui peuvent être associés à des nœuds.  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |Contient uniquement les attributs codés en dur « Visibilité » et « Comportement » sont utilisés dans la table tblNode.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |Contient les valeurs des attributs « Visibilité » et « Comportement » codés en dur utilisés dans la table tblNode.  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>Invitations, conversations et autres prise en charge du Client

|**Table**|**Description**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |Contient des invitations pour tous les utilisateurs configurés dans le système pour tous les nœuds avec l’invitation automatique activée.  <br/> |
|[tblChat](tblchat.md) <br/> |Contient tous les messages de conversation.  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |Contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |Contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.  <br/> |
|[tblPreference](tblpreference.md) <br/> |Contient les préférences du client utilisateur (utilisés par les clients hérités uniquement).  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |Contient des jetons temporaires pour le transfert de fichiers. Chaque fois qu’un fichier est téléchargé ou téléchargé, le service de conversation permanente génère un jeton que le client utilise pour accéder au magasin de fichiers du service Web.  <br/> |
   
## <a name="server-support"></a>Prise en charge du serveur

|**Table**|**Description**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |Contient les serveurs actifs du pool de serveurs de conversation permanente.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |Contient le verrou d’administrateur pour exécuter certaines commandes d’administration. L’entrée de révision dans la table Systemrevision système est incrémentée après chaque version du verrou.  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |Contient l’entrée du numéro de révision utilisée (avec la table tblAdminLock) pour harmoniser plusieurs serveurs.  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |Contient des connexions d’égal à égal actuelles entre les services de conversation permanente.  <br/> |
|[tblConfig](tblconfig.md) <br/> |Contient la configuration non prise en charge du serveur de conversation permanente.  <br/> |
   

