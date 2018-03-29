---
title: tblComplianceData
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contient les événements de conformité qui n’ont pas encore été traitées par l’adaptateur de la conformité.
ms.openlocfilehash: 6fcee20a96a83a69a3671fe9255f1336590b42de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData contient les événements de conformité qui n’ont pas encore été traitées par l’adaptateur de la conformité.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint, non null  <br/> |ID d’événement.  <br/> |
|entryDate  <br/> |smalldatetime, non null  <br/> |Heure de l’insertion (peut être dans le futur pour cmplType = 9, car l’entrée est simplement un espace réservé dans ce cas).  <br/> |
|cmplType  <br/> |int, non null  <br/> | Type d’événement de conformité : <br/>  1 : chat <br/>  2 : backchat <br/>  3 : téléchargement de fichier <br/>  4 : téléchargement de fichiers <br/>  9 : transfert de fichiers provisoire <br/>  10 : chat suppression (avec remplacement) <br/>  11 : purge de conversation <br/> |
|cmplTime  <br/> |bigint, non null  <br/> |Horodatage de l’événement.  <br/> |
|cmplChannelUri  <br/> |nvarchar (255), non null  <br/> |Chaîne identifiant universel (URI).  <br/> |
|cmplChatID  <br/> |bigint  <br/> |Chat ID (correspondant à la table de tblChat.chatId).  <br/> |
|cmplUserID  <br/> |int, non null  <br/> |ID d’entité de l’affiche (correspondant à la table de tblPrincipal.prinID).  <br/> |
|cmplUserUri  <br/> |nvarchar (255), non null  <br/> |URI de l’utilisateur.  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |Messages (codage dépend de cmplType).  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|cmplEventID  <br/> |Clé primaire.  <br/> |
   

