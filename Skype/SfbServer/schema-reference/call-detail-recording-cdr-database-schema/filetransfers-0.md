---
title: Table FileTransfers dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: Chaque enregistrement représente une session de transfert de fichier.
ms.openlocfilehash: 07ab898246efbac623910886000e97037f43ead2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Table FileTransfers dans Skype pour Business Server 2015
 
Chaque enregistrement représente une session de transfert de fichier.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaires et étrangères  <br/> |Heure de la demande de la session. Utilisé en association avec **SessionIdSeq** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaires et étrangères  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec **SessionIdTime** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**Nom de fichier** <br/> |nvarchar(256)  <br/> ||Nom du fichier.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> ||Identificateur unique pour faire la distinction entre les transferts de fichiers portant le même nom de fichier.  <br/> |
|**Cookie** <br/> |nvarchar (128)  <br/> |Principal  <br/> |Utilisé pour identifier chaque message suivi comme étant associée à celui-ci.  <br/> |
|**Accepter** <br/> |bit  <br/> ||Peut être TRUE ou la valeur NULL. Si TRUE, refuser et annuler sera NULL.  <br/> |
|**Rejeter** <br/> |bit  <br/> ||Peut être TRUE ou la valeur NULL. Si TRUE, alors accepter et annuler sera NULL.  <br/> |
|**Annuler** <br/> |bit  <br/> ||Peut être TRUE ou la valeur NULL. Si TRUE, alors accepter et rejeter sera NULL.  <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> ||Pour un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype pour Business Server 2015.  <br/> |
   

