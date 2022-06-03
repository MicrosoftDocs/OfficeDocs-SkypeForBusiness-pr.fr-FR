---
title: Installer des outils d’administration dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Résumé : Découvrez comment installer les outils d’administration requis pour une installation de Skype Entreprise Server.'
ms.openlocfilehash: e18ad5953eb063cdb91ea2927ad03ed1057c840a
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860525"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Installer des outils d’administration dans Skype Entreprise Server
 
**Résumé:** Découvrez comment installer les outils d’administration requis pour une installation de Skype Entreprise Server.
  
Les outils d’administration incluent le Générateur de topologie et le Panneau de configuration. Les outils d’administration doivent être installés sur au moins un serveur dans la topologie ou sur une station de travail de gestion 64 bits exécutant une version de système d’exploitation Windows prise en charge pour Skype Entreprise Server. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Toutefois, vous devez effectuer les étapes 6, 7 et 8 dans l’ordre, et après les étapes 1 à 5, comme indiqué dans le diagramme. L’installation des outils d’administration est l’étape 3 sur 8.
  
![Diagramme de vue d’ensemble.](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Installer Skype Entreprise Server outils d’administration

Le support d’installation de Skype Entreprise Server offre une expérience flexible. Lorsque vous exécutez Setup.exe pour la première fois, les seuls outils installés sont l’Assistant Déploiement Skype Entreprise Server et l’interpréteur de commandes de gestion Skype Entreprise Server. En utilisant ces deux outils, appelés composants principaux, vous pouvez poursuivre le processus d’installation, mais ils ne fournissent pas de fonctionnalités principales pour l’environnement Skype Entreprise Server global. L’Assistant Déploiement démarre automatiquement après l’installation des composants principaux. La section de l’Assistant Déploiement intitulée **Installer les outils d’administration** installe Skype Entreprise Server Générateur de topologie et Skype Entreprise Server Panneau de configuration.
  
> [!IMPORTANT]
> Chaque environnement Skype Entreprise Server doit avoir au moins un serveur avec les outils d’administration installés. 
  
Regardez les étapes vidéo pour **installer les outils d’administration** :
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>Installer Skype Entreprise Server outils d’administration à partir de l’Assistant Déploiement

1. Insérez le support d’installation Skype Entreprise Server. Si le programme d’installation ne démarre pas automatiquement, double-cliquez sur **Configurer**.
    
2. Le support d’installation nécessite l’exécution de Microsoft Visual C++. Une boîte de dialogue s’affiche pour vous demander si vous souhaitez l’installer. Cliquez sur **Oui**.
    
3. À l’aide du programme d’installation intelligente, une nouvelle fonctionnalité de Skype Entreprise Server, vous pouvez vous connecter à Internet pour rechercher des mises à jour pendant le processus d’installation. Cela offre une meilleure expérience en vous assurant que vous disposez des mises à jour les plus récentes du produit lors de l’installation. Cliquez sur **Installer** pour commencer l’installation.
    
4. Examinez attentivement le contrat de licence et, si vous acceptez, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**.
    
5. Les composants principaux Skype Entreprise Server seront installés sur le serveur. 
    
    Les composants principaux se composent des éléments suivants, comme illustré dans la figure.
    
    ![Écran Composants principaux dans les applications.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype Entreprise Server’Assistant Déploiement** Un programme de déploiement qui fournit un panneau de lancement pour l’installation des différents composants de Skype Entreprise Server.
    
   - **Skype Entreprise Server Management Shell** Un programme PowerShell préconfiguré qui permet l’administration de Skype Entreprise Server.
    
     Une fois l’installation des composants principaux terminée, l’Assistant Déploiement Skype Entreprise Server démarre automatiquement, comme illustré dans la figure. 
    
     ![Assistant Déploiement Skype Entreprise Server.](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. En plus des composants principaux, vous devez également installer Skype Entreprise Server Générateur de topologie et Skype Entreprise Server Panneau de configuration sur au moins un serveur dans l’environnement. Cliquez sur **Installer les outils d’administration** dans l’Assistant Déploiement.
    
7. Cliquez sur **Suivant** pour commencer l’installation.
    
8. Une fois l’installation terminée, cliquez sur **Terminer**. Les outils d’administration sont maintenant ajoutés au serveur, comme illustré dans la figure.
    
    ![Skype Entreprise Server outils d’administration.](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype Entreprise Server programme Générateur de topologie** A utilisé pour générer, déployer et gérer des topologies.
    
   - **Skype Entreprise Server Panneau de configuration** Un programme utilisé pour administrer l’installation.
    

