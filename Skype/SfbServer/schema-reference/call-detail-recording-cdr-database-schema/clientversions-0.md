---
title: Vue clientversions
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La vue ClientVersions stocke des informations sur les différents types de clients et les versions qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement dans la vue représente une version du client. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: cc4024a7e2644a177eb6962c8fdc7078fd6b397d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901521"
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
   

