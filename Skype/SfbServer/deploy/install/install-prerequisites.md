---
title: Installation des composants prérequis pour Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Résumé : En savoir plus sur les serveurs et les rôles de serveur que vous devez configurer avant d’installer Skype pour Business Server 2015. Téléchargez une version d’évaluation gratuite de Skype pour Business Server 2015 depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: f37954b4eddffbcef08c270dc86234e3a56e7079
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a>Installation des composants prérequis pour Skype Entreprise Server 2015
 
**Résumé :** Obtenir des informations sur les serveurs et les rôles de serveur que vous devez configurer avant d’installer Skype pour Business Server 2015. Téléchargez une version d’évaluation gratuite de Skype pour Business Server 2015 à partir du [Centre d’évaluation de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
L’installation des conditions préalables consiste à mettre en place Windows Server en installant les fonctionnalités et rôles requis pour chaque serveur de la topologie. Les conditions sont basées sur le rôle que le serveur va jouer dans la topologie. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Cependant, vous devez suivre les étapes 6, 7, et 8 dans l’ordre et après avoir effectué les étapes 1 à 5, comme expliqué sur le diagramme. L’installation des conditions préalables est présentée dans l’étape 1 sur 8.
  
![Schéma de vue d’ensemble - Composants prérequis pour l’installation.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Mise en place de Windows Server

Skype pour Business Server 2015 requiert le système d’exploitation Windows Server et un certain nombre de conditions préalables avant de pouvoir installer. Pour plus d’informations sur la planification des conditions préalables, voir [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  
> [!TIP]
> Cette procédure se base sur Windows Server 2012 R2. Si vous utilisez une version différente de Windows Server, la procédure peut être légèrement différente. 
  
> [!IMPORTANT]
> Avant de commencer, assurez-vous que Windows Server est mise à jour à l’aide de Windows Update. 
  
![Windows Server à jour.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Regardez la vidéo des étapes pour **installer les composants requis** :
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Installez les fonctionnalités et rôles requis pour les serveurs frontaux

Vous pouvez installer les rôles requis et les fonctionnalités à l’aide du Gestionnaire de serveur. 
    
1. Installer les fonctionnalités de logiciels répertoriées dans la [configuration serveur requise pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). Les logiciels requis doivent se trouver sur le serveur qui exécutera Skype pour Business Server 2015.
    
    > [!CAUTION]
    > Windows Server 2012 R2 n’installe pas tous les fichiers source pour les fonctionnalités requises par défaut. Si le serveur n’est pas connecté à internet, vous devrez installer le média Windows Server 2012 R2 et sélectionner **Spécifier un autre chemin d’accès source** afin d’installer les fonctionnalités requises. Les fichiers source se trouvent dans le répertoire sources\sxs. Par exemple, si le média Windows Server 2012 R2 se trouve dans le lecteur D, sélectionnez le chemin d’accès vers `d:\sources\sxs`. Il est important que vous ayez les dernières mises à jour de Windows Update. Si vous n’êtes pas connecté à internet, vous devrez installer manuellement toutes les mises à jour appropriées et toutes les conditions préalables pour les mises à jour requises. 
  
1. Lorsque la boîte de dialogue indiquera que l’installation a bien été effectuée, vous devrez redémarrer le serveur pour terminer le processus.
    
1. Réexécutez **Windows Update** pour vérifier les mises à jour pour les rôles et services qui ont été installés.
    
1. Si vous utilisez Skype pour le panneau de configuration serveur Business sur ce serveur vous devez également installer Silverlight. Pour installer Silverlight, voir [Microsoft Silverlight](https://www.microsoft.com/silverlight/).


> [!IMPORTANT]
> Les conditions préalables pour les serveurs ayant d’autres rôles que celui de serveur frontal (notamment les rôles de directeur, de conversation permanente, ou Edge) ont leurs propres conditions préalables. Pour plus d’informations sur la configuration exacte requise par chaque type de serveur, voir [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  

