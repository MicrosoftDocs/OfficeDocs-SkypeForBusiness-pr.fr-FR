---
title: tblFileToken
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken contient les jetons temporaires à des fins de transfert de fichier.
ms.openlocfilehash: 86047611c21301543a12486fa1c15bb15fde4c65
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken contient les jetons temporaires à des fins de transfert de fichier.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50), non null  <br/> |Jeton unique (un GUID).  <br/> |
|fileTokenUserID  <br/> |int, non null  <br/> |ID de l’entité de sécurité qui est de transférer le fichier.  <br/> |
|fileTokenChannelID  <br/> |GUID, pas null  <br/> |GUID du nœud de la salle de conversation.  <br/> |
|fileTokenExpireDate  <br/> |DateTime, non null  <br/> |Délai d’expiration. (Les jetons expirent après 30 minutes, à moins qu’épinglé (voir les descriptions suivantes dans cette colonne).  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |URL du fichier transféré (pour une utilisation du service de mise en conformité).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |URL de la miniature représentant le fichier transféré (pour une utilisation du service de mise en conformité).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |Horodateur de l’opération de transfert de fichier (pour une utilisation du service de mise en conformité).  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |True si le téléchargement ; False si télécharger (pour une utilisation du service de mise en conformité).  <br/> |
|fileTokenCompliancePinned  <br/> |bits, non null  <br/> |True si le jeton est mis en attente. Il est utilisé pour conserver le jeton dans la table jusqu'à ce que le service de mise en conformité pour extraire les champs appropriés.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|fileToken  <br/> |Clé primaire.  <br/> |
|fileTokenChannelID  <br/> |Clé étrangère avec la recherche dans la table de tblNode.nodeGuid.  <br/> |
   

