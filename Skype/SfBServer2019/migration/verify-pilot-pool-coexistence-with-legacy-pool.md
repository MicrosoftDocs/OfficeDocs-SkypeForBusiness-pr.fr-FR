---
title: Vérification de la coexistence du pool pilote avec le pool hérité
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Processus de vérification de la coexistence du pool pilote avec le pool hérité.
ms.openlocfilehash: 5d2e6adad0f3297260137df0abcd082b750f0345
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606813"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Vérification de la coexistence du pool pilote avec le pool hérité

 **Contenu de cet article :**
  
[Vérifier que Skype Entreprise Server services 2019 ont démarré](#sectionSection0)
  
[Ouvrir le Panneau de Skype Entreprise Server 2019](#sectionSection1)
  
[N’essayez pas d’ouvrir la topologie dans le Générateur de topologie hérité](#sectionSection2)
  
Après avoir déployé le premier pool, vous devez vérifier la coexistence des deux pools à l’aide des outils d’administration pour afficher les informations des pools. Pour les pools Skype Entreprise Server 2019 et les pools hérités, vous devez utiliser le Panneau de Skype Entreprise Server 2019 et les outils du Générateur de topologies. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Vérifier que Skype Entreprise Server services 2019 ont démarré
<a name="sectionSection0"> </a>

1. À partir Skype Entreprise Server serveur frontal 2019, accédez à l’applet Outils d’administration\Services.
    
2. Vérifiez que les services suivants sont exécutés sur le serveur frontal :

    - Agent du service de journalisation centralisée
    - Partage d’application
    - Audio Test Service
    - Conférence audio/vidéo
    - Parcage d’appel
    - Annonce de conférence
    - Assistant de conférence
    - Serveur frontal
    - Conférence de messagerie instantanée
    - Médiation
    - Agent réplicateur de réplicas
    - Response Group
    - Conférence web
    - Passerelle de traduction XMPP

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Ouvrir le Panneau de Skype Entreprise Server 2019
<a name="sectionSection1"> </a>

À partir du serveur frontal de votre déploiement Skype Entreprise Server 2019, ouvrez le Panneau de Skype Entreprise Server 2019 et sélectionnez le pool hérité. Répétez la procédure pour ouvrir Skype Entreprise Server pool 2019.
  
> [!IMPORTANT]
> Sur Skype Entreprise Server 2019, vous devez mettre à niveau Silverlight vers Silverlight version 5 avant d’utiliser Skype Entreprise Server panneau de Skype Entreprise Server. 
  
Cette topologie inclut désormais les rôles serveur hérités Skype Entreprise Server 2019. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>N’essayez pas d’ouvrir la topologie dans le Générateur de topologie hérité
<a name="sectionSection2"> </a>

La topologie peut uniquement être vue à l’aide Skype Entreprise Server générateur de topologie 2019. Le Skype Entreprise Server de topologie 2019 doit être utilisé pour créer des pools pour Skype Entreprise Server 2019 et l’installation héritée.

  

