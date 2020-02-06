---
title: Activation et désactivation de la contournement du contenu multimédia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Suivez les procédures décrites dans cet article pour activer ou désactiver la contournement du contenu multimédia à l’aide du panneau de configuration Skype entreprise Server.
ms.openlocfilehash: d1c0a5eb409c6bb5c07c530b4799ab8a53a9fddb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817543"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>Activation et désactivation du contournement de média dans Skype Entreprise Server

Suivez les procédures décrites dans cet article pour activer ou désactiver la contournement du contenu multimédia à l’aide du panneau de configuration Skype entreprise Server.

## <a name="enable-network-media-bypass"></a>Activer la dérivation de média réseau 

Les paramètres de contournement de média s’appliquent à un déploiement global de Skype entreprise Server. Bypass Media accepte les appels pour ignorer le serveur de médiation. Pour plus d’informations sur l’utilisation du contournement du contenu multimédia, voir [planifier la dérivation de médias](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

Vous pouvez activer et configurer le contournement multimédia dans le panneau de configuration Skype entreprise Server.


### <a name="to-enable-and-configure-media-bypass"></a>Pour activer et configurer le contournement multimédia

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **Global**.

4.  Dans la page **Global** , cliquez sur configuration **globale** . Il n’y a toujours qu’une seule configuration et elle est toujours nommée global.

5.  Dans le menu **édition** , cliquez sur **afficher les détails**.

6.  Dans la page **modifier le paramètre global** , activez la case à cocher **activer le contournement du contenu multimédia** .

7.  Sélectionnez l’une des options suivantes :
    
      - **Toujours ignorer**   sélectionnez cette option pour essayer la dérivation multimédia sur tous les appels. Cette option n’est pas disponible si le contrôle d’admission des appels (CAC) est activé. Si le CAC n’est pas activé, sélectionnez cette option dans les situations suivantes :
        
          - Le contrôle de la bande passante n’est pas nécessaire.
        
          - Il n’est pas nécessaire de disposer d’une configuration précise pour déterminer le moment où un contournement se produit.
        
          - Il existe une connectivité complète entre les passerelles et les clients.
    
      - **Utiliser la configuration**   des sites et des régions si le CAC est activé, cette option est activée par défaut et ne peut pas être modifiée. Lorsque cette option est sélectionnée, les sites et les régions de configuration réseau sont utilisés pour déterminer à quel moment une dérivation de média est possible. Si vous sélectionnez cette option, vous pouvez choisir d’activer le contournement pour les sites qui ne sont pas mappés. Activez la case à cocher **activer le contournement pour les sites non mappés** uniquement si vous avez un ou plusieurs sites de grande taille associés à la même région qui n’ont pas de contraintes de bande passante (par exemple, un site central de grande taille) et si des sites de succursales sont également associés à la même région qui comporte des contraintes de bande passante. Lorsque vous activez le contournement pour les sites non mappés, la configuration est simplifiée, car vous spécifiez uniquement les sous-réseaux associés aux sites de succursale plutôt que d’indiquer tous les sous-réseaux associés à tous les sites. Nous vous recommandons de ne pas activer la case à cocher **activer le contournement pour les sites non mappés** si le CAC est activé.

8.  Cliquez sur **valider** pour enregistrer vos modifications.


## <a name="disable-network-media-bypass"></a>Désactiver le contournement de média réseau

Les paramètres de contournement de média s’appliquent à un déploiement global de Skype entreprise Server. Bypass Media accepte les appels pour ignorer le serveur de médiation. Pour plus d’informations sur l’utilisation du contournement du contenu multimédia, voir [planifier la dérivation de médias](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). Vous pouvez désactiver la dérivation multimédia du panneau de configuration Skype entreprise Server. 


### <a name="to-disable-media-bypass"></a>Pour désactiver la dérivation multimédia

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **Global**.

4.  Dans la page **Global** , cliquez sur configuration **globale** . Il n’y a toujours qu’une seule configuration et elle est toujours nommée global.

5.  Dans le menu **édition** , cliquez sur **afficher les détails**.

6.  Dans la page **modifier le paramètre global** , décochez la case **activer le contournement multimédia** .

7.  Cliquez sur **valider** pour enregistrer vos modifications.

  
