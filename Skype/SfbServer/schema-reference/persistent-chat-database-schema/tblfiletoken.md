---
title: tblFileToken
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
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken contient des jetons temporaires aux fins de transfert de fichiers.
ms.openlocfilehash: 573c921278521eb5b9ed7cc754dec9fa3471e9f4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814592"
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken contient des jetons temporaires aux fins de transfert de fichiers.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50), pas null  <br/> |Jeton unique (GUID).  <br/> |
|fileTokenUserID  <br/> |ent, non null  <br/> |ID du principal qui transfère le fichier.  <br/> |
|fileTokenChannelID  <br/> |GUID, pas null  <br/> |GUID du nœud de salle de conversation.  <br/> |
|fileTokenExpireDate  <br/> |DATEHEURE, pas null  <br/> |Durée d’expiration. (Les jetons expirent au bout de 30 minutes, sauf s’ils sont épinglés (voir les descriptions suivies dans cette colonne).  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |URL du fichier transféré (pour une utilisation du service de conformité).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |URL de la miniature du fichier transféré (pour une utilisation du service de conformité).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |Horodatage de l’opération de transfert de fichiers réelle (pour l’utilisation du service de conformité).  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |True si Télécharger ; Faux si Télécharger (pour une utilisation du service de conformité).  <br/> |
|fileTokenCompliancePinned  <br/> |bit, pas null  <br/> |True si le jeton est épinglé. Il est utilisé pour conserver le jeton dans le tableau jusqu’à ce que le service de conformité puisse récupérer les champs appropriés.  <br/> |
   
**Permettent**

|**Colonne**|**Description**|
|:-----|:-----|
|fileToken  <br/> |Clé primaire.  <br/> |
|fileTokenChannelID  <br/> |Clé étrangère avec recherche dans la table tblNode. nodeGuid.  <br/> |
   

