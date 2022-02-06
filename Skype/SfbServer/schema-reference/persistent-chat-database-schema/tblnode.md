---
title: tblNode
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode contient l’arborescence d’objets (avec les nodes de catégorie ou de salle de conversation) telle qu’elle est gérée dans le panneau de contrôle et les cmdlets d’administration.
---

# <a name="tblnode"></a>tblNode
 
tblNode contient l’arborescence d’objets (avec les nodes de catégorie ou de salle de conversation) telle qu’elle est gérée dans le panneau de contrôle et les cmdlets d’administration.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, non null  <br/> |ID de nœud (numéro unique).  <br/> |
|nodeGuid  <br/> |GUID, non null  <br/> |GUID de nœud.  <br/> |
|parentID  <br/> |int  <br/> |ID de nœud du parent. Le nœud racine (avec l’ID 1) s’inclut lui-même comme parent.  <br/> |
|nodeType  <br/> |bit, non null  <br/> |True si le nœud est une catégorie.  <br/> False si le nœud est une salle de conversation.  <br/> |
|nodeName  <br/> |nvarchar (256), non null  <br/> |Nom du nœud.  <br/> |
|nodeDesc  <br/> |nvarchar (256), non null  <br/> |Description du nœud.  <br/> |
|invite  <br/> |bit  <br/> | Pour les catégories : <br/>  True si les invitations sont activées. <br/>  False si les invitations sont désactivées. <br/>  Pour les salles : <br/>  False si les invitations sont désactivées (remplace la catégorie parente). <br/>  Null si le paramètre d’invitation est hérité de la catégorie parente. <br/> |
|journalisé  <br/> |bit  <br/> | Pour les catégories : <br/>  True si l’historique des conversations est activé. <br/>  False si l’historique des conversations est désactivé. <br/>  Pour les salles : <br/>  Null. <br/> |
|filePost  <br/> |bit  <br/> | Pour les catégories : <br/>  True si les téléchargements de fichiers sont autorisés. <br/>  False si les téléchargements de fichiers sont interdits. <br/>  Pour les salles : <br/>  Null. <br/> |
|désactivé  <br/> |bit, non null  <br/> |True si la salle de conversation est désactivée. S’applique uniquement aux salles de conversation. (False pour les catégories.)  <br/> |
|comportement  <br/> |smallint, non null  <br/> | Comportement (tiré de la table EnumValue) : <br/>  4 : normal (salles de conversation normales). <br/>  5 : auditorium (salles de conversation de type auditorium, seuls les présentateurs peuvent contribuer). <br/>  S’applique uniquement aux salles de conversation. <br/> |
|visibility  <br/> |smallint, non null  <br/> | Visibilité (tirée de la table EnumValue) : <br/>  2 : privée <br/>  3 : limitée par une étendue <br/>  6 : ouvert <br/>  S’applique uniquement aux salles de conversation. <br/> |
|siopID  <br/> |GUID  <br/> |GUID de complément si un complément est associé à cette salle de conversation. (Les catégories n’ont pas de complément.)  <br/> Les informations relatives aux compléments sont recherchées dans la table SiopWhiteList.  <br/> |
|nodeAddedBy  <br/> |int, non null  <br/> |ID du principal ayant créé ce nœud.  <br/> |
|nodeAddedOn  <br/> |bigint, non null  <br/> |Horodatage de la création de nœud.  <br/> |
|nodeUpdatedBy  <br/> |int, non null  <br/> |ID du principal ayant effectué la dernière mise à jour de ce nœud.  <br/> |
|nodeUpdatedOn  <br/> |bigint, non null  <br/> |Horodatage de la dernière mise à jour de ce nœud.  <br/> |
|purgedOn  <br/> |DateHeure  <br/> |Heure de la dernière opération de vidage (suppression des étendues de la table tblScopedPrincipal et des rôles de la table tblPrincipalRole) ayant affecté ce nœud. Il est utilisé par le mécanisme de mise à jour du cache interne du service de conversation.  <br/> |
   
**Keys**

|**Colonne**|**Description**|
|:-----|:-----|
|nodeID  <br/> |Clé primaire.  <br/> |
|comportement  <br/> |Clé étrangère avec recherche dans la table tblEnumValue.valueID.  <br/> |
|visibility  <br/> |Clé étrangère avec recherche dans la table tblEnumValue.valueID.  <br/> |
|parentID  <br/> |Clé étrangère avec recherche dans la table tblNode.nodeID.  <br/> |
|siopID  <br/> |Clé étrangère avec recherche dans la table tblSiopWhiteList.siopId.  <br/> |
   

