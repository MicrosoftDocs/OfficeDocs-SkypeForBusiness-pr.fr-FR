---
title: tblChat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat contient tous les messages de conversation.
ms.openlocfilehash: 77aa6ec803803a0f38e02c01167d0bbc5f090080
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929909"
---
# <a name="tblchat"></a>tblChat
 
tblChat contient tous les messages de conversation.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|channelId  <br/> |int, non null  <br/> |ID du nœud.  <br/> |
|chatId  <br/> |bigint, non null  <br/> |Numéro séquentiel unique (par ID de nœud) qui définit l’ordre de la salle de conversation, généré par la table tblLastChatId.  <br/> |
|chatDate  <br/> |bigint, non null  <br/> |Horodatage du message de conversation.  <br/> |
|nom d’utilisateur  <br/> |int, non null  <br/> |ID principal de l’affiche.  <br/> |
|isAlert  <br/> |bit, non null  <br/> |True si le message est un message d’alerte. False si elle n’est pas.  <br/> |
|contenu  <br/> |nvarchar (max), non null  <br/> | Contenu de conversation (la version en texte brut). Le contenu est généralement au format texte brut avec les exceptions suivantes : <br/>  Les fichiers sont représentés sous forme de ma-filelink : des liens. <br/>  Liens sont représentés comme un élément HTML (bien que le type de contenu ne peut pas être considéré comme du HTML). <br/>  Articles sont encodés en tant que « [STORY]... »-comme format. <br/> |
|format RTF  <br/> |varchar (max)  <br/> |Contenu de conversation (la version RTF). Peut être Null si le client ne fournit pas.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|\<channelID, chatD\>  <br/> |Clé primaire.  <br/> |
   

