---
title: Vérifier les paramètres de configuration
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Vous pouvez valider la réplication des informations de configuration sur le serveur Edge en exécutant la cmdlet Skype Entreprise Server 2019 Get-CsManagementStoreReplicationStatus sur l’ordinateur interne sur lequel se trouve le magasin central de gestion ou sur tout ordinateur joint à un domaine sur lequel Skype Entreprise Server 2019 Core Components (OcsCore.msi) est installé.
ms.openlocfilehash: e681781598af876f722094b0191aa784da2c533adc509a9f9fc4fad96fa4db4c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335744"
---
# <a name="verify-configuration-settings"></a>Vérifier les paramètres de configuration

Vous pouvez valider la réplication des informations de configuration sur le serveur Edge en exécutant l’cmdlet Skype Entreprise Server 2019 **Get-CsManagementStoreReplicationStatus** sur l’ordinateur interne sur lequel se trouve le magasin central de gestion ou sur tout ordinateur joint à un domaine sur lequel Skype Entreprise Server 2019 Core Components (OcsCore.msi) est installé. 
  
Les résultats initiaux peuvent indiquer le statut de réplication « False » au lieu de « True ». Si tel est le cas, exécutez l’applet de commande **Invoke-CsManagementStoreReplication** pour donner à la réplication le temps nécessaire de se terminer avant de réexécuter **Get-CsManagementStoreReplicationStatus**. 
  

