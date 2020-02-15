---
title: Installer les composants requis pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Résumé : Découvrez les serveurs et les rôles serveur que vous devez configurer avant d’installer Skype entreprise Server. Téléchargez une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft à l’adresse suivante :.'
ms.openlocfilehash: fedcebe601d21f0e581795c264ed26c6e90716bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018255"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Installer les composants requis pour Skype entreprise Server
 
**Résumé :** Découvrez les serveurs et les rôles serveur que vous devez configurer avant d’installer Skype entreprise Server. Téléchargez une version d’évaluation gratuite de Skype entreprise Server à partir du [Centre d’évaluation Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
L’installation des éléments prérequis consiste à configurer Windows Server en installant les rôles et les fonctionnalités requis sur chacun des serveurs de la topologie. La configuration requise est basée sur le rôle que le serveur doit remplir dans la topologie. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Toutefois, vous devez effectuer les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5, comme indiqué dans le diagramme. L’installation des composants requis est l’étape 1 sur 8.
  
![Diagramme de vue d’ensemble : installer les composants requis.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Configurer Windows Server

Skype entreprise Server requiert le système d’exploitation Windows Server et un certain nombre de conditions préalables avant d’être installé. Pour plus d’informations sur la planification des conditions préalables, reportez-vous à la rubrique [Server Requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  
> [!TIP]
> Cette procédure utilise Windows Server 2012 R2. Si vous utilisez une autre version de Windows Server, la procédure peut être légèrement différente. 
  
> [!IMPORTANT]
> Avant de commencer, assurez-vous que Windows Server est à jour à l’aide de Windows Update. 
  
![Windows Server à jour.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Regardez les étapes de la vidéo pour l' **installation des composants requis**:
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Installer les rôles et fonctionnalités requis pour les serveurs frontaux

Vous pouvez installer les rôles et les fonctionnalités requis à l’aide du gestionnaire de serveur. 
    
1. Installez les fonctionnalités logicielles prérequises indiquées dans [Configuration requise pour le serveur pour Skype entreprise Server](../../../SfBServer2019/plan/system-requirements.md). Les logiciels requis doivent se trouver sur le serveur qui exécutera Skype entreprise Server.
    
    > [!CAUTION]
    > Windows Server 2012 R2 n’installe pas tous les fichiers sources pour les fonctionnalités requises par défaut. Si le serveur n’est pas connecté à Internet, vous devez insérer le support Windows Server 2012 R2 et sélectionner **spécifier un autre chemin d’accès source** afin d’installer les fonctionnalités requises. Les fichiers sources se trouvent dans le répertoire sources\sxs Par exemple, si le support Windows Server 2012 R2 est dans le lecteur D, définissez le chemin d’accès `d:\sources\sxs`sur. Il est important que vous disposiez des dernières mises à jour de Windows Update. Si vous n’êtes pas connecté à Internet, vous devrez installer manuellement toutes les mises à jour appropriées, ainsi que les conditions préalables pour les mises à jour requises. 
  
1. Lorsque la boîte de dialogue indique que l’installation est terminée, vous devrez redémarrer le serveur pour terminer le processus.
    
1. Exécutez de nouveau **Windows Update** pour vérifier s’il existe des mises à jour des rôles et des services qui ont été installés.
    
1. Si vous utilisez le panneau de configuration de Skype entreprise Server sur ce serveur, vous devez également installer Silverlight. Pour installer Silverlight, voir [Microsoft Silverlight](https://www.microsoft.com/silverlight/).


> [!IMPORTANT]
> Les conditions préalables pour les serveurs exécutant des rôles autres que le serveur frontal, telles que le rôle directeur, la conversation permanente ou le serveur Edge, ont leurs propres conditions préalables. Pour plus d’informations sur les conditions préalables requises pour chaque type de serveur, reportez-vous à la rubrique [Server Requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  

