---
title: Configurer les paramètres globaux de contournement de médias dans Skype entreprise Server pour utiliser les informations de site et de région
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
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Configurez la dérivation de médias à utiliser pour certains sites et régions dans Skype entreprise Server voix entreprise.
ms.openlocfilehash: 3bfb3dca6e53316d5c1de71abad976ae9223c787
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240043"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>Configurer les paramètres globaux de contournement de médias dans Skype entreprise Server pour utiliser les informations de site et de région
 
Configurez la dérivation de médias à utiliser pour certains sites et régions dans Skype entreprise Server voix entreprise. 
  
 Si vous suivez les étapes décrites dans cette rubrique pour configurer des paramètres globaux pour le contournement du média multimédia, il est supposé que vous ne disposez pas d’une bonne connectivité entre tous les points de terminaison Skype entreprise et les homologues pour lesquels vous avez configuré une contournement multimédia sur la connexion Trunk.
  
> [!NOTE]
> Les informations relatives aux régions du réseau et aux sites réseau sont partagées entre les fonctionnalités Voix Entreprise avancées de contrôle d’admission des appels et de déviation du trafic multimédia lorsque ces deux fonctionnalités sont activées. Par conséquent, si vous avez déjà configuré le contrôle d’admission des appels, vous n’avez pas besoin d’effectuer la procédure ci-dessous pour modifier les informations relatives aux sites et aux régions destinées à la déviation du trafic multimédia. Suivez les étapes de cette procédure si vous n’avez pas encore configuré les régions et les sites du réseau pour le contrôle d’admission des appels et si vous souhaitez modifier les paramètres de déviation du trafic multimédia. 
  
Pour le bon fonctionnement du contournement de médias, il doit exister une cohérence entre un site défini dans le générateur de topologie et tel qu’il est défini lorsque vous configurez des régions réseau et des sites réseau. Par exemple, si vous disposez d’un site de succursale que vous avez défini dans le générateur de topologie comme ayant uniquement une passerelle RTC déployée, ce site de succursale doit être configuré avec une stratégie vocale d’entreprise permettant aux utilisateurs du site de succursale d’avoir leurs appels RTC via le RTC. passerelle sur le site de la succursale.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>Pour configurer les informations relatives aux sites et aux régions pour la déviation du trafic multimédia

1. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.  
    
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
> Si vous n’avez pas encore créé de régions et de sites réseau, vous devez les créer pour poursuivre le déploiement de la déviation du trafic multimédia. Pour plus d’informations, reportez-vous à la rubrique [déploiement de régions, de sites et de sous-réseaux dans Skype entreprise](deploy-network.md). 
  
## <a name="see-also"></a>Voir aussi

[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)

