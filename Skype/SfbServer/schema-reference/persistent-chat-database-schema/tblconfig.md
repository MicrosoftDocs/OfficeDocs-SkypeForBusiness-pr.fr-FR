---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contient une configuration non prise en charge Persistent Chat Server, dans une seule ligne.
ms.openlocfilehash: 79cd7e2303210bb07f35fa2c6b7ecc5c86b7e8cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930021"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig contient une configuration non prise en charge Persistent Chat Server, dans une seule ligne.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), non null  <br/> |Contient « pool ».  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |Contenu de la configuration.  <br/> |
|configPoolID  <br/> |GUID, non null  <br/> |ID unique de l’instance de base de données.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|configLabel  <br/> |Clé primaire.  <br/> |
   

