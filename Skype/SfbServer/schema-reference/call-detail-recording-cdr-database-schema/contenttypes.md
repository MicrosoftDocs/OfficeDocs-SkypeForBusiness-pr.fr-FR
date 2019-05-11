---
title: Table ContentTypes dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: La table ContentTypes est une table de prise en charge qui stocke une liste des types de contenu utilisés dans les sessions d’égal à égal et des sessions de conférence. Chaque enregistrement de la table représente un type de contenu.
ms.openlocfilehash: e30f5f142b9b1e166266cf8d45fe7657fee1b1b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901079"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Table ContentTypes dans Skype pour Business Server 2015
 
La table ContentTypes est une table de prise en charge qui stocke une liste des types de contenu utilisés dans les sessions d’égal à égal et des sessions de conférence. Chaque enregistrement de la table représente un type de contenu.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant le type de contenu.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||Nom du type de contenu.  <br/> |
   

