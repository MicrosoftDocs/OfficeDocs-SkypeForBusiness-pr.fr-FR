---
title: Vue de ClientVersions
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La vue ClientVersions stocke des informations sur les différents types de clients et les versions qui ont participé aux sessions enregistrées dans la base de données. Chaque enregistrement dans la vue représente une version du client. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 0906e35d0912684c9aeb169017b5df0a53202c50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="clientversions-view"></a>Vue de ClientVersions
 
La vue ClientVersions stocke des informations sur les différents types de clients et les versions qui ont participé aux sessions enregistrées dans la base de données. Chaque enregistrement dans la vue représente une version du client. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
> [!NOTE]
> Il peuvent exister plusieurs enregistrements pour certaines colonnes. 
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**Valeur de VersionId** <br/> |int  <br/> |Numéro unique identifiant le type de client et de la version.  <br/> |
|**Version** <br/> |nvarchar(256)  <br/> |Représente l’agent utilisateur.  <br/> |
|**TypeClient** <br/> |int  <br/> |Type de client.  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Catégorie à laquelle appartient le client. Par exemple, le client Conferencing_Attendant_1.0 appartient à la TCHA ClientCategory.  <br/> |
   

