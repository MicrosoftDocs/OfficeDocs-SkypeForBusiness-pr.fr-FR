---
title: Affichage FileTransfers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: Le mode FileTransfer stocke les informations sur les sessions d’égal à égal de transfert de fichiers. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: d650c04b8dada5828eed5d7bc3039cb77570ce2b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815202"
---
# <a name="filetransfers-view"></a>Affichage FileTransfers
 
Le mode FileTransfer stocke les informations sur les sessions d’égal à égal de transfert de fichiers. Cet affichage a été présenté dans Microsoft Lync Server 2013.
  
> [!NOTE]
> Le mode FileTransfers contient toutes les colonnes de la [vue SessionDetails](sessiondetails-0.md) , en plus des colonnes répertoriées ci-dessous.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |Nom du fichier transféré.  <br/> |
|**Sans** <br/> |nvarchar(128  <br/> |Permet de détecter chaque message de suivi associé à celui-ci.  <br/> |
|**FileIdentity** <br/> |identificateur  <br/> |Identificateur unique permettant de faire la distinction entre les transferts de fichiers impliquant le même nom de fichier.  <br/> |
|**Valide** <br/> |bit  <br/> |Peut être vrai ou nul. Si vrai, l’argument refuser et annuler est nul.  <br/> |
|**Rejeter** <br/> |bit  <br/> |Peut être vrai ou nul. Si vrai, l’argument accepter et annuler est nul.  <br/> |
|**Annuler** <br/> |bit  <br/> |Peut être vrai ou nul. Si vrai, l’argument accepter et refuser est nul.  <br/> |
   

