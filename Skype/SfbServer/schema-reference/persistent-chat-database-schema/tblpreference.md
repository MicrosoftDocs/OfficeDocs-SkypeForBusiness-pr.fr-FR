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
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contient les préférences client de l’utilisateur. Il est généralement utilisé par les clients antérieurs à Lync 2013.
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295341"
---
# <a name="tblpreference"></a>tblPreference

tblPreference contient les préférences client de l’utilisateur. Il est généralement utilisé par les clients antérieurs à Lync 2013.

**Celles**


| **Colonne**            | **Type**                        | **Description**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), pas null  <br/> | Étiquette avec un format tel que: \<URI SIP utilisateur\>                   |
| prefSeqID  <br/>      | ent, non null  <br/>            | Un numéro séquentiel (par étiquette) à des fins de contrôle de version.  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | Contenu encodé.  <br/>                                         |
| lastModifiedBy  <br/> | ent, non null  <br/>            | ID de l’objet principal qui a mis à jour la préférence.  <br/>         |

**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Clé primaire.  <br/> |


