---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList représente la liste des compléments inscrits qui peuvent être associés à des nœuds.
ms.openlocfilehash: 7a84170ccf79e3cb84c876a1bc1828c4eabf4e78
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743100"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList représente la liste des compléments inscrits qui peuvent être associés à des nœuds.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID, non null  <br/> |GUID du complément.  <br/> |
|siopName  <br/> |nvarchar (50), non null  <br/> |Nom d’affichage du complément.  <br/> |
|siopUrl  <br/> |nvarchar (255), non null  <br/> |URL du complément.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|siopID  <br/> |Clé primaire.  <br/> |
   

