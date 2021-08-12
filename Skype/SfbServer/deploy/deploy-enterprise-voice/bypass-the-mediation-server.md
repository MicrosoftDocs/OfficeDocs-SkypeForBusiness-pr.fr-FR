---
title: Configurer le contournement de média dans Skype Entreprise Server pour toujours contourner le serveur de médiation
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Activez la déviation du média pour qu’elle contourne toujours le serveur de médiation dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: c80b3479546e9154480af8f71417b5ebce43b261510eec19332ecf1cf9287bc4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310029"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Configurer le contournement de média dans Skype Entreprise Server pour toujours contourner le serveur de médiation
 
Activez la déviation du média pour qu’elle contourne toujours le serveur de médiation dans Skype Entreprise Server Voix Entreprise. 
  
 Si vous utilisez les étapes de cette rubrique pour configurer les paramètres globaux du contournement de média, nous partons du principe que vous avez une bonne connectivité entre les points de terminaison Skype Entreprise et tout homologue pour lequel vous avez configuré le contournement de média sur la connexion de liaison.
  
Si vous n’avez pas une bonne connectivité entre les points de terminaison Skype Entreprise et tous les homologues du serveur de médiation dont les connexions de liaison respectives ont été activées pour le contournement de média, vous devez configurer les paramètres globaux de déviation du média pour utiliser les informations de site et de région lors de l’utilisation du contournement de média. Cela permet de déterminer plus précisément le moment auquel le média contourne le serveur de médiation. Pour ce faire, utilisez les étapes de configuration des [paramètres](use-site-and-region-information.md) globaux de déviation du média dans Skype Entreprise Server pour utiliser les informations de site et de région et associer un sous-réseau à un [site](deploy-network.md#BKMK_AssociateSubnets) réseau à la place.
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Pour activer le contournement de média au niveau global pour qu’il contourne toujours le serveur de médiation

1. Ouvrez Skype Entreprise Server panneau de contrôle.
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Double-cliquez sur la configuration **Globale** dans la liste.
    
4. Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contournement de média**.
    
5. Cliquez sur **Toujours ignorer**.
    
6. Cliquez sur **Valider**.
    
## <a name="see-also"></a>Voir aussi

[Planifier le contournement de média dans Skype Entreprise](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Déployer le contournement de média dans Skype Entreprise Server](deploy-media-bypass.md)

