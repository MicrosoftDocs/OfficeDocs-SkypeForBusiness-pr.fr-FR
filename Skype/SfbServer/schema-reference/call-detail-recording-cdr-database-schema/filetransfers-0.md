---
title: Table FileTransfers dans Skype Entreprise Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: Chaque enregistrement représente une session de transfert de fichiers.
---

# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Table FileTransfers dans Skype Entreprise Server 2015
 
Chaque enregistrement représente une session de transfert de fichiers.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de la demande de session. Utilisée conjointement avec **SessionIdSeq** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015](dialogs.md). <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’ID pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015](dialogs.md). <br/> |
|**Nom de fichier** <br/> |nvarchar(256)  <br/> ||Nom du fichier.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> ||Identificateur unique permettant de différencier les transferts de fichiers concernant le même nom de fichier.  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |Primaire  <br/> |Utilisé pour identifier chaque message de suivi comme étant associé à celui-ci.  <br/> |
|**Accept** <br/> |bit  <br/> ||Peut-être TRUE ou NULL. Si TRUE, alors Reject et Cancel seront NULL.  <br/> |
|**Reject** <br/> |bit  <br/> ||Peut-être TRUE ou NULL. Si TRUE, alors Accept et Cancel seront NULL.  <br/> |
|**Cancel** <br/> |bit  <br/> ||Peut-être TRUE ou NULL. Si TRUE, alors Accept et Reject seront NULL.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Réservé à un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype Entreprise Server 2015.  <br/> |
   

