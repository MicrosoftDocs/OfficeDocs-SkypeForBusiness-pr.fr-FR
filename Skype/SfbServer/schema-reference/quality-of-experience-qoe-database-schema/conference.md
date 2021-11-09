---
title: Table Conference
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La table Conference est une table de prise en charge. Chaque enregistrement représente une conférence ou une session d’égal à égal.
ms.openlocfilehash: 8d47cd6c67d6d8d17d187353b8b15d79b38acab3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827367"
---
# <a name="conference-table"></a>Table Conference
 
La table Conference est une table de prise en charge. Chaque enregistrement représente une conférence ou une session d’égal à égal.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique d’identification de cet enregistrement de conférence.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |unique  <br/> |URI de conférence s’il s’agit d’une conférence, ou DialogID s’il s’agit d’une session d’égal à égal.  <br/> |
|**Somme de contrôle** <br/> |int  <br/> |Index  <br/> |Checksum de l’URI de la conférence. À usage interne.  <br/> |
|**NextUpdateTS** <br/> |DateHeure  <br/> ||À usage interne uniquement.  <br/> |
   

