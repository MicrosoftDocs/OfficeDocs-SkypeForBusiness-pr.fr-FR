---
title: Vue FileTransfers
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: L’affichage FileTransfer stocke des informations sur les sessions de transfert de fichiers d’égal à égal. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 11e46edf67c6ba9d1597f296ffd8ecf551241132
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777804"
---
# <a name="filetransfers-view"></a>Vue FileTransfers
 
L’affichage FileTransfer stocke des informations sur les sessions de transfert de fichiers d’égal à égal. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
> [!NOTE]
> L’affichage FileTransfers contient toutes les colonnes de l’affichage [SessionDetails](sessiondetails-0.md) en plus des colonnes répertoriées ci-dessous.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |Nom du fichier transféré.  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |Utilisé pour identifier chaque message de suivi comme étant associé à celui-ci.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |Identificateur unique permettant de différencier les transferts de fichiers concernant le même nom de fichier.  <br/> |
|**Accept** <br/> |bit  <br/> |Peut-être TRUE ou NULL. Si TRUE, alors Reject et Cancel seront NULL.  <br/> |
|**Reject** <br/> |bit  <br/> |Peut-être TRUE ou NULL. Si TRUE, alors Accept et Cancel seront NULL.  <br/> |
|**Cancel** <br/> |bit  <br/> |Peut-être TRUE ou NULL. Si TRUE, alors Accept et Reject seront NULL.  <br/> |
   

