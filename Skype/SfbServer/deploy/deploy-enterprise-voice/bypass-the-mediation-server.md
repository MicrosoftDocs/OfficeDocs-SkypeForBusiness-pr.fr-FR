---
title: Configurer le contournement de média dans Skype pour le serveur d’entreprise pour toujours contourner le serveur de médiation
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Activer le contournement de média pour toujours contourner le serveur de médiation dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 2671a4df1b7c068e650cba35be6409f97b8682f8
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881853"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Configurer le contournement de média dans Skype pour le serveur d’entreprise pour toujours contourner le serveur de médiation
 
Activer le contournement de média pour toujours contourner le serveur de médiation dans Skype pour Business Server Enterprise Voice. 
  
 Si vous utilisez les étapes décrites dans cette rubrique pour configurer les paramètres globaux pour le média de contournement, il est supposé que vous avez vérifié la connectivité entre Skype pour systèmes d’extrémité Business et un homologue pour lequel vous avez configuré le contournement de média sur la connexion de jonction.
  
Si vous n’avez pas vérifié la connectivité entre Skype pour systèmes d’extrémité Business et tous les homologues au serveur de médiation dont connexions de jonction respectifs ont été activées pour le contournement de média, vous devez configurer les paramètres de déviation du trafic multimédia globale pour utiliser les informations de site et de région Lorsque utilisant le contournement de média. Ainsi, pour plus de déterminer quand média contourne le serveur de médiation. Pour ce faire, utilisez les étapes décrites dans [les paramètres globaux dans Skype pour Business Server utilise des informations de site et de la région du contournement de média de configurer](use-site-and-region-information.md) et [d’associer un sous-réseau à un site réseau](deploy-network.md#BKMK_AssociateSubnets) .
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Pour activer la déviation du trafic multimédia au niveau global pour qu’il contourne toujours le serveur de médiation

1. Ouvrez le panneau de configuration serveur Business Skype.
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Double-cliquez sur la configuration **Globale** dans la liste.
    
4. Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer la déviation du trafic multimédia**.
    
5. Cliquez sur **Toujours ignorer**.
    
6. Cliquez sur **Valider**.
    
## <a name="see-also"></a>Voir aussi

[Planification du contournement de média dans Skype pour les entreprises](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Déployer le contournement de média dans Skype pour Business Server](deploy-media-bypass.md)

