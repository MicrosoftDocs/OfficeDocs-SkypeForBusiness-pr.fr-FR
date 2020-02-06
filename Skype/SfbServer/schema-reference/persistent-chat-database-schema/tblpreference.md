---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contient les préférences client de l’utilisateur. Il est généralement utilisé par les clients antérieurs à Lync 2013.
ms.openlocfilehash: 426a9f6aebe6cc6e510e2a75093b9210d3a0ba46
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814552"
---
# <a name="tblpreference"></a>tblPreference

tblPreference contient les préférences client de l’utilisateur. Il est généralement utilisé par les clients antérieurs à Lync 2013.

**Celles**


| **Colonne**            | **Type**                        | **Description**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), pas null  <br/> | Étiquette avec un format tel que : \<URI SIP utilisateur\>                   |
| prefSeqID  <br/>      | ent, non null  <br/>            | Un numéro séquentiel (par étiquette) à des fins de contrôle de version.  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | Contenu encodé.  <br/>                                         |
| lastModifiedBy  <br/> | ent, non null  <br/>            | ID de l’objet principal qui a mis à jour la préférence.  <br/>         |

**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Clé primaire.  <br/> |


