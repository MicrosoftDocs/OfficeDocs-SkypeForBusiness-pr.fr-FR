---
title: Configurer les paramètres globaux de contournement de média dans Skype pour 2015 de Server entreprise d’utiliser les informations de site et de la région
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
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Configurer le contournement de média à utiliser uniquement pour certains sites et régions dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: cebfa9d416fe3e68cd5615ae11616707ba1f60a8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-2015-to-use-site-and-region-information"></a>Configurer les paramètres globaux de contournement de média dans Skype pour 2015 de Server entreprise d’utiliser les informations de site et de la région
 
Configurer le contournement de média à utiliser uniquement pour certains sites et régions dans Skype pour Business Server Voix Entreprise. 
  
 Si vous utilisez les étapes décrites dans cette rubrique pour configurer les paramètres globaux pour le média ignorer, l’hypothèse est que vous n’avez pas vérifié la connectivité entre tous les Skype pour les points de terminaison Business et n’importe quel poste pour lequel vous avez configuré le contournement de média sur la connexion de jonction.
  
> [!NOTE]
> Les informations relatives aux régions du réseau et aux sites réseau sont partagées entre les fonctionnalités Voix Entreprise avancées de contrôle d’admission des appels et de déviation du trafic multimédia lorsque ces deux fonctionnalités sont activées. Par conséquent, si vous avez déjà configuré le contrôle d’admission des appels, vous n’avez pas besoin d’effectuer la procédure ci-dessous pour modifier les informations relatives aux sites et aux régions destinées à la déviation du trafic multimédia. Suivez les étapes de cette procédure si vous n’avez pas encore configuré les régions et les sites du réseau pour le contrôle d’admission des appels et si vous souhaitez modifier les paramètres de déviation du trafic multimédia. 
  
Pour contournent les supports pour travailler correctement il faut la cohérence entre un site tel que défini dans le Générateur de topologies et telle qu’elle est définie lorsque vous configurez des zones de réseau et les sites de réseau. Par exemple, si vous disposez d’un site de la succursale que vous avez définie dans le Générateur de topologies comme ayant une passerelle RTPC déployé, puis ce site de la succursale doit être configuré avec une stratégie de Voix Entreprise qui permet aux utilisateurs de site de succursale de leurs appels RTPC routé via le réseau RTPC passerelle sur le site de la succursale.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>Pour configurer les informations relatives aux sites et aux régions pour la déviation du trafic multimédia

1. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.  
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Double-cliquez sur la configuration **Globale** dans le tableau.
    
4. Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer la déviation du trafic multimédia**.
    
5. Cliquez sur **Utiliser la configuration des sites et des régions**.
    
6. Si nécessaire, activez la case à cocher **Activer la déviation pour les sites non mappés**.
    
    > [!NOTE]
    > N’activez cette case à cocher que si des sites de grande taille et des sites de succursale sont associées à la même région, les premiers (par exemple, un grand site central) sans contraintes de bande passante et les seconds avec des contraintes de bande passante. Lorsque vous activez la déviation du trafic pour les sites non mappés, la configuration est rationalisée. Vous ne spécifiez que les sous-réseaux associés aux sites de succursale au lieu d’avoir à spécifier tous les sous-réseaux associés à tous les sites. Nous vous recommandons de ne pas activer cette case à cocher si le contrôle d’admission des appels est activé. 
  
7. Cliquez sur **Valider**.
    
Ensuite, ajoutez les sous-réseaux au site réseau, comme indiqué dans la rubrique [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets). Une fois que vous avez associé tous les sous-réseaux aux sites réseau, le déploiement de la déviation du trafic multimédia est terminé.
> [!IMPORTANT]
> Si vous n’avez pas encore créé de régions et de sites réseau, vous devez les créer pour poursuivre le déploiement de la déviation du trafic multimédia. Pour plus d’informations, consultez [zones de réseau de déployer, des sites et des sous-réseaux dans Skype pour entreprise 2015](deploy-network.md). 
  
## <a name="see-also"></a>Voir aussi

#### 

[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)

