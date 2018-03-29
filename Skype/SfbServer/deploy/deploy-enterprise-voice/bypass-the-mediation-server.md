---
title: Configurer le contournement de média dans Skype pour 2015 de serveur d’entreprise pour toujours ignorer le serveur de médiation
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Activer le contournement de média pour toujours ignorer le serveur de médiation dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 5a7ca70b6f060c9d6a5399934fb784c9247e95fa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-media-bypass-in-skype-for-business-server-2015-to-always-bypass-the-mediation-server"></a>Configurer le contournement de média dans Skype pour 2015 de serveur d’entreprise pour toujours ignorer le serveur de médiation
 
Activer le contournement de média pour toujours ignorer le serveur de médiation dans Skype pour Business Server Voix Entreprise. 
  
 Si vous utilisez les étapes décrites dans cette rubrique pour configurer les paramètres globaux pour support de contournent, il est supposé que vous disposez d’une bonne connectivité entre Skype pour les points de terminaison Professionnel et n’importe quel poste pour lequel vous avez configuré le contournement de média sur la connexion de jonction.
  
Si vous n’avez pas vérifié la connectivité entre Skype pour les points de terminaison Business et tous les homologues sur le serveur de médiation dont les connexions trunk respectifs ont été activées pour le contournement de média, vous devez configurer les paramètres de contournement de média global pour utiliser les informations de site et de la région Lorsque media utilisant bypass. Cela permet davantage de contrôle pour déterminer lorsque media ignore le serveur de médiation. Pour ce faire, utilisez les étapes de [configurer media contourne des paramètres globaux dans Skype pour 2015 de Server entreprise d’utiliser les informations de site et de la région](use-site-and-region-information.md) et [d’associer un sous-réseau à un site de réseau](deploy-network.md#BKMK_AssociateSubnets) à la place.
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Pour activer la déviation du trafic multimédia au niveau global pour qu’il contourne toujours le serveur de médiation

1. Ouvrez Skype pour le panneau de configuration de Business Server.
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Double-cliquez sur la configuration **Globale** dans la liste.
    
4. Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer la déviation du trafic multimédia**.
    
5. Cliquez sur **Toujours ignorer**.
    
6. Cliquez sur **Valider**.
    
## <a name="see-also"></a>Voir aussi

#### 

[Planifier le contournement de média dans Skype pour entreprise 2015](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Déployer le contournement de média dans Skype pour Business Server 2015](deploy-media-bypass.md)

