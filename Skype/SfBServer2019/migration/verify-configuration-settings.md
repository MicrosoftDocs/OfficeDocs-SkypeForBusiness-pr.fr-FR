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
description: Vous pouvez valider la réplication des informations de configuration sur le serveur Edge en exécutant la cmdlet Get-CsManagementStoreReplicationStatus Skype Entreprise Server 2019 sur l’ordinateur interne sur lequel se trouve le magasin central de gestion, ou sur tout ordinateur joint à un domaine sur lequel Skype Entreprise Server 2019 Core Components (OcsCore.msi) est installé.
ms.openlocfilehash: dd270bd54bb427cf3fc74fe0081ef2e383a58589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752146"
---
# <a name="verify-configuration-settings"></a>Vérifier les paramètres de configuration

Vous pouvez valider la réplication des informations de configuration sur le serveur Edge en exécutant l’cmdlet Skype Entreprise Server 2019 **Get-CsManagementStoreReplicationStatus** sur l’ordinateur interne sur lequel se trouve le magasin central de gestion, ou sur tout ordinateur joint à un domaine sur lequel Skype Entreprise Server 2019 Core Components (OcsCore.msi) est installé. 
  
Les résultats initiaux peuvent indiquer le statut de réplication « False » au lieu de « True ». Si tel est le cas, exécutez l’applet de commande **Invoke-CsManagementStoreReplication** pour donner à la réplication le temps nécessaire de se terminer avant de réexécuter **Get-CsManagementStoreReplicationStatus**. 
  

