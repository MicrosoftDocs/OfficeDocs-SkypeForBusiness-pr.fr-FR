---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par la carte de conformité.
ms.openlocfilehash: 88319da90c1f3e03b6ca3e441259972f51d0bcf9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929930"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par la carte de conformité.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint, non null  <br/> |ID d’événement.  <br/> |
|entryDate  <br/> |smalldatetime, non null  <br/> |Heure d’insertion (peut être éloigné dans le futur pour cmplType = 9, car l’entrée est juste un espace réservé dans ce cas).  <br/> |
|cmplType  <br/> |int, non null  <br/> | Type d’événement de conformité : <br/>  1 : conversation <br/>  2 : sauvegarde de conversation <br/>  3 : téléchargement de fichier <br/>  4 : téléchargement de fichier <br/>  9 : transfert de fichier provisoire <br/>  10 : suppression (avec remplacement) de conversation <br/>  11 : purge des conversations <br/> |
|cmplTime  <br/> |bigint, non null  <br/> |Horodatage de l’événement.  <br/> |
|cmplChannelUri  <br/> |nvarchar (255), non null  <br/> |Canal Uniform Resource Identifier (URI).  <br/> |
|cmplChatID  <br/> |bigint  <br/> |ID de conversation (correspondant à la table tblChat.chatId).  <br/> |
|cmplUserID  <br/> |int, non null  <br/> |ID principal de l’affiche (correspondant à la table tblPrincipal.prinID).  <br/> |
|cmplUserUri  <br/> |nvarchar (255), non null  <br/> |URI de l’utilisateur.  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |Message (codage dépend de cmplType).  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|cmplEventID  <br/> |Clé primaire.  <br/> |
   

