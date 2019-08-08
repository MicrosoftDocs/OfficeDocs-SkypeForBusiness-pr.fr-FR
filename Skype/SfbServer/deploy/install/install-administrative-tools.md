---
title: Installer les outils d’administration dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Résumé: Découvrez comment installer les outils d’administration nécessaires à l’installation de Skype entreprise Server. Télécharger une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft pour:.'
ms.openlocfilehash: 168202048fcd72b16d93cfd410f678cad01b3058
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244619"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Installer les outils d’administration dans Skype entreprise Server
 
**Résumé:** Découvrez comment installer les outils d’administration nécessaires à l’installation de Skype entreprise Server. Télécharger une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Microsoft pour:.
  
Parmi les outils d’administration disponibles figurent Générateur de topologie et le Panneau de configuration. Les outils d’administration doivent être installés sur au moins un serveur dans la topologie ou une station de travail de gestion 64 bits exécutant une version de système d’exploitation Windows qui est prise en charge par Skype entreprise Server. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Vous devez cependant réaliser les étapes 6, 7 et 8 dans l’ordre stipulé, après les étapes 1 à 5, comme indiqué par le diagramme. L’installation des outils d’administration constitue la 3e des 8 étapes.
  
![Schéma de vue d’ensemble](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Installer les outils d’administration de Skype entreprise Server

Le support d’installation de Skype entreprise Server offre une interface flexible. Lorsque vous exécutez le programme Setup. exe pour la première fois, les seuls outils installés sont l’Assistant Déploiement de Skype entreprise Server et Skype entreprise Server Management Shell. À l’aide de ces deux outils, appelés composants principaux, vous pouvez poursuivre le processus d’installation, mais ils ne fournissent pas de fonctionnalités principales pour l’environnement Skype entreprise Server global. L’assistant Déploiement démarre automatiquement après l’installation des composants principaux. La section de l’Assistant Déploiement intitulée **installer les outils d’administration** installe le générateur de topologie Skype entreprise Server et le panneau de configuration Skype entreprise Server.
  
> [!IMPORTANT]
> Chaque environnement Skype entreprise Server doit avoir au moins un serveur sur lequel les outils d’administration sont installés. 
  
Visionnez les étapes présentées dans la vidéo pour l’**installation des outils d’administration** :
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>Installer les outils d’administration de Skype entreprise Server depuis l’Assistant Déploiement

1. Insérez le CD d’installation de Skype entreprise Server. Si l’installation ne démarre pas automatiquement, double-cliquez sur **Installation (Setup)**.
    
2. Le support d’installation nécessite Microsoft Visual C++ pour s’exécuter. Une boîte de dialogue apparaît pour demander si vous souhaitez l’installer. Cliquez sur **Oui**.
    
3. À l’aide de la configuration intelligente, d’une nouvelle fonctionnalité de Skype entreprise Server, vous pouvez vous connecter à Internet pour rechercher des mises à jour lors du processus d’installation. Cela permet une meilleure expérience du fait de la recherche des mises à jour les plus récentes disponibles pour le produit. Cliquez sur **Installer** pour lancer l’installation.
    
4. Passez en revue le Contrat de Licence Utilisateur Final et si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**.
    
5. Les composants principaux de Skype entreprise Server sont installés sur le serveur. 
    
    Les composants principaux sont les suivants, comme indiqué dans la figure.
    
    ![Composants centraux dans l’écran Apps.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Assistant Déploiement de Skype entreprise Server** Programme de déploiement proposant un pavé de lancement pour l’installation des différents composants de Skype entreprise Server.
    
   - **Skype entreprise Server Management Shell** Programme PowerShell préconfiguré qui permet l’administration de Skype entreprise Server.
    
     Une fois l’installation des composants principaux terminée, l’Assistant Déploiement de Skype entreprise Server démarre automatiquement, comme illustré dans la figure. 
    
     ![Assistant Déploiement de Skype Entreprise Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Outre les composants principaux, vous devez également installer le générateur de topologie Skype entreprise Server et le panneau de configuration Skype entreprise Server sur au moins un serveur dans l’environnement. Cliquez sur **Installer les outils d’administration** dans l’assistant Déploiement.
    
7. Cliquez sur **Suivant** pour commencer l’installation.
    
8. Une fois l’installation terminée, cliquez sur **Terminer**. Les outils d’administration sont désormais ajoutés au serveur, comme indiqué dans le schéma.
    
    ![Outils d’administration de Skype entreprise Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Générateur de topologie Skype entreprise Server** Programme utilisé pour générer, déployer et gérer des topologies.
    
   - **Panneau de configuration Skype entreprise Server** Programme utilisé pour administrer l’installation.
    

