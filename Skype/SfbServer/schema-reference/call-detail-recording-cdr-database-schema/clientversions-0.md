---
title: Vue clientversions
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La vue ClientVersions stocke des informations sur les différents types de clients et les versions qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement dans la vue représente une version du client. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: abf1436a2c3309e95bec8371b586c017e11b816d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881694"
---
# <a name="clientversions-view"></a>Vue clientversions
 
La vue ClientVersions stocke des informations sur les différents types de clients et les versions qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement dans la vue représente une version du client. Cet affichage a été introduit dans Microsoft Lync Server 2013.
  
> [!NOTE]
> Il peuvent exister plusieurs enregistrements pour certaines colonnes. 
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |Numéro unique identifiant ce type de client et de la version.  <br/> |
|**Version** <br/> |nvarchar(256)  <br/> |Représente l’agent utilisateur.  <br/> |
|**TypeClient** <br/> |int  <br/> |Type de client.  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Catégorie à laquelle appartient le client. Par exemple, le client Conferencing_Attendant_1.0 appartient à la CAA ClientCategory.  <br/> |
   

