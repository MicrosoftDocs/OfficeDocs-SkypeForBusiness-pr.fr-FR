---
title: Correctif ou de mise à jour d’un SQL Server dans un groupe de disponibilité AlwaysOn dans Skype pour Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7298254b-bc33-450e-846a-2612f6dc7006
description: 'Résumé : Découvrez les étapes supplémentaires nécessaires après vous correctif ou mise à niveau d’un serveur principal qui fait partie d’un groupe de disponibilité AlwaysOn dans Skype pour Business Server.'
ms.openlocfilehash: 8f5c9131e59ccedd7f590f696fe53aa6c18c7d22
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group-in-skype-for-business-server-2015"></a>Correctif ou de mise à jour d’un SQL Server dans un groupe de disponibilité AlwaysOn dans Skype pour Business Server 2015
 
**Résumé :** Découvrez les étapes supplémentaires nécessaires après correctif ou la mise à niveau d’un serveur principal qui fait partie d’un groupe de disponibilité AlwaysOn dans Skype pour Business Server.
  
Après application du correctif un serveur principal qui fait partie d’un groupe de disponibilité AlwaysOn, vous devez republier la topologie.
  
### <a name="patching-or-updating-a-sql-server-that-is-part-of-an-alwayson-availability-group"></a>Application de correctifs ou de mise à jour d’un SQL Server qui fait partie d’un groupe de disponibilité AlwaysOn

1. Installez la mise à jour sur votre Skype pour les entreprises ou les serveurs.
    
2. Exécutez la commande PowerShell suivante dans votre Skype pour Business Management Shell (connecté avec un compte qui est correctement autorisé à appliquer les modifications aux bases de données SQL AlwaysOn) comme suit :
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Où [sqlpool.contoso.com] est remplacé par le nom de domaine pleinement qualifié (FQDN) de votre groupe de disponibilité AlwaysOn.
    

