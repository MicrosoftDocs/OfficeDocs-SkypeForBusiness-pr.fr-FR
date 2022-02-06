---
title: tblComplianceData
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par l’ensemble des traducteurs inscrits.
---

# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par l’ensemble des traducteurs inscrits.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint, non null  <br/> |ID d’événement.  <br/> |
|entryDate  <br/> |smalldatetime, non null  <br/> |Moment de l’insertion (peut être éloigné dans le futur pour cmplType=9, car l’entrée est juste un espace réservé dans ce cas).  <br/> |
|cmplType  <br/> |int, non null  <br/> | Type d’événement de conformité : <br/>  1: Conversation <br/>  2: Sauvegarde de conversation <br/>  3: Téléchargement de fichiers <br/>  4: Chargement de fichiers <br/>  9: Transfert de fichier provisoire <br/>  10: Suppression de conversation (avec remplacement) <br/>  11: Purge des conversations <br/> |
|cmplTime  <br/> |bigint, non null  <br/> |Horodatage pour l’événement.  <br/> |
|cmplChannelUri  <br/> |nvarchar (255), non null  <br/> |URI (Uniform Resource Identifier) de canal.  <br/> |
|cmplChatID  <br/> |bigint  <br/> |ID de conversation (correspondant à la table tblChat.chatId).  <br/> |
|cmplUserID  <br/> |int, non null  <br/> |ID principal de l’affiche (correspondant à la table tblPrincipal.prinID).  <br/> |
|cmplUserUri  <br/> |nvarchar (255), non null  <br/> |URI de l’utilisateur.  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |Message (le codage dépend de cmplType).  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|cmplEventID  <br/> |Clé primaire.  <br/> |
   

