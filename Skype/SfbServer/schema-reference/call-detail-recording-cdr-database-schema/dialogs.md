---
title: Boîtes de dialogue tableau Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La table Dialogs est une table de prise en charge qui stocke les informations sur le Dialogid pour les sessions d’égal à égal.
ms.openlocfilehash: 379956a2c77c60a53e702913d81b25b41dc2fc23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901128"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Boîtes de dialogue tableau Skype pour Business Server 2015
 
La table Dialogs est une table de prise en charge qui stocke les informations sur le Dialogid pour les sessions d’égal à égal.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Principal  <br/> |Heure de la demande de session ; utilisé en conjonction avec SessionIDSeq pour identifier de manière unique une session.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec SessionIDTime pour identifier de manière unique une session.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Somme de contrôle de la ExternalID. Ce champ est utilisé pour augmenter la vitesse des recherches de base de données.  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |ID de boîte de dialogue SIP, stockée sous forme d’un fichier binaire. Le format de fichier binaire est :  <br/> boîte de dialogue de balise ; pour une balise  <br/> Ces données peuvent être converties au format texte à l’aide de la syntaxe suivante :  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

