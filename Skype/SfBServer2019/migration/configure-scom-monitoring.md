---
title: Configuration de la surveillance SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après avoir migré vers Microsoft Skype entreprise Server 2019, vous devez effectuer quelques tâches pour configurer Skype entreprise Server 2019 de manière à utiliser System Center Operations Manager.
ms.openlocfilehash: aa782f2ef51e3397d465b1cd0f914783d371eded
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989589"
---
# <a name="configure-scom-monitoring"></a>Configuration de la surveillance SCOM

Après la migration vers Skype entreprise Server 2019, vous devez effectuer quelques tâches pour configurer Skype entreprise Server 2019 de manière à utiliser System Center Operations Manager.
  
- Appliquez les mises à jour à un serveur choisi pour gérer la logique de découverte centrale.
    
- Mettez à jour la clé de Registre du serveur prototype de découverte central.
    
- Configurer votre serveur de gestion Operations Manager principal de System Center pour remplacer le nœud de découverte central.
    
Vous trouverez ci-dessous des instructions pour chacune de ces tâches.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Appliquez les mises à jour à un serveur choisi pour gérer la logique de découverte centrale.

1. Électionnez un serveur sur lequel les fichiers de l’agent Operations Manager System Center Operations Manager sont installés et est configuré en tant que nœud de découverte candidat. 
    
2. Appliquez les mises à jour de ce serveur. Voir la rubrique [appliquer les mises à jour](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Mettez à jour la clé de Registre du serveur prototype de découverte central.

1. Sur le serveur choisi pour gérer la logique de découverte centralisée, ouvrez une fenêtre de commande Windows PowerShell. 
    
2. Dans la ligne de commande, tapez ce qui suit :
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Dès lors que vous modifiez le registre, il est possible que la commande échoue si la clé de Registre existe déjà. Si vous êtes à l’abri de cela, vous pouvez ignorer l’erreur. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Configurez votre serveur de gestion du gestionnaire d’opérations principales pour remplacer le nœud du centre de découverte central.

1. Sur un ordinateur sur lequel est installé la console System Center Operations Manager, développez **objets du pack d’administration** , puis sélectionnez découvertes d' **objets**.
    
2. Cliquez sur **modifier l’étendue**
    
3. Dans la page d' **objets du pack d’administration d’étendue** , sélectionnez **ls découverte candidate**.
    
4. Remplacez la **valeur effective** de la fonction de découverte (LS) par le nom du serveur candidat élu dans la procédure précédente. 
    
Pour finaliser vos modifications, redémarrez le service d’intégrité sur le serveur de gestion de racines System Center Operations Manager.
  

