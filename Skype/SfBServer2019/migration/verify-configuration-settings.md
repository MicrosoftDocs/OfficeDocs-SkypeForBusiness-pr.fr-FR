---
title: Vérifier les paramètres de configuration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez valider la réplication des informations de configuration pour le serveur Edge en exécutant la Skype pour l’applet de commande Business Server 2019 Get-CsManagementStoreReplicationStatus sur l’ordinateur interne sur lequel se trouve le magasin Central de gestion, ou sur tout ordinateur sur lequel est installé Skype pour les composants principaux (OcsCore.msi) de Business Server 2019 joint au domaine.
ms.openlocfilehash: 1b64569ffbdce3d7f41e7f6c54815d051848cfd1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231356"
---
# <a name="verify-configuration-settings"></a>Vérifier les paramètres de configuration

Vous pouvez valider la réplication des informations de configuration pour le serveur Edge en exécutant la Skype pour l’applet de commande Business Server 2019 **Get-CsManagementStoreReplicationStatus** sur l’ordinateur interne sur lequel se trouve le magasin Central de gestion, ou Skype pour les composants principaux (OcsCore.msi) de Business Server 2019 est installé sur tout ordinateur sur lequel liés à un domaine. 
  
Résultats initiale peuvent indiquer l’état en tant que valeur « False » au lieu de la valeur « True » pour la réplication. Dans ce cas, exécutez l’applet de commande **Invoke-CsManagementStoreReplication** et attendez que la réplication soit terminée avant d’exécuter de nouveau la **Get-CsManagementStoreReplicationStatus** . 
  

