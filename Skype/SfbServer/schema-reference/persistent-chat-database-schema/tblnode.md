---
title: tblNode
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode contient l’arborescence d’objets (avec les nœuds de catégorie ou de la salle de conversation) comme géré dans le panneau de commande et des applets de commande d’administration.
ms.openlocfilehash: b743453225fda70db18a7bc616a5f7b647d5ebff
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblnode"></a>tblNode
 
tblNode contient l’arborescence d’objets (avec les nœuds de catégorie ou de la salle de conversation) comme géré dans le panneau de commande et des applets de commande d’administration.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, non null  <br/> |ID de nœud (numéro unique).  <br/> |
|nodeGuid  <br/> |GUID, pas null  <br/> |Nœud GUID.  <br/> |
|parentID  <br/> |int  <br/> |ID du nœud parent. Le nœud racine (avec l’ID 1) inclut lui-même en tant que parent ainsi.  <br/> |
|nodeType  <br/> |bits, non null  <br/> |True si le nœud est une catégorie.  <br/> False si le nœud est une salle de conversation.  <br/> |
|Nom_nœud  <br/> |nvarchar (256), non null  <br/> |Nom du nœud.  <br/> |
|nodeDesc  <br/> |nvarchar (256), non null  <br/> |Description du nœud.  <br/> |
|inviter  <br/> |bit  <br/> | Pour les catégories : <br/>  True si les invitations sont sur. <br/>  False si les invitations sont désactivés. <br/>  Pour les salles : <br/>  False si les invitations sont désactivés (remplace la catégorie parente). <br/>  Null si les invitations définition est hérité à partir de la catégorie parente. <br/> |
|connecté  <br/> |bit  <br/> | Pour les catégories : <br/>  True si l’historique de conversation. <br/>  False si l’historique de conversation est désactivée. <br/>  Pour les salles : <br/>  Valeur null. <br/> |
|filePost  <br/> |bit  <br/> | Pour les catégories : <br/>  True si les téléchargements de fichiers sont autorisés. <br/>  False si les téléchargements de fichiers ne sont pas autorisées. <br/>  Pour les salles : <br/>  Valeur null. <br/> |
|désactivé  <br/> |bits, non null  <br/> |True si la salle de conversation est désactivée. S’applique uniquement aux salles de conversation. (False pour les catégories).  <br/> |
|||
|comportement  <br/> |smallint, non null  <br/> | Comportement (recherché dans la table de EnumValue) : <br/>  4 : Normal (salles de conversation normales). <br/>  5 : auditorium (salles de conversation auditorium, uniquement les présentateurs peuvent contribuer). <br/>  S’applique uniquement aux salles de conversation. <br/> |
|visibilité  <br/> |smallint, non null  <br/> | Visibilité (recherchée sur EnumValue table) : <br/>  2 : privé <br/>  3 : portée <br/>  6 : ouverture <br/>  S’applique uniquement aux salles de conversation. <br/> |
|siopID  <br/> |GUID  <br/> |Complément GUID si un complément est associé à cette salle de conversation. (Catégories n’ont pas de modules complémentaires).  <br/> Les informations de complément sont recherchées dans le tableau de SiopWhiteList.  <br/> |
|nodeAddedBy  <br/> |int, non null  <br/> |ID de l’entité de sécurité qui a créé ce nœud.  <br/> |
|nodeAddedOn  <br/> |bigint, non null  <br/> |Horodatage de la création du nœud.  <br/> |
|nodeUpdatedBy  <br/> |int, non null  <br/> |ID de l’entité de sécurité qui ont fait de la dernière mise à jour de ce nœud.  <br/> |
|nodeUpdatedOn  <br/> |bigint, non null  <br/> |Horodatage de la dernière mise à jour de ce nœud.  <br/> |
|purgedOn  <br/> |DateHeure  <br/> |Heure de la dernière purge opération (suppression des étendues à partir de la table de tblScopedPrincipal et des rôles à partir de la table de tblPrincipalRole) affectés de ce nœud. Il est utilisé par le mécanisme de mise à jour du cache interne du service Chat.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|nodeID  <br/> |Clé primaire.  <br/> |
|comportement  <br/> |Clé étrangère avec la recherche dans la table de tblEnumValue.valueID.  <br/> |
|visibilité  <br/> |Clé étrangère avec la recherche dans la table de tblEnumValue.valueID.  <br/> |
|parentID  <br/> |Clé étrangère avec la recherche dans la table de tblNode.nodeID.  <br/> |
|siopID  <br/> |Clé étrangère avec la recherche dans la table de tblSiopWhiteList.siopId.  <br/> |
   

