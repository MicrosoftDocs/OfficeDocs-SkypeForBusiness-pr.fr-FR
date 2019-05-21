---
title: Tableau boîtes de dialogue dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Le tableau boîtes de dialogue est une table de prise en charge qui contient les informations sur DialogIDs pour les sessions d’égal à égal.
ms.openlocfilehash: 61230cf7f72405c4c5f27ff7b159afe4e5a7842e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296321"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Tableau boîtes de dialogue dans Skype entreprise Server 2015
 
Le tableau boîtes de dialogue est une table de prise en charge qui contient les informations sur DialogIDs pour les sessions d’égal à égal.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Principal  <br/> |Durée de la demande de session; utilisé conjointement avec SessionIDSeq pour identifier une session de manière unique.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal  <br/> |IDENTIFIant de la session. Utilisé conjointement avec SessionIDTime pour identifier une session de manière unique.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Checksum du ExternalID. Ce champ est utilisé pour augmenter la vitesse de recherche de la base de données.  <br/> |
|**ExternalId** <br/> |varbinary (LGA775)  <br/> | <br/> |ID de boîte de dialogue SIP, enregistré en tant que fichier binaire. Le format du binaire est le suivant:  <br/> boîte de dialogue; à partir d’une balise  <br/> Vous pouvez convertir ces données en format texte à l’aide de la syntaxe suivante:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

