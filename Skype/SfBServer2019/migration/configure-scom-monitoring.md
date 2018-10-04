---
title: Configurer la surveillance SCOM
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après la migration vers Microsoft Skype pour Business Server 2019, vous devez effectuer certaines tâches pour configurer Skype pour Business Server 2019 travailler avec System Center Operations Manager.
ms.openlocfilehash: c54038bc89c62a9911e684e451a66f4f12a23124
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373741"
---
# <a name="configure-scom-monitoring"></a>Configurer la surveillance SCOM

Après avoir migré vers Skype pour Business Server 2019, vous devez effectuer certaines tâches pour configurer Skype pour Business Server 2019 travailler avec System Center Operations Manager.
  
- Mettre à jour un serveur dédié à la gestion de la logique de détection centrale.
    
- Mettre à jour la clé de Registre du serveur de détection centrale candidat.
    
- Configurer votre serveur d’administration System Center Operations Manager principal pour remplacer le nœud candidat de détection centrale.
    
Instructions pour la réalisation de chacune de ces tâches sont fournies ci-dessous.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Mettre à jour un serveur dédié à la gestion de la logique de détection centrale.

1. Choisir un serveur ayant System Center Operations Manager fichiers de l’agent installé et configuré comme un nœud candidat de détection. 
    
2. Appliquer des mises à jour pour ce serveur. Consultez la rubrique [appliquer des mises à jour](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Mettre à jour la clé de Registre du serveur de détection centrale candidat.

1. Sur le serveur dédié à la gestion de la logique de détection centrale, ouvrez une fenêtre de commande Windows PowerShell. 
    
2. Dans la ligne de commande, tapez ce qui suit :
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Lorsque vous modifiez le Registre, vous pouvez rencontrer une erreur Échec de la commande si la clé de Registre existe déjà. Si vous rencontrez cette option, vous pouvez ignorer l’erreur. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Configurer votre serveur d’administration System Center Operations Manager principal pour remplacer le nœud Observateur candidat de détection centrale.

1. Sur un ordinateur sur lequel la console System Center Operations Manager est installée, développez **Objets du Pack d’administration** , puis sélectionnez **Détections d’objets**.
    
2. Cliquez sur **Modifier l’étendue**
    
3. Dans la page **Étendue objets du Pack d’administration** , sélectionnez **Candidat de détection LS**.
    
4. Remplacer la **Valeur Effective du candidat de détection LS** sur le nom du serveur candidat choisi dans la procédure précédente. 
    
Pour finaliser vos modifications, redémarrez le service d’intégrité sur le serveur de gestion de System Center Operations Manager racine.
  

