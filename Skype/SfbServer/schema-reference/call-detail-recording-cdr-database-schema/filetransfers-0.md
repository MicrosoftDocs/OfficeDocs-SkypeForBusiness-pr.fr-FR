---
title: Table FileTransfers dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 3ca1386919027e7f64444014f3569a2c4251e0ad7dbef79484eb812dc33eabf5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54334806"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Table FileTransfers dans Skype Entreprise Server 2015
 
Chaque enregistrement représente une session de transfert de fichiers.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de la demande de session. Utilisée conjointement avec **SessionIdSeq** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’ID pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**Nom de fichier** <br/> |nvarchar(256)  <br/> ||Nom du fichier.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> ||Identificateur unique permettant de différencier les transferts de fichiers concernant le même nom de fichier.  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |Primaire  <br/> |Utilisé pour identifier chaque message de suivi comme étant associé à celui-ci.  <br/> |
|**Accept** <br/> |bit  <br/> ||Peut-être TRUE ou NULL. Si TRUE, alors Reject et Cancel seront NULL.  <br/> |
|**Rejeter** <br/> |bit  <br/> ||Peut-être TRUE ou NULL. Si TRUE, alors Accept et Cancel seront NULL.  <br/> |
|**Cancel** <br/> |bit  <br/> ||Peut-être TRUE ou NULL. Si TRUE, alors Accept et Reject seront NULL.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Réservé à un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype Entreprise Server 2015.  <br/> |
   

