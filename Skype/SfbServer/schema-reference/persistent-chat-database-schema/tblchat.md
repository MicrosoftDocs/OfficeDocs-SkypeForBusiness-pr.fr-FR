---
title: tblChat
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat contient tous les messages de conversation.
ms.openlocfilehash: 1a1a2986d69e2f5efafe365da3394de01c911623
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblchat"></a>tblChat
 
tblChat contient tous les messages de conversation.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|channelId  <br/> |int, non null  <br/> |ID du nœud.  <br/> |
|chatId  <br/> |bigint, non null  <br/> |Numéro séquentiel unique (par ID de nœud) qui définit l’ordre de la salle de conversation, généré par la table de tblLastChatId.  <br/> |
|chatDate  <br/> |bigint, non null  <br/> |Horodatage pour le message de conversation.  <br/> |
|ID utilisateur  <br/> |int, non null  <br/> |ID d’entité de l’affiche.  <br/> |
|isAlert  <br/> |bits, non null  <br/> |True si le message est un message d’alerte. False si elle ne l’est pas.  <br/> |
|contenu  <br/> |nvarchar (max), non null  <br/> | Contenu de la conversation (la version en texte brut). Le contenu est généralement au format texte brut avec les exceptions suivantes : <br/>  Les fichiers sont représentés en tant que ma-filelink : des liens. <br/>  Des liens sont représentées sous la forme d’un élément HTML (bien que le type de contenu ne peut pas être considéré comme HTML). <br/>  Récits sont codés sous la forme d’un « [article]... »-comme format. <br/> |
|RTF  <br/> |varchar (max)  <br/> |Contenu de la conversation (la version RTF). Peut avoir la valeur Null si le client ne fournit pas.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|\<channelID, chatD\>  <br/> |Clé primaire.  <br/> |
   

