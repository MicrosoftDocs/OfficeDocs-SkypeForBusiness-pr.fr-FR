---
title: Activation et désactivation de la déviation du trafic multimédia
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Utilisez les procédures décrites dans cet article pour activer ou désactiver le contournement multimédia à l’aide de la Skype Entreprise Server Panneau de configuration.
ms.openlocfilehash: 38ec29c6e4b51a4c6898b13c4de0172f55947907
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675336"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>Activation et désactivation du contournement de média dans Skype Entreprise Server

Utilisez les procédures décrites dans cet article pour activer ou désactiver le contournement multimédia à l’aide de la Skype Entreprise Server Panneau de configuration.

## <a name="enable-network-media-bypass"></a>Activer la déviation du trafic multimédia réseau 

Les paramètres de contournement du média s’appliquent globalement à un déploiement Skype Entreprise Server. La déviation du trafic multimédia permet aux appels de contourner le serveur de médiation. Pour plus d’informations sur l’utilisation de la déviation du trafic multimédia, consultez [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

Vous pouvez activer et configurer la déviation du trafic multimédia à partir du Skype Entreprise Server Panneau de configuration.


### <a name="to-enable-and-configure-media-bypass"></a>Pour activer et configurer le contournement du média

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL Administration pour ouvrir le Skype Entreprise Server Panneau de configuration. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Global**.

4.  Dans la page **Globale**, cliquez sur la configuration **Globale**. Il n’existe toujours qu’une seule configuration, qui se nomme toujours Globale.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier le paramètre global** , cliquez sur la case à cocher **Activer le contournement du média** .

7.  Sélectionnez l’une des options suivantes :
    
      - **Toujours contourner**   Sélectionnez cette option pour tenter de contourner le trafic multimédia sur tous les appels. Cette option n’est pas disponible si le contrôle d’admission des appels (CAC) est activé. Si l’option CAC n’est pas activée, sélectionnez cette option dans les situations suivantes :
        
          - Il n’est pas nécessaire de contrôler la bande passante.
        
          - Il n’est pas nécessaire d’avoir une configuration affinée pour déterminer quand le contournement doit se produire.
        
          - Il existe une connectivité complète entre les passerelles et les clients.
    
      - **Utiliser des sites et la configuration de région**   Si cac est activé, cette option est sélectionnée par défaut et ne peut pas être modifiée. Lorsque cette option est sélectionnée, les sites de configuration réseau et les régions sont utilisés pour déterminer quand la déviation du trafic multimédia est possible. Si vous sélectionnez cette option, vous pouvez choisir d’activer le contournement pour les sites qui ne sont pas mappés. Activez la case à cocher **Activer le contournement pour les sites non mappés** uniquement si vous avez un ou plusieurs sites volumineux associés à la même région qui n’ont pas de contraintes de bande passante (par exemple, un site central volumineux) et si certains sites de branche sont associés à la même région que celles qui ont des contraintes de bande passante. Lorsque vous activez le contournement pour les sites non mappés, la configuration est rationalisée, car vous spécifiez uniquement les sous-réseaux associés aux sites de branche au lieu de devoir spécifier tous les sous-réseaux associés à tous les sites. Nous vous recommandons de ne pas cocher la case **Activer le contournement pour les sites non mappés** si l’option CAC est activée.

8.  Cliquez sur **OK** pour enregistrer vos modifications.


## <a name="disable-network-media-bypass"></a>Désactiver le contournement du média réseau

Les paramètres de contournement du média s’appliquent globalement à un déploiement Skype Entreprise Server. La déviation du trafic multimédia permet aux appels de contourner le serveur de médiation. Pour plus d’informations sur l’utilisation de la déviation du trafic multimédia, consultez [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). Vous pouvez désactiver la déviation du trafic multimédia à partir du Skype Entreprise Server Panneau de configuration. 


### <a name="to-disable-media-bypass"></a>Pour désactiver le contournement de média

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL Administration pour ouvrir le Skype Entreprise Server Panneau de configuration. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Global**.

4.  Dans la page **Globale**, cliquez sur la configuration **Globale**. Il n’existe toujours qu’une seule configuration, qui se nomme toujours Globale.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier la configuration globale**, décochez la case **Activer le contournement de média**.

7.  Cliquez sur **OK** pour enregistrer vos modifications.

  
