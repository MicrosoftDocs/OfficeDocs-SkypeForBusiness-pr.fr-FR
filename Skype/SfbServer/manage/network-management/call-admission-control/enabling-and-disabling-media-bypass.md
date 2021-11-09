---
title: Activation et désactivation du contournement de média
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Utilisez les procédures de cet article pour activer ou désactiver le contournement de média à l’aide du Skype Entreprise Server de contrôle.
ms.openlocfilehash: e8465d376e32d677d52cb0bdb57e86d9aa9fac44
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851998"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>Activation et désactivation du contournement de média dans Skype Entreprise Server

Utilisez les procédures de cet article pour activer ou désactiver le contournement de média à l’aide du Skype Entreprise Server de contrôle.

## <a name="enable-network-media-bypass"></a>Activer le contournement de média réseau 

Les paramètres de déviation du média s’appliquent globalement à un déploiement Skype Entreprise Server de média. La déviation du média permet aux appels de contourner le serveur de médiation. Pour plus d’informations sur l’utilisation du contournement de média, voir [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

Vous pouvez activer et configurer le contournement de média à partir Skype Entreprise Server panneau de configuration.


### <a name="to-enable-and-configure-media-bypass"></a>Pour activer et configurer le contournement de média

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Global**.

4.  Dans la page **Globale**, cliquez sur la configuration **Globale**. Il n’existe toujours qu’une seule configuration, qui se nomme toujours Globale.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier les paramètres globaux,** activez la case à cocher Activer le **contournement de** média.

7.  Sélectionnez l’une des options suivantes :
    
      - **Toujours ignorer**   Sélectionnez cette option pour tenter le contournement de média sur tous les appels. Cette option n’est pas disponible si le contrôle d’admission des appels est activé. Si cac n’est pas activé, sélectionnez cette option dans les situations suivantes :
        
          - Il n’est pas nécessaire de contrôler la bande passante.
        
          - La configuration fine n’est pas nécessaire pour déterminer quand le contournement doit se produire.
        
          - Il existe une connectivité complète entre les passerelles et les clients.
    
      - **Utiliser la configuration des sites et des régions**   Si le cac est activé, cette option est sélectionnée par défaut et ne peut pas être modifiée. Lorsque cette option est sélectionnée, les sites et régions de configuration réseau sont utilisés pour déterminer quand le contournement de média est possible. Si vous sélectionnez cette option, vous pouvez choisir d’activer le contournement pour les sites qui ne sont pas mappés. Cliquez sur la case à cocher Activer le contournement pour les **sites non** mappés uniquement si vous avez un ou plusieurs sites de grande taille associés à la même région qui n’ont pas de contraintes de bande passante (par exemple, un site central de grande taille) et si certains sites de succursale associés à la même région ont des contraintes de bande passante. Lorsque vous activez le contournement pour les sites non mappés, la configuration est simplifiée, car vous spécifiez uniquement les sous-réseaux associés aux sites de succursale au lieu de devoir spécifier tous les sous-réseaux associés à tous les sites. Nous vous recommandons de ne pas activer la case à cocher Activer le contournement pour les **sites non** mappés si le contrôle d’enregistrement des contrôles d’enregistrement est activé.

8.  Cliquez sur **OK** pour enregistrer vos modifications.


## <a name="disable-network-media-bypass"></a>Désactiver le contournement de média réseau

Les paramètres de déviation du média s’appliquent globalement à un déploiement Skype Entreprise Server de média. La déviation du média permet aux appels de contourner le serveur de médiation. Pour plus d’informations sur l’utilisation du contournement de média, voir [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). Vous pouvez désactiver le contournement de média à partir du Panneau Skype Entreprise Server de contrôle. 


### <a name="to-disable-media-bypass"></a>Pour désactiver le contournement de média

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Global**.

4.  Dans la page **Globale**, cliquez sur la configuration **Globale**. Il n’existe toujours qu’une seule configuration, qui se nomme toujours Globale.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier la configuration globale**, décochez la case **Activer le contournement de média**.

7.  Cliquez sur **OK** pour enregistrer vos modifications.

  
