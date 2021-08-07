---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList représente la liste des compléments inscrits qui peuvent être associés à des nœuds.
ms.openlocfilehash: 3f1ad0461bc227970d4a2a0864dbc6318ef0af32d854402180321bab74aa91e5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305376"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList représente la liste des compléments inscrits qui peuvent être associés à des nœuds.
  
**Columns**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID, non null  <br/> |GUID du complément.  <br/> |
|siopName  <br/> |nvarchar (50), non null  <br/> |Nom d’affichage du complément.  <br/> |
|siopUrl  <br/> |nvarchar (255), non null  <br/> |URL du complément.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|siopID  <br/> |Clé primaire.  <br/> |
   

