---
title: Affichage ClientVersions
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: Le mode ClientVersions stocke les informations sur les différents types de clients et différentes versions ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement dans la vue représente une version du client. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: d37e2a1599eaf8906d11fdb8faf545aa3447f00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815412"
---
# <a name="clientversions-view"></a>Affichage ClientVersions
 
Le mode ClientVersions stocke les informations sur les différents types de clients et différentes versions ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement dans la vue représente une version du client. Cet affichage a été présenté dans Microsoft Lync Server 2013.
  
> [!NOTE]
> Il peut y avoir plusieurs enregistrements pour certaines colonnes. 
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |Numéro unique identifiant ce type et version de client.  <br/> |
|**Version** <br/> |nvarchar(256)  <br/> |Représente l’agent utilisateur.  <br/> |
|**TypeClient** <br/> |int  <br/> |Type de client.  <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Catégorie à laquelle le client appartient. Par exemple, le client Conferencing_Attendant_1.0 appartient au CAA ClientCategory.  <br/> |
   

