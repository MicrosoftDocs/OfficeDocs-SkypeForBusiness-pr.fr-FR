---
title: Table Dialogs in Skype for Business Server 2015
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La table Dialogs est une table de prise en charge qui stocke les informations sur les DialogIDs pour les sessions d’égal à égal.
ms.openlocfilehash: a4f0bb8c63e165985ef09af8f9aafa071529bf1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816044"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Table Dialogs in Skype for Business Server 2015
 
La table Dialogs est une table de prise en charge qui stocke les informations sur les DialogIDs pour les sessions d’égal à égal.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire  <br/> |Heure de la demande de session ; utilisé conjointement avec SessionIDSeq pour identifier de manière unique une session.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire  <br/> |Numéro d’ID identifiant la session. Utilisé conjointement avec SessionIDTime pour identifier de manière unique une session.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Checksum de l’ExternalID. Ce champ est utilisé pour augmenter la vitesse des recherches dans la base de données.  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |ID de boîte de dialogue SIP, stocké en tant que fichier binaire. Le format du fichier binaire est :  <br/> dialog;from-tag;to-tag  <br/> Ces données peuvent être converties au format texte à l’aide de cette syntaxe :  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

