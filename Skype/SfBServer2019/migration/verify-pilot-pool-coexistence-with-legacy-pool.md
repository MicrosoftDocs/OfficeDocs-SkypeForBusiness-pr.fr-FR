---
title: Vérifier la coexistence du pool pilote avec le pool hérité
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Processus pour vérifier la coexistence du pool pilote avec le pool hérité.
ms.openlocfilehash: 717726acd3654abb2296d622afc5a4d45009430e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028690"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Vérifier la coexistence du pool pilote avec le pool hérité

 **Dans cet article**
  
[Vérifiez que Skype pour Business Server 2019 services ont démarré](#sectionSection0)
  
[Ouvrez le Skype pour Business Server 2019 le panneau de configuration](#sectionSection1)
  
[Ne pas essayer d’ouvrir la topologie dans le Générateur de topologie hérité](#sectionSection2)
  
Après avoir déployé le pool pilote, vous devez vérifier la coexistence des deux pools en utilisant les outils d’administration pour afficher les informations de pool. Pour Skype pour Business Server 2019 pools et les pools hérités, vous devez utiliser le Skype des outils Business Server 2019 le panneau de configuration et le Générateur de topologie. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Vérifiez que Skype pour Business Server 2019 services ont démarré
<a name="sectionSection0"> </a>

1. Skype pour Business Server 2019 serveur frontal, accédez à l’applet outils d’administration.
    
2. Vérifiez que les services suivants sont en cours d’exécution sur le serveur frontal :

    - Agent du service de journalisation centralisée
    - Partage d’application
    - Service de Test audio
    - Conférence audio/vidéo
    - parcage d’appel
    - Annonce de conférence
    - Intendant Conférence
    - Frontal
    - Conférence par messagerie instantanée
    - Serveur(s)
    - Agent réplicateur de réplica
    - Response Group
    - Conférence web
    - Traduction de la passerelle XMPP

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Ouvrez le Skype pour Business Server 2019 le panneau de configuration
<a name="sectionSection1"> </a>

Dans le serveur frontal dans votre Skype pour le déploiement de Business Server 2019, ouvrez le Skype pour Business Server 2019 le panneau de configuration, puis sélectionnez le pool hérité. Répétez la procédure pour ouvrir le Skype pour Business Server 2019 pool.
  
> [!IMPORTANT]
> Sur Skype pour Business Server 2019, vous devez mettre à niveau Silverlight vers Silverlight 5 avant d’utiliser le Skype pour le panneau de configuration serveur Business. 
  
Cette topologie inclut désormais hérité et Skype pour les rôles de serveur Business Server 2019. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>Ne pas essayer d’ouvrir la topologie dans le Générateur de topologie hérité
<a name="sectionSection2"> </a>

Si vous essayez d’ouvrir la topologie à l’aide du Générateur de topologie hérité, vous rencontrerez l’erreur suivante. La topologie peut uniquement être affichée à l’aide de Skype pour le Générateur de topologie 2019 Business Server. Le Skype pour le Générateur de topologie 2019 Business Server doit être utilisé pour créer des pools pour Skype pour Business Server 2019 et de l’installation héritée.

  

