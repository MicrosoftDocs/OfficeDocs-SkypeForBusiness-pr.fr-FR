---
title: tblPreference
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contient les préférences client des utilisateurs. Il est généralement utilisé par les clients antérieurs à Lync 2013.
ms.openlocfilehash: e9b4518fbe203750406fe02a3a69b04d1e45a9c1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578598"
---
# <a name="tblpreference"></a>tblPreference

tblPreference contient les préférences client des utilisateurs. Il est généralement utilisé par les clients antérieurs à Lync 2013.

**Colonnes**


| **Colonne**            | **Type (Type)**                        | **Description**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), non null  <br/> | Étiquette avec un format tel que : \<user sip uri\>                   |
| prefSeqID  <br/>      | entier, non null  <br/>            | Numéro séquentiel (par étiquette) à des fins de contrôle de version.  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | Contenu codé.  <br/>                                         |
| lastModifiedBy  <br/> | entier, non null  <br/>            | ID du principal qui à mis à jour la préférence.  <br/>         |

**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Clé primaire.  <br/> |


