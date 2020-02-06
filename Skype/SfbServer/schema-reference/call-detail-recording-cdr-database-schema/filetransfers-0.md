---
title: Table FileTransfers dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: Chaque enregistrement représente une session de transfert de fichiers.
ms.openlocfilehash: 8b287d2fc2c40fe7e20cb3abc4ed6e403da701b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815212"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Table FileTransfers dans Skype entreprise Server 2015
 
Chaque enregistrement représente une session de transfert de fichiers.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Etranger principal  <br/> |Durée de la demande de session. Utilisé conjointement avec **SessionIdSeq** pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Etranger principal  <br/> |IDENTIFIant de la session. Utilisé conjointement avec **SessionIdTime** pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**Nom de fichier** <br/> |nvarchar(256)  <br/> ||Nom du fichier.  <br/> |
|**FileIdentity** <br/> |identificateur  <br/> ||Identificateur unique permettant de faire la distinction entre les transferts de fichiers impliquant le même nom de fichier.  <br/> |
|**Sans** <br/> |nvarchar(128  <br/> |Principal  <br/> |Permet de détecter chaque message de suivi associé à celui-ci.  <br/> |
|**Valide** <br/> |bit  <br/> ||Peut être vrai ou nul. Si vrai, l’argument refuser et annuler est nul.  <br/> |
|**Rejeter** <br/> |bit  <br/> ||Peut être vrai ou nul. Si vrai, l’argument accepter et annuler est nul.  <br/> |
|**Annuler** <br/> |bit  <br/> ||Peut être vrai ou nul. Si vrai, l’argument accepter et refuser est nul.  <br/> |
|**LastModifiedTime** <br/> |Valeur  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ a été présenté dans Skype entreprise Server 2015.  <br/> |
   

