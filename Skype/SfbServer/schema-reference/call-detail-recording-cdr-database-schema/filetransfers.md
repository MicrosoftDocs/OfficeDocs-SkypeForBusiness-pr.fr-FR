---
title: Vue de FileTransfers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: La vue FileTranfer stocke des informations sur les sessions de transfert de fichier de peer-to-peer. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 69b986c24a3a8f3646738eb3e1e3e97794be8e9e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="filetransfers-view"></a>Vue de FileTransfers
 
La vue FileTranfer stocke des informations sur les sessions de transfert de fichier de peer-to-peer. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
> [!NOTE]
> La vue FileTransfers contient toutes les colonnes dans la [vue de le SessionDetails](sessiondetails-0.md) en outre les colonnes répertoriées ci-dessous.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**Nom de fichier** <br/> |nvarchar(256)  <br/> |Nom du fichier transféré.  <br/> |
|**Cookie** <br/> |nvarchar (128)  <br/> |Utilisé pour identifier chaque message suivi comme étant associée à celui-ci.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |Identificateur unique pour faire la distinction entre les transferts de fichiers portant le même nom de fichier.  <br/> |
|**Accepter** <br/> |bit  <br/> |Peut être TRUE ou la valeur NULL. Si TRUE, refuser et annuler sera NULL.  <br/> |
|**Rejeter** <br/> |bit  <br/> |Peut être TRUE ou la valeur NULL. Si TRUE, alors accepter et annuler sera NULL.  <br/> |
|**Annuler** <br/> |bit  <br/> |Peut être TRUE ou la valeur NULL. Si TRUE, alors accepter et rejeter sera NULL.  <br/> |
   

