---
title: tblChat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat contient tous les messages de discussion.
ms.openlocfilehash: 15c7030fe14f62c5d32af54c0f5a6901da3f977b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295537"
---
# <a name="tblchat"></a>tblChat
 
tblChat contient tous les messages de discussion.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|channelId  <br/> |ent, non null  <br/> |ID du nœud.  <br/> |
|chatId  <br/> |bigint, pas null  <br/> |Numéro séquentiel unique (par ID de nœud) qui définit l’ordre des salles de conversation généré par la table tblLastChatId.  <br/> |
|chatDate  <br/> |bigint, pas null  <br/> |Horodatage du message.  <br/> |
|userId  <br/> |ent, non null  <br/> |ID principal de l’affiche.  <br/> |
|isAlert  <br/> |bit, pas null  <br/> |True si le message est un message d’alerte. Faux si ce n’est pas le cas.  <br/> |
|teneur  <br/> |nvarchar (max), pas null  <br/> | Contenu de la discussion (version en texte brut). Le contenu est généralement au format texte brut avec les exceptions suivantes: <br/>  Les fichiers sont représentés par ma-filelink: links. <br/>  Les liens sont représentés sous forme d’élément HTML (même si le type de contenu ne peut pas être considéré comme du code HTML). <br/>  Les récits sont encodés en tant que format «[histoire]....». <br/> |
|RTF  <br/> |varchar (max)  <br/> |Contenu de conversation (version RTF). Est susceptible d’être null si le client ne la fournit pas.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|\<channelID, conversation\>  <br/> |Clé primaire.  <br/> |
   

