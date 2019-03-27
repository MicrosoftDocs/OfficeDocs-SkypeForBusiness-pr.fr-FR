---
title: tblPreference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contient les préférences du client les utilisateurs. Cela est généralement utilisé par les clients antérieurs à Lync 2013.
ms.openlocfilehash: b5036d9c71feaea6406ecdcaa6f15b61f64d5ad3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879790"
---
# <a name="tblpreference"></a>tblPreference

tblPreference contient les préférences du client les utilisateurs. Cela est généralement utilisé par les clients antérieurs à Lync 2013.

**Colonnes**


| **Colonne**            | **Type**                        | **Description**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), non null  <br/> | Étiquette dont le format telle que : \<uri sip utilisateur\>                   |
| prefSeqID  <br/>      | int, non null  <br/>            | Un numéro séquentiel (par étiquette) à des fins de contrôle de version.  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | Contenu codé.  <br/>                                         |
| lastModifiedBy  <br/> | int, non null  <br/>            | ID du principal ayant la préférence de mise à jour.  <br/>         |

**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Clé primaire.  <br/> |


