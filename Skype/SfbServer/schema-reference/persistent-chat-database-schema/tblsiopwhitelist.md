---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblsiopwhitelist représente la liste des compléments inscrits qui peuvent être associés à des nœuds.
ms.openlocfilehash: f3389f3d4a956e00180303c09bd3eb264d786b9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924772"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblsiopwhitelist représente la liste des compléments inscrits qui peuvent être associés à des nœuds.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID, non null  <br/> |GUID de la macro complémentaire.  <br/> |
|siopName  <br/> |nvarchar (50), non null  <br/> |Nom complet de la macro complémentaire.  <br/> |
|siopUrl  <br/> |nvarchar (255), non null  <br/> |URL de l’application add-in.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|siopID  <br/> |Clé primaire.  <br/> |
   

