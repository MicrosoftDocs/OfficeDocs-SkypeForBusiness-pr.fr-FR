---
title: Installer les outils d’administration dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Résumé : Découvrez comment installer les outils d’administration requis pour une installation de Skype pour Business Server. Téléchargez une version d’évaluation gratuite de Skype pour Business Server depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 48c6234b04f3c594f8cc50bda82ffca8cb256552
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32210724"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Installer les outils d’administration dans Skype pour Business Server
 
**Résumé :** Découvrez comment installer les outils d’administration requis pour une installation de Skype pour Business Server. Téléchargez une version d’évaluation gratuite de Skype pour Business Server depuis le centre d’évaluation Microsoft à : [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Parmi les outils d’administration disponibles figurent Générateur de topologie et le Panneau de configuration. Les outils d’administration doivent être installés sur au moins un serveur dans la topologie ou une station de travail de gestion 64 bits qui exécute une version du système d’exploitation Windows pris en charge pour Skype pour Business Server. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Vous devez cependant réaliser les étapes 6, 7 et 8 dans l’ordre stipulé, après les étapes 1 à 5, comme indiqué par le diagramme. L’installation des outils d’administration constitue la 3e des 8 étapes.
  
![Schéma de vue d’ensemble](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Installer Skype pour les outils d’administration Business Server

Le support d’installation pour Skype pour Business Server fournit une expérience flexible. Lors de la première exécution de Setup.exe, installés les outils seulement sont le Skype pour l’Assistant de déploiement Business Server et le Skype pour Business Server Management Shell. À l’aide de ces deux outils, appelés composants principaux, vous pouvez poursuivre le processus d’installation, mais ils ne fournissent pas de fonctionnalité principale pour le Skype globale pour l’environnement Business Server. L’assistant Déploiement démarre automatiquement après l’installation des composants principaux. La section de l’Assistant Déploiement intitulée **Installer les outils d’administration** installe Skype pour le Générateur de topologie du serveur Business et Skype pour le panneau de configuration serveur Business.
  
> [!IMPORTANT]
> Chaque Skype pour un environnement Business Server doit avoir au moins un serveur doté des outils d’administration. 
  
Visionnez les étapes présentées dans la vidéo pour l’**installation des outils d’administration** :
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>Installer Skype pour les outils d’administration Business Server à partir de l’Assistant Déploiement

1. Insérez le Skype pour le support d’installation Business Server. Si l’installation ne démarre pas automatiquement, double-cliquez sur **Installation (Setup)**.
    
2. Le support d’installation nécessite Microsoft Visual C++ pour s’exécuter. Une boîte de dialogue apparaît pour demander si vous souhaitez l’installer. Cliquez sur **Oui**.
    
3. À l’aide de la configuration active, une nouvelle fonctionnalité de Skype pour Business Server, vous pouvez vous connecter à Internet pour vérifier les mises à jour au cours du processus d’installation. Cela permet une meilleure expérience du fait de la recherche des mises à jour les plus récentes disponibles pour le produit. Cliquez sur **Installer** pour lancer l’installation.
    
4. Passez en revue le Contrat de Licence Utilisateur Final et si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**.
    
5. Le Skype pour les composants principaux d’entreprise Server sera installé sur le serveur. 
    
    Les composants principaux sont les suivants, comme indiqué dans la figure.
    
    ![Composants centraux dans l’écran Apps.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype pour l’Assistant de déploiement Business Server** Un programme de déploiement qui fournit une zone de lancement pour installer les différents composants de Skype pour Business Server.
    
   - **Skype pour Business Server Management Shell** Un programme PowerShell préconfiguré qui permet la gestion de Skype pour Business Server.
    
     Une fois l’installation des composants principaux est terminée, le Skype pour l’Assistant de déploiement Business Server lance automatiquement, comme le montre la figure. 
    
     ![Assistant Déploiement de Skype Entreprise Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Outre les composants principaux, vous devez également installer Skype pour le Générateur de topologie du serveur Business et Skype pour le panneau de configuration serveur Business au moins un serveur dans l’environnement. Cliquez sur **Installer les outils d’administration** dans l’assistant Déploiement.
    
7. Cliquez sur **Suivant** pour commencer l’installation.
    
8. Une fois l’installation terminée, cliquez sur **Terminer**. Les outils d’administration sont désormais ajoutés au serveur, comme indiqué dans le schéma.
    
    ![Skype pour les outils d’administration serveur](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype pour le Générateur de topologie Business Server** Un programme utilisé pour générer, déployer et gérer les topologies.
    
   - **Skype pour le panneau de configuration serveur Business** Programme permettant de gérer l’installation.
    

