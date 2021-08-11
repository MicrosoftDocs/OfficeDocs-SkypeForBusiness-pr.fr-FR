---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contient une configuration non pris en compte du serveur de conversation permanente, sur une ligne.
ms.openlocfilehash: 0e9cc0a0c4686432032591aa0c380b303fc5251a56a6c983a1e10b009e0eb28a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278352"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig contient une configuration non pris en compte du serveur de conversation permanente, sur une ligne.
  
**Columns**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), non null  <br/> |Contient « pool ».  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |Contenu de configuration.  <br/> |
|configPoolID  <br/> |GUID, non null  <br/> |ID unique de l’instance de base de données.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|configLabel  <br/> |Clé primaire.  <br/> |
   

