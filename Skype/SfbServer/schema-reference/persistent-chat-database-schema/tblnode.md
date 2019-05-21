---
title: tblNode
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode contient l’arborescence d’objets (avec des nœuds de catégorie ou de salle de conversation) qui est gérée dans les applets de commande du panneau de configuration et d’administration.
ms.openlocfilehash: fedb7f88cd9b5a634fe9a6b34f746e61e6ee9be7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295348"
---
# <a name="tblnode"></a>tblNode
 
tblNode contient l’arborescence d’objets (avec des nœuds de catégorie ou de salle de conversation) qui est gérée dans les applets de commande du panneau de configuration et d’administration.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|ID  <br/> |ent, non null  <br/> |ID de nœud (numéro unique).  <br/> |
|nodeGuid  <br/> |GUID, pas null  <br/> |GUID du nœud.  <br/> |
|Parent  <br/> |int  <br/> |ID de nœud du parent. Le nœud racine (avec l’ID 1) s’intègre également en tant que parent.  <br/> |
|nodeType  <br/> |bit, pas null  <br/> |True si le nœud est une catégorie.  <br/> Faux si le nœud est une salle de conversation.  <br/> |
|nodeName  <br/> |nvarchar (256), pas null  <br/> |Nom du nœud.  <br/> |
|nodeDesc  <br/> |nvarchar (256), pas null  <br/> |Description du nœud.  <br/> |
|inviter  <br/> |bit  <br/> | Pour les catégories: <br/>  True si les invitations sont activées. <br/>  Faux si les invitations sont désdésactivées. <br/>  Pour les salles: <br/>  Faux si les invitations sont désactivées (ignore la catégorie parent). <br/>  NULL si le paramètre d’invitations est hérité de la catégorie parent. <br/> |
|utilisé  <br/> |bit  <br/> | Pour les catégories: <br/>  True si l’historique des conversations est activé. <br/>  Faux si l’historique des conversations est désactivé. <br/>  Pour les salles: <br/>  Valeur. <br/> |
|filePost  <br/> |bit  <br/> | Pour les catégories: <br/>  True si les téléchargements de fichiers sont autorisés. <br/>  False si les téléchargements de fichiers ne le sont pas. <br/>  Pour les salles: <br/>  Valeur. <br/> |
|désactivé  <br/> |bit, pas null  <br/> |True si la salle de conversation est désactivée. S’applique uniquement aux salles de conversation. (Faux pour les catégories.)  <br/> |
|fonctionnement  <br/> |smallint, pas null  <br/> | Comportement (recherché dans la table EnumValue): <br/>  4: normal (salles de conversation normales). <br/>  5: Auditorium (salles de conversation d’Auditorium; seuls les présentateurs peuvent collaborer). <br/>  S’applique uniquement aux salles de conversation. <br/> |
|notoriété  <br/> |smallint, pas null  <br/> | Visibility (recherché sur la table EnumValue): <br/>  2: privé <br/>  3: étendue <br/>  6: ouvrir <br/>  S’applique uniquement aux salles de conversation. <br/> |
|siopID  <br/> |GUID  <br/> |GUID du complément si un complément est associé à cette salle de conversation. (Les catégories n’ont pas de compléments.)  <br/> Les informations de complément sont recherchées dans la table SiopWhiteList.  <br/> |
|nodeAddedBy  <br/> |ent, non null  <br/> |ID de l’élément principal qui a créé ce nœud.  <br/> |
|nodeAddedOn  <br/> |bigint, pas null  <br/> |Horodatage de la création du nœud.  <br/> |
|nodeUpdatedBy  <br/> |ent, non null  <br/> |ID de l’entité de l’utilisateur qui a effectué la dernière mise à jour de ce nœud.  <br/> |
|nodeUpdatedOn  <br/> |bigint, pas null  <br/> |Horodatage de la dernière mise à jour de ce nœud.  <br/> |
|purgedOn  <br/> |DateHeure  <br/> |Heure de la dernière opération de purge (la suppression des étendues de la table tblScopedPrincipal et des rôles de la table tblPrincipalRole) qui ont affecté ce nœud. Ce mode est utilisé par le mécanisme de mise à jour du cache interne du service de conversation.  <br/> |
   
**Permettent**

|**Colonne**|**Description**|
|:-----|:-----|
|ID  <br/> |Clé primaire.  <br/> |
|fonctionnement  <br/> |Clé étrangère avec recherche dans la table tblEnumValue. valueID.  <br/> |
|notoriété  <br/> |Clé étrangère avec recherche dans la table tblEnumValue. valueID.  <br/> |
|Parent  <br/> |Clé étrangère avec recherche dans la table tblNode. nodeID.  <br/> |
|siopID  <br/> |Clé étrangère avec recherche dans la table tblSiopWhiteList. siopId.  <br/> |
   

