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
description: Après avoir effectué la migration vers Microsoft Skype entreprise Server 2019, vous devez effectuer quelques tâches pour configurer Skype entreprise Server 2019 de manière à ce qu’il fonctionne avec System Center Operations Manager.
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754044"
---
# <a name="configure-scom-monitoring"></a>Configuration de la surveillance SCOM

Après avoir effectué une migration vers Skype entreprise Server 2019, vous devez effectuer quelques tâches pour configurer Skype entreprise Server 2019 de manière à ce qu’il fonctionne avec System Center Operations Manager.
  
- Appliquer des mises à jour à un serveur choisi pour gérer la logique de détection centrale.
    
- Mettez à jour la clé de Registre du serveur candidat de détection centrale.
    
- Configurez votre serveur de gestion principal de System Center Operations Manager pour remplacer le nœud de découverte centrale candidat.
    
Des instructions pour mener à bien chacune de ces tâches sont fournies ci-dessous.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Appliquer des mises à jour à un serveur choisi pour gérer la logique de détection centrale.

1. Choisissez un serveur sur lequel les fichiers de l’agent System Center Operations Manager sont installés et qui est configuré en tant que nœud candidat de détection centrale. 
    
2. Appliquer les mises à jour à ce serveur. Consultez la rubrique [appliquer les mises à jour](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Mettez à jour la clé de Registre du serveur candidat de détection centrale.

1. Sur le serveur choisi pour gérer la logique de découverte centrale, ouvrez une fenêtre de commande Windows PowerShell. 
    
2. Sur la ligne de commande, tapez ce qui suit :
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Configurez votre serveur de gestion principal de System Center Operations Manager pour remplacer le nœud du service Observateur de découverte centrale candidat.

1. Sur un ordinateur doté de la console System Center Operations Manager, développez **Objets du pack d’administration**, puis sélectionnez **Détections d’objets**.
    
2. Cliquez sur **modifier l’étendue**
    
3. Dans la page **Étendre les objets du pack d’administration**, sélectionnez **Candidat de détection LS**.
    
4. Remplacez la **Valeur effective du candidat de détection LS** par le nom du serveur candidat choisi dans la procédure précédente. 
    
Pour finaliser vos modifications, redémarrez le service d’intégrité sur le serveur d’administration racine System Center Operations Manager.
  

