---
title: tblChat
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat contient tous les messages de conversation.
ms.openlocfilehash: e8a07c0c8ff8b3b473855ee86f6fc0c276e959f6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839816"
---
# <a name="tblchat"></a>tblChat
 
tblChat contient tous les messages de conversation.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
|:-----|:-----|:-----|
|channelId  <br/> |int, non null  <br/> |ID de nœud.  <br/> |
|chatId  <br/> |bigint, non null  <br/> |Numéro d’ordre unique (par ID de nœud) qui définit l’ordre de la salle de conversation, généré par la table tblLastChatId.  <br/> |
|chatDate  <br/> |bigint, non null  <br/> |Horodatage du message de conversation.  <br/> |
|userId  <br/> |int, non null  <br/> |ID de principal de la personne ayant publié le message.  <br/> |
|isAlert  <br/> |bit, non null  <br/> |True s’il s’agit d’un message d’alerte. False dans le cas contraire.  <br/> |
|contenu  <br/> |nvarchar (max), non null  <br/> | Contenu de la conversation (version en texte brut). Le contenu est généralement en texte brut, avec les exceptions suivantes : <br/>  les fichiers sont représentés sous forme de liens ma-filelink: ; <br/>  les liens sont représentés sous forme d’éléments HTML (bien que le type de contenu ne puisse pas être considéré comme du HTML) ; <br/>  Les articles sont codés au format « [STORY]. ... ». <br/> |
|rtf  <br/> |varchar(max)  <br/> |Contenu de la conversation (version au format RTF). Peut être Null si le client ne le fournit pas.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|\<channelID, chatD\>  <br/> |Clé primaire.  <br/> |
   

