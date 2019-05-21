---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par la carte de conformité.
ms.openlocfilehash: b505b3e05fb2aebba98804f5b7ad6a1d4d2da53e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295509"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par la carte de conformité.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint, pas null  <br/> |ID de l’événement.  <br/> |
|entryDate  <br/> |smalldatetime, pas null  <br/> |Temps d’insertion (peut-être lointain dans le cas de cmplType = 9, car l’entrée n’est qu’un espace réservé dans le cas présent).  <br/> |
|cmplType  <br/> |ent, non null  <br/> | Type d’événement de conformité: <br/>  1: conversation <br/>  2: discussions <br/>  3: Téléchargement de fichier <br/>  4: Téléchargement de fichier <br/>  9: transfert de fichier provisoire <br/>  10: suppression d’une discussion (avec remplacer) <br/>  11: suppression de conversation <br/> |
|cmplTime  <br/> |bigint, pas null  <br/> |Date et heure de l’événement.  <br/> |
|cmplChannelUri  <br/> |nvarchar (255), pas null  <br/> |URI (Uniform Resource Identifier) de canal.  <br/> |
|cmplChatID  <br/> |bigint  <br/> |ID de conversation (correspondant à la table tblChat. chatId).  <br/> |
|cmplUserID  <br/> |ent, non null  <br/> |ID principal de l’affiche (correspondant à la table tblPrincipal. prinID).  <br/> |
|cmplUserUri  <br/> |nvarchar (255), pas null  <br/> |URI de l’utilisateur.  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |Le message (Encoding dépend de cmplType).  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|cmplEventID  <br/> |Clé primaire.  <br/> |
   

