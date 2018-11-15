---
title: Vue filetransfers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: Le mode de transfert de fichiers stocke des informations sur les sessions de transfert de fichiers d’égal à égal. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 97bc5f957192c8a2c6d888f81fce0891aa2b4f75
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531218"
---
# <a name="filetransfers-view"></a>Vue filetransfers
 
Le mode de transfert de fichiers stocke des informations sur les sessions de transfert de fichiers d’égal à égal. Cet affichage a été introduit dans Microsoft Lync Server 2013.
  
> [!NOTE]
> La vue filetransfers contient toutes les colonnes de [SessionDetails view](sessiondetails-0.md) en outre les colonnes répertoriées ci-dessous.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |Nom du fichier transféré.  <br/> |
|**Cookie** <br/> |nvarchar (128)  <br/> |Utilisé pour identifier chaque message de suivi comme étant associé à celle-ci.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |Identificateur unique pour distinguer les transferts de fichiers impliquant le même nom de fichier.  <br/> |
|**Accepter** <br/> |bit  <br/> |Peut avoir la valeur TRUE ou NULL. Si TRUE, refuser et annuler sera NULL.  <br/> |
|**Rejeter** <br/> |bit  <br/> |Peut avoir la valeur TRUE ou NULL. Si la valeur TRUE, puis accepter et annuler sera NULL.  <br/> |
|**Annuler** <br/> |bit  <br/> |Peut avoir la valeur TRUE ou NULL. Si la valeur TRUE, puis accepter et rejeter sera NULL.  <br/> |
   

