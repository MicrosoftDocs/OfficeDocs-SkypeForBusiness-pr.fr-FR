---
title: Installation des outils d’administration dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Résumé : Apprenez à installer les outils d’administration requis pour une installation de Skype pour Business Server 2015. Téléchargez une version d’évaluation gratuite de Skype pour 2015 de serveur d’entreprise depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: e54dfd4b29f3947b58517007949922a5c1230d51
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="install-administrative-tools-in-skype-for-business-server-2015"></a>Installation des outils d’administration dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à installer les outils d’administration requis pour une installation de Skype pour Business Server 2015. Téléchargez une version d’évaluation gratuite de Skype pour 2015 de serveur d’entreprise depuis le centre d’évaluation Microsoft à : [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Parmi les outils d’administration disponibles figurent Générateur de topologie et le Panneau de configuration. Les outils d’administration doivent être installés sur au moins un serveur dans la topologie ou une station de travail de gestion 64 bits exécutant une version de système d’exploitation Windows est pris en charge par Skype pour Business Server. Vous pouvez effectuer les étapes 1 à 5 dans un ordre quelconque. Vous devez cependant réaliser les étapes 6, 7 et 8 dans l’ordre stipulé, après les étapes 1 à 5, comme indiqué par le diagramme. L’installation des outils d’administration constitue la 3e des 8 étapes.
  
![Schéma de vue d’ensemble](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-2015-administrative-tools"></a>Installer Skype pour les outils d’administration de Business Server 2015

Le support d’installation de Skype pour Business Server 2015 offre un environnement flexible. Lors de la première exécution de Setup.exe, les outils sont uniquement installés sont le Skype pour l’Assistant de déploiement de Business Server et le Skype pour Business Server Management Shell. À l’aide de ces deux outils, appelés composants principaux, vous pouvez poursuivre le processus d’installation, mais elles ne fournissent pas de fonctionnalité principale pour le Skype global pour l’environnement du serveur de l’entreprise. L’assistant Déploiement démarre automatiquement après l’installation des composants principaux. La section de l’Assistant de déploiement intitulée **Installer les outils d’administration** installe Skype pour le Générateur de topologies de serveur Business et Skype pour le panneau de configuration de Business Server.
  
> [!IMPORTANT]
> Chaque Skype pour environnement Business Server doit avoir au moins un serveur avec les outils d’administration est installés. 
  
Visionnez les étapes présentées dans la vidéo pour l’**installation des outils d’administration** :
  
![Votre navigateur ne prend pas en charge la vidéo. Installez Microsoft Silverlight, Adobe Flash Player ou Internet Explorer 9.](../../media/MSN_Video_Widget.gif)
  
### <a name="install-skype-for-business-server-2015-administrative-tools-from-the-deployment-wizard"></a>Installer Skype pour Business Server 2015 des outils d’administration à partir de l’Assistant de déploiement

1. Insérez le Skype pour le support d’installation Business Server 2015. Si l’installation ne démarre pas automatiquement, double-cliquez sur **Installation (Setup)**.
    
2. Le support d’installation nécessite Microsoft Visual C++ pour s’exécuter. Une boîte de dialogue apparaît pour demander si vous souhaitez l’installer. Cliquez sur **Oui**.
    
3. En utilisant le programme d’installation active, une nouvelle fonctionnalité dans Skype pour 2015 de serveur d’entreprise, vous pouvez vous connecter à Internet pour vérifier les mises à jour pendant le processus d’installation. Cela permet une meilleure expérience du fait de la recherche des mises à jour les plus récentes disponibles pour le produit. Cliquez sur **Installer** pour lancer l’installation.
    
4. Passez en revue le Contrat de Licence Utilisateur Final et si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**.
    
5. Le Skype pour 2015 principaux composants Business Server sera installé sur le serveur. 
    
    Les composants principaux sont les suivants, comme indiqué dans la figure.
    
    ![Composants centraux dans l’écran Apps.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
  - **Skype pour l’Assistant de déploiement 2015 Business Server** Un programme de déploiement qui fournit le lancement d’un boîtier de commande pour installer les différents composants de Skype pour Business Server 2015.
    
  - **Skype pour Business Server 2015 Management Shell** Un programme PowerShell préconfiguré qui permet l’administration de Skype pour Business Server 2015.
    
    Une fois l’installation des composants principaux est terminée, le Skype pour l’Assistant de déploiement 2015 Business Server démarre automatiquement, comme illustré dans la figure. 
    
    ![Assistant Déploiement de Skype Entreprise Server 2015](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Outre les composants de base, vous devez également installer Skype pour le Générateur de topologies Business Server 2015 et Skype pour panneau de Business Server 2015 au moins un serveur dans l’environnement. Cliquez sur **Installer les outils d’administration** dans l’assistant Déploiement.
    
7. Cliquez sur **Suivant** pour commencer l’installation.
    
8. Une fois l’installation terminée, cliquez sur **Terminer**. Les outils d’administration sont désormais ajoutés au serveur, comme indiqué dans le schéma.
    
    ![Outils d’administration du serveur Skype Entreprise 2015](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype pour le Générateur de topologies 2015 Business Server** Un programme utilisé pour générer, déployer et gérer des topologies.
    
   - **Skype pour panneau Business Server 2015** Un programme permettant de gérer l’installation.
    

