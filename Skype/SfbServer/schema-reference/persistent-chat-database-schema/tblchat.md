---
title: tblChat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat contient tous les messages de conversation.
ms.openlocfilehash: b375c8c5dcd626a02f59aa9a916d3ca883e4767d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809894"
---
# <a name="tblchat"></a>tblChat
 
tblChat contient tous les messages de conversation.
  
**Columns**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|channelId  <br/> |int, non null  <br/> |ID de nœud.  <br/> |
|chatId  <br/> |bigint, non null  <br/> |Numéro d’ordre unique (par ID de nœud) qui définit l’ordre de la salle de conversation, généré par la table tblLastChatId.  <br/> |
|chatDate  <br/> |bigint, non null  <br/> |Horodatage du message de conversation.  <br/> |
|userId  <br/> |int, non null  <br/> |ID de principal de la personne ayant publié le message.  <br/> |
|isAlert  <br/> |bit, non null  <br/> |True s’il s’agit d’un message d’alerte. False dans le cas contraire.  <br/> |
|contenu  <br/> |nvarchar (max), non null  <br/> | Contenu de la conversation (version en texte brut). Le contenu est généralement en texte brut, avec les exceptions suivantes : <br/>  les fichiers sont représentés sous forme de liens ma-filelink: ; <br/>  les liens sont représentés sous forme d’éléments HTML (bien que le type de contenu ne puisse pas être considéré comme du HTML) ; <br/>  Les articles sont codés sous la forme d’un format « [STORY]. ... ». <br/> |
|rtf  <br/> |varchar(max)  <br/> |Contenu de la conversation (version au format RTF). Peut être Null si le client ne le fournit pas.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|\<channelID, chatD\>  <br/> |Clé primaire.  <br/> |
   

