---
title: tblPreference
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
ms.openlocfilehash: c76c62ec453ab1a152738cb16d76e5c5394a2a98
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375942"
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


