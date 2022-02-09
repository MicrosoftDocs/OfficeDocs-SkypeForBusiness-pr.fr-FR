---
title: tblFileToken
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken contient des jetons temporaires pour le transfert de fichiers.
ms.openlocfilehash: 78d132123430143f9609f544d54f176ea5d966d1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62417447"
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken contient des jetons temporaires pour le transfert de fichiers.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50), non null  <br/> |Jeton unique (un GUID).  <br/> |
|fileTokenUserID  <br/> |int, non null  <br/> |ID du principal qui transfère le fichier.  <br/> |
|fileTokenChannelID  <br/> |GUID, non null  <br/> |GUID du nœud de salles de conversation.  <br/> |
|fileTokenExpireDate  <br/> |datetime, non null  <br/> |Heure d’expiration. Les jetons expirent après 30 minutes sauf s’ils sont épinglés (voir les descriptions suivantes dans cette colonne).  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |URL du fichier transféré (pour l’utilisation du service de conformité).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |URL de la miniature du fichier transféré (pour l’utilisation du service de conformité).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |Horodatage de l’opération effective de transfert de fichier (pour l’utilisation du service de conformité).  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |True en cas de téléchargement sortant ; False en cas de téléchargement entrant (pour l’utilisation du service de conformité).  <br/> |
|fileTokenCompliancePinned  <br/> |bit, non null  <br/> |True si le jeton est épinglé. Il est utilisé pour conserver le jeton dans la table jusqu’à ce que le service de conformité ait la possibilité d’extraire les champs pertinents de celui-ci.  <br/> |
   
**Keys**

|**Colonne**|**Description**|
|:-----|:-----|
|fileToken  <br/> |Clé primaire.  <br/> |
|fileTokenChannelID  <br/> |Clé étrangère avec recherche dans la table tblNode.nodeGuid.  <br/> |
   

