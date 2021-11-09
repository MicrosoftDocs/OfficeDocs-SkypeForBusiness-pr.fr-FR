---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contient une configuration non pris en compte du serveur de conversation permanente, sur une ligne.
ms.openlocfilehash: ddfd8cdc48158a3f4b2776b80c0bf0293ecff71b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846287"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig contient une configuration non pris en compte du serveur de conversation permanente, sur une ligne.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), non null  <br/> |Contient « pool ».  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |Contenu de configuration.  <br/> |
|configPoolID  <br/> |GUID, non null  <br/> |ID unique de l’instance de base de données.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|configLabel  <br/> |Clé primaire.  <br/> |
   

