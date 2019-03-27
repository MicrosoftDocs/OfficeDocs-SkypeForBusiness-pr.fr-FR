---
title: tblNode
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode contient l’arborescence d’objets (avec les nœuds de catégorie ou salle de conversation) comme géré dans le panneau de configuration et les applets de commande d’administration.
ms.openlocfilehash: c5028b138711b6f57c0e947ea41572fd9984b3fb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878892"
---
# <a name="tblnode"></a>tblNode
 
tblNode contient l’arborescence d’objets (avec les nœuds de catégorie ou salle de conversation) comme géré dans le panneau de configuration et les applets de commande d’administration.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, non null  <br/> |ID de nœud (numéro unique).  <br/> |
|nodeGuid  <br/> |GUID, non null  <br/> |GUID de nœud.  <br/> |
|parentID  <br/> |int  <br/> |ID du nœud parent. Le nœud racine (avec l’ID 1) inclut lui-même comme ainsi que le parent.  <br/> |
|nodeType  <br/> |bit, non null  <br/> |True si le nœud est une catégorie.  <br/> False si le nœud est une salle de conversation.  <br/> |
|Nom_nœud  <br/> |nvarchar (256), non null  <br/> |Nom du nœud.  <br/> |
|nodeDesc  <br/> |nvarchar (256), non null  <br/> |Description du nœud.  <br/> |
|inviter  <br/> |bit  <br/> | Pour les catégories : <br/>  True si les invitations sont activées. <br/>  False si les invitations sont désactivées. <br/>  Pour les salles : <br/>  False si les invitations sont désactivées (remplace la catégorie parente). <br/>  Null si le paramètre d’invitation est hérité de la catégorie parente. <br/> |
|connecté  <br/> |bit  <br/> | Pour les catégories : <br/>  True si l’historique des conversations. <br/>  False si l’historique des conversations sont désactivé. <br/>  Pour les salles : <br/>  NULL. <br/> |
|filePost  <br/> |bit  <br/> | Pour les catégories : <br/>  True si les téléchargements de fichiers sont autorisées. <br/>  False si les téléchargements de fichiers sont interdits. <br/>  Pour les salles : <br/>  NULL. <br/> |
|désactivé  <br/> |bit, non null  <br/> |True si la salle de conversation est désactivée. S’applique uniquement aux salles de conversation. (False pour les catégories).  <br/> |
|comportement  <br/> |smallint, non null  <br/> | Comportement (table EnumValue) : <br/>  4 : Normal (salles de conversation normales). <br/>  5 : auditorium (salles de conversation de type auditorium, seuls les présentateurs peuvent contribuer). <br/>  S’applique uniquement aux salles de conversation. <br/> |
|visibilité  <br/> |smallint, non null  <br/> | Visibilité (recherchée dans la table EnumValue) : <br/>  2 : privé <br/>  3 : étendue <br/>  6 : ouvrir <br/>  S’applique uniquement aux salles de conversation. <br/> |
|siopID  <br/> |GUID  <br/> |Complément GUID si un complément est associé à cette salle de conversation. (Catégories n’ont pas de compléments).  <br/> Les informations sont recherchées dans la table SiopWhiteList.  <br/> |
|nodeAddedBy  <br/> |int, non null  <br/> |ID du principal ayant créé ce nœud.  <br/> |
|nodeAddedOn  <br/> |bigint, non null  <br/> |Horodatage de la création de nœud.  <br/> |
|nodeUpdatedBy  <br/> |int, non null  <br/> |ID du principal ayant effectué la dernière mise à jour de ce nœud.  <br/> |
|nodeUpdatedOn  <br/> |bigint, non null  <br/> |Horodatage de la dernière mise à jour de ce nœud.  <br/> |
|purgedOn  <br/> |DateHeure  <br/> |Heure de l’opération de vider le plus récent (suppression des étendues à partir de la table tblScopedPrincipal et des rôles à partir de la table tblPrincipalRole table) qui ont affecté ce nœud. Il est utilisé par le mécanisme de mise à jour du cache interne du service de conversation.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|nodeID  <br/> |Clé primaire.  <br/> |
|comportement  <br/> |Clé étrangère avec recherche dans la table tblEnumValue.valueID.  <br/> |
|visibilité  <br/> |Clé étrangère avec recherche dans la table tblEnumValue.valueID.  <br/> |
|parentID  <br/> |Clé étrangère avec recherche dans la table tblNode.nodeID.  <br/> |
|siopID  <br/> |Clé étrangère avec recherche dans la table tblSiopWhiteList.siopId.  <br/> |
   

