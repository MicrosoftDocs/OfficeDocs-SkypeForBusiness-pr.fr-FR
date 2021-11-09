---
title: Table Locations dans Skype Entreprise Server 2015
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Chaque enregistrement représente une référence d’emplacement dans un appel d’urgence, par exemple un appel E9-1-1.
ms.openlocfilehash: 4a008ae472dd9726af7c85f89d069bc49bd2ce4d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847047"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a>Table Locations dans Skype Entreprise Server 2015
 
Chaque enregistrement représente une référence d’emplacement dans un appel d’urgence, par exemple un appel E9-1-1.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de la demande de session. Utilisée conjointement avec **SessionIdSeq** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’ID pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**Location** <br/> |nvarchar(max)  <br/> ||Emplacement de l’appel d’urgence.  <br/> |
   

