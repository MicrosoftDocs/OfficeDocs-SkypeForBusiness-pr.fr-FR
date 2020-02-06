---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contient certaines configurations du serveur de chat permanent non prises en charge, en une seule ligne.
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814622"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig contient certaines configurations du serveur de chat permanent non prises en charge, en une seule ligne.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), pas null  <br/> |Contient « pool ».  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |Contenu de configuration.  <br/> |
|configPoolID  <br/> |GUID, pas null  <br/> |ID unique de l’instance de base de données.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|configLabel  <br/> |Clé primaire.  <br/> |
   

