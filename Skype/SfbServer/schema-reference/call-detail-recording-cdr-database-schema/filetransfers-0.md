---
title: Table FileTransfers dans Skype pour Business Server 2015
ms.reviewer: ''
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
ms.openlocfilehash: fe95db4e023dfb25158cf0bdf1b07f147abe6bd6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899340"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Table FileTransfers dans Skype pour Business Server 2015
 
Chaque enregistrement représente une session de transfert de fichier.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de la demande de session. Utilisé en conjonction avec **SessionIdSeq** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**Nom de fichier** <br/> |nvarchar(256)  <br/> ||Nom du fichier.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> ||Identificateur unique pour distinguer les transferts de fichiers impliquant le même nom de fichier.  <br/> |
|**Cookie** <br/> |nvarchar (128)  <br/> |Principal  <br/> |Utilisé pour identifier chaque message de suivi comme étant associé à celle-ci.  <br/> |
|**Accepter** <br/> |bit  <br/> ||Peut avoir la valeur TRUE ou NULL. Si TRUE, refuser et annuler sera NULL.  <br/> |
|**Rejeter** <br/> |bit  <br/> ||Peut avoir la valeur TRUE ou NULL. Si la valeur TRUE, puis accepter et annuler sera NULL.  <br/> |
|**Annuler** <br/> |bit  <br/> ||Peut avoir la valeur TRUE ou NULL. Si la valeur TRUE, puis accepter et rejeter sera NULL.  <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ est une nouveauté dans Skype pour Business Server 2015.  <br/> |
   

