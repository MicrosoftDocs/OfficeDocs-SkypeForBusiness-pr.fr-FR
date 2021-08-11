---
title: Configuration de la surveillance SCOM
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Après avoir migré vers Microsoft Skype Entreprise Server 2019, vous devez effectuer quelques tâches pour configurer Skype Entreprise Server 2019 afin qu’il fonctionne avec System Center Operations Manager.
ms.openlocfilehash: 477fbd3c405328ffac4aa70a722120d375e95b295bf5a23d19882248d1ece54e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279612"
---
# <a name="configure-scom-monitoring"></a>Configuration de la surveillance SCOM

Après avoir migré vers Skype Entreprise Server 2019, vous devez effectuer quelques tâches pour configurer Skype Entreprise Server 2019 afin qu’il fonctionne avec System Center Operations Manager.
  
- Appliquer des mises à jour à un serveur choisi pour gérer la logique de découverte centrale.
    
- Mettez à jour la clé de Registre du serveur candidat de détection centrale.
    
- Configurez votre serveur de System Center Operations Manager principal pour remplacer le nœud de découverte centrale candidat.
    
Des instructions pour mener à bien chacune de ces tâches sont fournies ci-dessous.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Appliquer des mises à jour à un serveur choisi pour gérer la logique de découverte centrale.

1. Choisissez un serveur sur lequel les fichiers de l’agent System Center Operations Manager sont installés et qui est configuré en tant que nœud candidat de détection centrale. 
    
2. Appliquez les mises à jour à ce serveur. Consultez la rubrique [Appliquer les mises à jour.](apply-updates.md)
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Mettez à jour la clé de Registre du serveur candidat de détection centrale.

1. Sur le serveur choisi pour gérer la logique de découverte centrale, ouvrez Windows PowerShell fenêtre de commande. 
    
2. Sur la ligne de commande, tapez ce qui suit :
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > À chaque modification du Registre, une erreur liée à l’échec de la commande risque de se produire si la clé de Registre existe déjà. Dans ce cas, vous pouvez ignorer cette erreur sans risque. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Configurez votre serveur de System Center Operations Manager principal pour remplacer le nœud de détection centrale du candidat.

1. Sur un ordinateur doté de la console System Center Operations Manager, développez **Objets du pack d’administration**, puis sélectionnez **Détections d’objets**.
    
2. Cliquez sur **Modifier l’étendue**
    
3. Dans la page **Étendre les objets du pack d’administration**, sélectionnez **Candidat de détection LS**.
    
4. Remplacez la **Valeur effective du candidat de détection LS** par le nom du serveur candidat choisi dans la procédure précédente. 
    
Pour finaliser vos modifications, redémarrez le service d’état d’System Center du serveur d’administration racine Operations Manager.
  

