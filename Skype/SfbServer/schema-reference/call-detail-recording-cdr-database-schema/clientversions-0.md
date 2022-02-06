---
title: Affichage ClientVersions
ms.reviewer: null
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: L’affichage ClientVersions stocke des informations sur les différents types et versions de clients qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de l’affichage représente une version du client. Cette vue a été introduite dans Microsoft Lync Server 2013.
---

# <a name="clientversions-view"></a>Affichage ClientVersions
 
L’affichage ClientVersions stocke des informations sur les différents types et versions de clients qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de l’affichage représente une version du client. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
> [!NOTE]
> Il peut y avoir plusieurs enregistrements pour certaines colonnes. 
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |Numéro unique identifiant le type et la version de ce client.  <br/> |
|**Version** <br/> |nvarchar(256)  <br/> |Représente l’agent utilisateur.  <br/> |
|**ClientType** <br/> |int  <br/> |Type de client.  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Catégorie à qui appartient le client. Par exemple, le client Conferencing_Attendant_1.0 appartient à l’ACA ClientCategory.  <br/> |
   

