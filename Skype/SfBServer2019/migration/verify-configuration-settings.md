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
ms.localizationpriority: medium
description: Vous pouvez valider la réplication des informations de configuration sur le serveur Edge en exécutant la cmdlet Skype Entreprise Server 2019 Get-CsManagementStoreReplicationStatus sur l’ordinateur interne sur lequel se trouve le magasin central de gestion ou sur tout ordinateur joint à un domaine sur lequel Skype Entreprise Server 2019 Core Components (OcsCore.msi) est installé.
ms.openlocfilehash: ff46dbad696ac4bf200bb669de768a28d0815e1b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594262"
---
# <a name="verify-configuration-settings"></a>Vérifier les paramètres de configuration

Vous pouvez valider la réplication des informations de configuration sur le serveur Edge en exécutant l’cmdlet Skype Entreprise Server 2019 **Get-CsManagementStoreReplicationStatus** sur l’ordinateur interne sur lequel se trouve le magasin central de gestion ou sur tout ordinateur joint à un domaine sur lequel Skype Entreprise Server 2019 Core Components (OcsCore.msi) est installé. 
  
Les résultats initiaux peuvent indiquer le statut de réplication « False » au lieu de « True ». Si tel est le cas, exécutez l’applet de commande **Invoke-CsManagementStoreReplication** pour donner à la réplication le temps nécessaire de se terminer avant de réexécuter **Get-CsManagementStoreReplicationStatus**. 
  

