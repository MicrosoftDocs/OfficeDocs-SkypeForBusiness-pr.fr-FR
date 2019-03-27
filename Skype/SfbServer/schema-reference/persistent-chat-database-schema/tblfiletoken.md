---
title: tblFileToken
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken contient des jetons temporaires pour le transfert de fichiers.
ms.openlocfilehash: 46553a4b8752e2a95691dc2042a2632845166fc7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881297"
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken contient des jetons temporaires pour le transfert de fichiers.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50), non null  <br/> |Jeton unique (GUID).  <br/> |
|fileTokenUserID  <br/> |int, non null  <br/> |ID du principal qui transfère le fichier.  <br/> |
|fileTokenChannelID  <br/> |GUID, non null  <br/> |GUID du nœud de la salle de conversation.  <br/> |
|fileTokenExpireDate  <br/> |DateTime, non null  <br/> |Délai d’expiration. (Jetons expirent au bout de 30 minutes, à moins qu’épinglé (consultez les descriptions suivantes dans cette colonne).  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |URL du fichier transféré (pour l’utilisation du service de conformité).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |URL de la miniature du fichier transféré (pour l’utilisation du service de conformité).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |Horodatage de l’opération de transfert de fichier (pour l’utilisation du service de conformité).  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |True si télécharger ; False si Téléchargez (pour l’utilisation du service de conformité).  <br/> |
|fileTokenCompliancePinned  <br/> |bit, non null  <br/> |True si le jeton est mis en attente. Il est utilisé pour conserver le jeton dans la table jusqu'à ce que le service de conformité pour extraire les champs appropriés.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|fileToken  <br/> |Clé primaire.  <br/> |
|fileTokenChannelID  <br/> |Clé étrangère avec recherche dans la table tblNode.nodeGuid.  <br/> |
   

