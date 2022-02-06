---
title: Exemples de requêtes de base de données de conversation permanente
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: Cette section contient des exemples de requêtes pour la base de données de conversation permanente.
---

# <a name="sample-persistent-chat-database-queries"></a>Exemples de requêtes de base de données de conversation permanente
 
Cette section contient des exemples de requêtes pour la base de données de conversation permanente.
  
Utilisez l’exemple suivant pour obtenir la liste de vos salles de conversation permanente les plus actives après une date précise.
  
```SQL
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

Utilisez l’exemple suivant pour obtenir la liste de vos utilisateurs les plus actifs après une date précise.
  
```SQL
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

Utilisez l’exemple suivant pour obtenir la liste de toutes les personnes qui ont envoyé un message avec « Hello World ».
  
```SQL
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

Utilisez l’exemple suivant pour obtenir la liste des appartenances à un groupe pour un certain principal.
  
```SQL
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

Utilisez l’exemple suivant pour obtenir la liste de chaque salle de conversation dont une utilisateur, Jane Dow, est un membre direct.
  
```SQL
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

Utilisez l’exemple suivant pour obtenir la liste des invitations reçues par un utilisateur.
  
```SQL
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
