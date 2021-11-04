---
title: Configurer les paramètres globaux de contournement de média dans Skype Entreprise Server pour utiliser les informations de site et de région
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Configurez le contournement de média pour qu’il soit utilisé uniquement pour certains sites et régions dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 2d1c10ce06421635783a50bf97286c8d752f478b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741350"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>Configurer les paramètres globaux de contournement de média dans Skype Entreprise Server pour utiliser les informations de site et de région
 
Configurez le contournement de média pour qu’il soit utilisé uniquement pour certains sites et régions dans Skype Entreprise Server Voix Entreprise. 
  
 Si vous utilisez les étapes de cette rubrique pour configurer les paramètres globaux du contournement de média, nous partons du principe que vous n’avez pas une bonne connectivité entre tous les points de terminaison Skype Entreprise et tous les homologues pour lesquels vous avez configuré le contournement de média sur la connexion de liaison.
  
> [!NOTE]
> Les informations relatives aux régions du réseau et aux sites réseau sont partagées entre les fonctionnalités Voix Entreprise avancées de contrôle d’admission des appels et de contournement de média lorsque ces deux fonctionnalités sont activées. Par conséquent, si vous avez déjà configuré le contrôle d’admission des appels, vous n’avez pas besoin d’effectuer la procédure suivante pour modifier les informations relatives aux sites et aux régions destinées au contournement de média. Suivez les étapes de cette procédure si vous n’avez pas encore configuré les régions et les sites du réseau pour le contrôle d’admission des appels et si vous souhaitez modifier les paramètres du contournement de média. 
  
Pour que le contournement de média fonctionne correctement, il doit y avoir une cohérence entre un site tel que défini dans le Générateur de topologie et tel qu’il est défini lorsque vous configurez des régions réseau et des sites réseau. Par exemple, si vous avez un site de succursale que vous avez défini dans le Générateur de topologie comme n’ayant qu’une passerelle PSTN déployée, ce site de succursale doit être configuré avec une stratégie Voix Entreprise qui permet aux utilisateurs de sites de succursale de faire router leurs appels PSTN via la passerelle PSTN sur le site de succursale.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>Pour configurer les informations relatives aux sites et aux régions pour le contournement de média

1. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.  
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Double-cliquez sur la configuration **Globale** dans le tableau.
    
4. Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contournement de média**.
    
5. Cliquez sur **Utiliser la configuration des sites et des régions**.
    
6. Si nécessaire, activez la case à cocher **Activer le contournement pour les sites non mappés**.
    
    > [!NOTE]
    > Activez uniquement cette case à cocher si des sites de grande taille et des sites de succursale sont associées à la même région, les premiers (par exemple, un grand site central) sans contraintes de bande passante et les seconds avec des contraintes de bande passante. Lorsque vous activez le contournement pour les sites non mappés, la configuration est rationalisée. Vous devez uniquement spécifier les sous-réseaux associés aux sites de succursale au lieu de devoir spécifier tous les sous-réseaux associés à tous les sites. Nous vous recommandons de ne pas activer cette case à cocher si le contrôle d’admission des appels est activé. 
  
7. Cliquez sur **Valider**.
    
Ensuite, ajoutez des sous-réseaux au site réseau, comme décrit dans Associer un [sous-réseau à un site réseau.](deploy-network.md#BKMK_AssociateSubnets) Une fois que vous avez associé tous les sous-réseaux aux sites réseau, le déploiement du contournement de média est terminé.
> [!IMPORTANT]
> Si vous n’avez pas encore créé de régions et de sites réseau, vous devez les créer pour pouvoir poursuivre le déploiement du contournement de média. Pour plus d’informations, voir Déployer des régions réseau, des sites et [des sous-réseaux dans Skype Entreprise](deploy-network.md). 
  
## <a name="see-also"></a>Voir aussi

[Associer un sous-réseau à un site réseau](deploy-network.md#BKMK_AssociateSubnets)

