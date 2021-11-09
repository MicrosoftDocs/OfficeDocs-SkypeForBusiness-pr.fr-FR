---
title: tblPreference
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 8c719ba33196e32d48f045c07ea89ded317ab5ab
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846187"
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


