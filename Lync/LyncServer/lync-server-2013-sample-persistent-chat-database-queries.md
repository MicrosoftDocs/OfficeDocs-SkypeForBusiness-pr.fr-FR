---
title: "Lync Server 2013 : Ex. de requêtes de BD de conversation permanente"
TOCTitle: Exemples de requêtes de base de données de conversation permanente
ms:assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558649(v=OCS.15)
ms:contentKeyID: 49297219
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exemples de requêtes de base de données de conversation permanente pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-06_

Cette section contient des exemples de requêtes pour la base de données de conversation permanente.

Utilisez l’exemple suivant pour obtenir une liste de vos salles de conversation permanente les plus actives après une certaine date.

    SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
      FROM tblChat, tblNode
      WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY nodeName
      ORDER BY ChatMessages DESC

Utilisez l’exemple suivant pour obtenir une liste de vos utilisateurs les plus actifs après une certaine date.

    SELECT prinName as Name, count(*) as ChatMessages
      FROM tblChat, tblPrincipal
      WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY prinName
      ORDER BY ChatMessages DESC

Utilisez l’exemple suivant pour obtenir une liste des personnes qui vous ont envoyé un message contenant le message « Hello World ».

    SELECT nodeName as ChatRoom, prinName as Name, content as Message
      FROM tblChat, tblNode, tblPrincipal
      WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'

Utilisez l’exemple suivant pour obtenir une liste d’adhérents de groupe pour un certain principal.

    SELECT prinName as Name    
      FROM tblPrincipalAffiliations as pa, tblPrincipal
      where principalID = 7 and affiliationID = prinID

Utilisez l’exemple suivant pour obtenir une liste de toutes les salles de conversation dont une utilisatrice, Jane Dow, est une membre directe.

    SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
      FROM tblPrincipalRole, tblPrincipal, tblNode
      WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'

Utilisez l’exemple suivant pour obtenir une liste d’invitations qu’un utilisateur a reçues.

    SELECT prinName
          ,nodeName
          ,invID   
          ,createdOn
      FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
      where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
      ORDER BY invID DESC

