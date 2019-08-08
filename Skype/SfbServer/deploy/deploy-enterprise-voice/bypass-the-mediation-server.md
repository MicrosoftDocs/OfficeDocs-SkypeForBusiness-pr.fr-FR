---
title: Configurer l’exclusion de médias dans Skype entreprise Server pour ignorer toujours le serveur de médiation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Activez le contournement multimédia pour ignorer toujours le serveur de médiation dans Skype entreprise Server Voice.
ms.openlocfilehash: dfffda1130fc1fb119e6cbf5d9b12af766b9c038
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233836"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Configurer l’exclusion de médias dans Skype entreprise Server pour ignorer toujours le serveur de médiation
 
Activez le contournement multimédia pour ignorer toujours le serveur de médiation dans Skype entreprise Server Voice. 
  
 Si vous suivez les étapes décrites dans cette rubrique pour configurer des paramètres globaux pour le contournement du média multimédia, il est supposé que vous disposez d’une bonne connectivité entre les points de terminaison Skype entreprise et les homologues pour lesquels vous avez configuré une contournement multimédia sur la connexion Trunk.
  
Si vous n’avez pas de bonne connectivité entre les points de terminaison Skype entreprise et tous les homologues sur le serveur de médiation pour lesquels une connexion de ligne respective a été activée pour la dérivation de média, vous devez configurer des paramètres globaux de contournement de médias pour utiliser les informations relatives au site et à la région. lors de l’utilisation d’une dérivation de média. Cela permet d’augmenter le contrôle lors du contournement du serveur de médiation par le média. Pour cela, suivez les étapes décrites dans l’article [configurer les paramètres globaux de contournement de médias dans Skype entreprise Server pour utiliser les informations sur les sites et les régions](use-site-and-region-information.md) et [associer un sous-réseau à un site réseau](deploy-network.md#BKMK_AssociateSubnets) .
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Pour activer la déviation du trafic multimédia au niveau global pour qu’il contourne toujours le serveur de médiation

1. Ouvrez le panneau de configuration Skype entreprise Server.
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Double-cliquez sur la configuration **Globale** dans la liste.
    
4. Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer la déviation du trafic multimédia**.
    
5. Cliquez sur **Toujours ignorer**.
    
6. Cliquez sur **Valider**.
    
## <a name="see-also"></a>Voir aussi

[Plan de contournement de médias dans Skype entreprise](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Déploiement du contournement multimédia dans Skype entreprise Server](deploy-media-bypass.md)

