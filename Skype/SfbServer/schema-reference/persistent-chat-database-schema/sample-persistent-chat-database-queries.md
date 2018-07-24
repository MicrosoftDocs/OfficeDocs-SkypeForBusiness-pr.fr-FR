---
title: Exemples de requêtes de base de données de conversation permanente
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: Cette section contient des exemples de requêtes pour la base de données de conversation permanente.
ms.openlocfilehash: ab4db61e70108bb922646add050ddcf7f52951b1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21025918"
---
# <a name="sample-persistent-chat-database-queries"></a><span data-ttu-id="86c5e-103">Exemples de requêtes de base de données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="86c5e-103">Sample Persistent Chat database queries</span></span>
 
<span data-ttu-id="86c5e-104">Cette section contient des exemples de requêtes pour la base de données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="86c5e-104">This section contains sample queries for the Persistent Chat database.</span></span>
  
<span data-ttu-id="86c5e-105">L’exemple suivant permet d’obtenir une liste de vos salles de conversation permanente plus actives après une certaine date.</span><span class="sxs-lookup"><span data-stu-id="86c5e-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>
  
```
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="86c5e-106">L’exemple suivant permet d’obtenir une liste de vos utilisateurs les plus actifs après une certaine date.</span><span class="sxs-lookup"><span data-stu-id="86c5e-106">Use the following example to get a list of your most active users after a certain date.</span></span>
  
```
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="86c5e-107">Utilisez l’exemple suivant pour obtenir une liste de toutes les personnes qui vous ont envoyé un message avec « Hello World » de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="86c5e-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>
  
```
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

<span data-ttu-id="86c5e-108">L’exemple suivant permet d’obtenir la liste des appartenances de groupe pour un certain principal.</span><span class="sxs-lookup"><span data-stu-id="86c5e-108">Use the following example to get a list of group memberships for a certain principal.</span></span>
  
```
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

<span data-ttu-id="86c5e-109">L’exemple suivant permet d’obtenir une liste de chaque salle de conversation dont une utilisatrice, Jane Dow, est une membre directe.</span><span class="sxs-lookup"><span data-stu-id="86c5e-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>
  
```
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

<span data-ttu-id="86c5e-110">L’exemple suivant permet d’obtenir une liste d’invitations qu’un utilisateur a reçu.</span><span class="sxs-lookup"><span data-stu-id="86c5e-110">Use the following example to get a list of invitations that a user has received.</span></span>
  
```
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```