---
title: Vérification de la coexistence du pool pilote avec le pool hérité
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Processus de vérification de la coexistence du pool pilote avec le pool hérité.
ms.openlocfilehash: dd2edd2e6ecef26b22ba9bf5c093c631866110ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280652"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Vérification de la coexistence du pool pilote avec le pool hérité

 **Dans cet article**
  
[Vérifiez que les services 2019 de Skype entreprise Server ont démarré](#sectionSection0)
  
[Ouverture du panneau de configuration Skype entreprise Server 2019](#sectionSection1)
  
[Ne pas essayer d’ouvrir la topologie dans le générateur de topologie hérité](#sectionSection2)
  
Après avoir déployé le pool de pilotes, vous devez vérifier la coexistence des deux pools en utilisant les outils d’administration pour afficher les informations sur le pool. Pour les pools 2019 de Skype entreprise Server et les versions antérieures, vous devez utiliser les outils du panneau de configuration et du générateur de topologie de Skype entreprise Server 2019. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Vérifiez que les services 2019 de Skype entreprise Server ont démarré
<a name="sectionSection0"> </a>

1. À partir du serveur frontal Skype entreprise Server 2019, accédez à l’applet d’administration Tools\Services.
    
2. Vérifiez que les services suivants s’exécutent sur le serveur frontal:

    - Agent du service de journalisation centralisée
    - Partage d’application
    - Service de test audio
    - Audioconférence ou visioconférence
    - parcage d’appel
    - Annonce de conférence
    - Surveillant de conférences
    - Frontal
    - Conférences de messagerie instantanée
    - Serveur(s)
    - Agent réplicateur de réplicas
    - Response Group
    - Conférence web
    - Passerelle de traduction XMPP

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Ouverture du panneau de configuration Skype entreprise Server 2019
<a name="sectionSection1"> </a>

Sur le serveur frontal de votre déploiement de Skype entreprise Server 2019, ouvrez le panneau de configuration Skype entreprise Server 2019 et sélectionnez le pool hérité. Répétez cette procédure pour ouvrir le pool Skype entreprise Server 2019.
  
> [!IMPORTANT]
> Dans Skype entreprise Server 2019, vous devez mettre à niveau Silverlight vers Silverlight version 5 avant d’utiliser le panneau de configuration Skype entreprise Server. 
  
Cette topologie inclut désormais des rôles de serveur anciens et Skype entreprise Server 2019. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>Ne pas essayer d’ouvrir la topologie dans le générateur de topologie hérité
<a name="sectionSection2"> </a>

Si vous essayez d’ouvrir la topologie à l’aide du générateur de topologie hérité, vous pouvez rencontrer l’erreur ci-dessous. La topologie ne peut être affichée qu’à l’aide du générateur de topologie 2019 de Skype entreprise Server. Le générateur de topologie 2019 de Skype entreprise Server doit être utilisé pour créer des pools pour Skype entreprise Server 2019 et l’installation héritée.

  

