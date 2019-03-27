---
title: Activation et désactivation du contournement de média
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Utilisez les procédures décrites dans cet article pour activer ou désactiver le contournement de média à l’aide de la Skype pour le panneau de configuration serveur Business.
ms.openlocfilehash: eebbc111f0d205be8dced9ec8ddb5150deff8119
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874285"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>Activation et désactivation du contournement de média dans Skype Entreprise Server

Utilisez les procédures décrites dans cet article pour activer ou désactiver le contournement de média à l’aide de la Skype pour le panneau de configuration serveur Business.

## <a name="enable-network-media-bypass"></a>Activer le contournement de média réseau 

Paramètres de déviation du trafic multimédia s’appliquent globalement un Skype pour le déploiement de serveur d’entreprise. Le contournement de média autorise les appels à ignorer le serveur de médiation. Pour plus d’informations sur l’utilisation de Media contournement de média, voir [Plan pour le média de contournement](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

Vous pouvez activer et configurer le contournement de média à partir de la Skype pour le panneau de configuration serveur Business.


### <a name="to-enable-and-configure-media-bypass"></a>Pour activer et configurer le contournement de média

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Global**.

4.  Dans la page **globale** , cliquez sur la configuration **globale** . Il y a toujours qu’une seule configuration, et il est toujours nommé Global.

5.  Dans le menu **Edition** , cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier la configuration globale** , cliquez sur la case à cocher **Activer le contournement de média** .

7.  Sélectionnez une des options suivantes :
    
      - **Toujours contourner**   Sélectionnez cette option pour essayer de médias contournement de média sur tous les appels. Cette option n’est pas disponible si le contrôle d’admission des appels (CAC) est activé. Si CAC n’est pas activé, sélectionnez cette option dans les situations suivantes :
        
          - Il n’est pas nécessaire de contrôler la bande passante.
        
          - Il n’est pas nécessaire d’affiner la configuration déterminer si la déviation doit avoir lieu.
        
          - Connectivité est complète entre passerelles et clients.
    
      - **Utiliser les sites et la configuration de la zone**   si CAC est activé, cette option est sélectionnée par défaut et ne peut pas être modifiée. Lorsque cette option est sélectionnée, sites de configuration réseau et les régions seront utilisées pour déterminer quand le contournement de média est possible. Si vous sélectionnez cette option, vous pouvez choisir d’activer le contournement de média pour les sites qui ne sont pas associés. Cliquez sur la case à cocher **Activer le contournement de média pour les sites non mappés** uniquement si vous avez un ou plusieurs sites de grande taille associés à la même région qui n’ont pas de contraintes de bande passante (par exemple, un site central volumineux) et vous avez également certains sites de succursale associés à la zone qui ont des contraintes de bande passante. Lorsque vous activez le contournement de média pour les sites non mappés, configuration est simple puisque vous spécifiez uniquement les sous-réseaux associés avec les sites de succursale, plutôt que d’avoir à spécifier tous les sous-réseaux associés à tous les sites. Il est recommandé que vous ne sélectionnez pas la case à cocher **Activer le contournement de média pour les sites non mappés** si CAC est activé.

8.  Cliquez sur **Valider** pour enregistrer vos modifications.


## <a name="disable-network-media-bypass"></a>Désactiver le contournement de média réseau

Paramètres de déviation du trafic multimédia s’appliquent globalement un Skype pour le déploiement de serveur d’entreprise. Le contournement de média autorise les appels à ignorer le serveur de médiation. Pour plus d’informations sur l’utilisation de Media contournement de média, voir [Plan pour le média de contournement](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). Vous pouvez désactiver le contournement de média à partir de la Skype pour le panneau de configuration serveur Business. 


### <a name="to-disable-media-bypass"></a>Pour désactiver le contournement de média

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Global**.

4.  Dans la page **globale** , cliquez sur la configuration **globale** . Il y a toujours qu’une seule configuration, et il est toujours nommé Global.

5.  Dans le menu **Edition** , cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier la configuration globale** , désactivez la case à cocher **Activer le contournement de média** .

7.  Cliquez sur **Valider** pour enregistrer vos modifications.

  
