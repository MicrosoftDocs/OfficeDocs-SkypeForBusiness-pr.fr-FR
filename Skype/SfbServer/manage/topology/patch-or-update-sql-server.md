---
title: Correctifs ou mise à jour de SQL Server dans un groupe de disponibilité AlwaysOn dans Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7298254b-bc33-450e-846a-2612f6dc7006
description: 'Résumé : Découvrez les étapes supplémentaires nécessaires après correctifs ou mise à niveau d’un serveur principal qui fait partie d’un groupe de disponibilité AlwaysOn dans Skype pour Business Server.'
ms.openlocfilehash: 7227bdc61e7accbdd6f6e760e1a33d9a2b76eb30
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20982985"
---
# <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group-in-skype-for-business-server"></a>Correctifs ou mise à jour de SQL Server dans un groupe de disponibilité AlwaysOn dans Skype pour Business Server
 
**Résumé :** Découvrez les étapes supplémentaires après avoir des correctifs ou mise à niveau d’un serveur principal qui fait partie d’un groupe de disponibilité AlwaysOn dans Skype pour Business Server.
  
Après la mise à jour d’un serveur principal qui fait partie d’un groupe de disponibilité AlwaysOn, vous devez republier la topologie.
  
### <a name="patching-or-updating-a-sql-server-that-is-part-of-an-alwayson-availability-group"></a>Mise à jour corrective ou la mise à jour de SQL Server qui fait partie d’un groupe de disponibilité AlwaysOn

1. Installez la mise à jour sur votre Skype pour l’entreprise ou les serveurs.
    
2. Exécutez la commande PowerShell suivante dans votre Skype pour Business Management Shell (connecté avec un compte qui est correctement autorisé à appliquer les modifications apportées aux bases de données SQL AlwaysOn) comme suit :
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Où [sqlpool.contoso.com] est remplacé par le nom de domaine complet (FQDN) de votre groupe de disponibilité AlwaysOn.
    

