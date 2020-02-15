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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Résumé : Découvrez comment installer les outils d’administration requis pour une installation de Skype entreprise Server. Téléchargez une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft à l’adresse suivante :.'
ms.openlocfilehash: 27cda52612eef1259017250ebcc4669e45165229
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018265"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Installer les outils d’administration dans Skype entreprise Server
 
**Résumé :** Découvrez comment installer les outils d’administration requis pour une installation de Skype entreprise Server. Téléchargez une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Microsoft à l’adresse suivante :.
  
Les outils d’administration comprennent le générateur de topologie et le panneau de configuration. Les outils d’administration doivent être installés sur au moins un serveur de la topologie ou sur une station de travail de gestion 64 bits exécutant une version du système d’exploitation Windows prise en charge pour Skype entreprise Server. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Toutefois, vous devez effectuer les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5, comme indiqué dans le diagramme. L’installation des outils d’administration est l’étape 3 sur 8.
  
![Diagramme de vue d’ensemble](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Installer les outils d’administration de Skype entreprise Server

Le support d’installation de Skype entreprise Server offre une expérience flexible. Lorsque vous exécutez Setup. exe pour la première fois, les seuls outils installés sont l’Assistant Déploiement de Skype entreprise Server et Skype entreprise Server Management Shell. À l’aide de ces deux outils, appelés composants principaux, vous pouvez poursuivre le processus d’installation, mais ils ne fournissent pas de fonctionnalité principale pour l’environnement de Skype entreprise Server global. L’Assistant déploiement est lancé automatiquement après l’installation des composants principaux. La section de l’Assistant Déploiement intitulée **installer les outils d’administration** installe le générateur de topologie Skype entreprise Server et le panneau de configuration Skype entreprise Server.
  
> [!IMPORTANT]
> Chaque environnement Skype entreprise Server doit disposer d’au moins un serveur sur lequel les outils d’administration sont installés. 
  
Regardez les étapes vidéo pour **installer les outils d’administration**:
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>Installer les outils d’administration de Skype entreprise Server à partir de l’Assistant Déploiement

1. Insérez le support d’installation de Skype entreprise Server. Si le programme d’installation ne commence pas automatiquement, double-cliquez sur **configuration**.
    
2. Le support d’installation nécessite Microsoft Visual C++ pour s’exécuter. Une boîte de dialogue s’affiche et vous demande si vous souhaitez l’installer. Cliquez sur **Oui**.
    
3. À l’aide de l’installation intelligente, une nouvelle fonctionnalité de Skype entreprise Server, vous pouvez vous connecter à Internet pour vérifier les mises à jour pendant le processus d’installation. Cela permet une meilleure expérience en s’assurant que vous disposez des dernières mises à jour du produit lors de l’installation. Cliquez sur **Installer** pour commencer l’installation.
    
4. Lisez attentivement le contrat de licence et, si vous l’acceptez, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**.
    
5. Les composants principaux de Skype entreprise Server seront installés sur le serveur. 
    
    Les composants principaux se composent des éléments suivants, comme illustré dans la figure.
    
    ![Composants principaux dans l’écran Apps.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Assistant Déploiement de Skype entreprise Server** Programme de déploiement qui fournit un pavé de lancement pour l’installation des différents composants de Skype entreprise Server.
    
   - **Skype entreprise Server Management Shell** Programme PowerShell préconfiguré qui permet l’administration de Skype entreprise Server.
    
     Une fois l’installation des composants principaux terminée, l’Assistant Déploiement de Skype entreprise Server se lance automatiquement, comme illustré dans la figure. 
    
     ![Assistant Déploiement de Skype entreprise Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. En plus des composants principaux, vous devrez également installer le générateur de topologie Skype entreprise Server et le panneau de configuration Skype entreprise Server sur au moins un serveur de l’environnement. Cliquez sur **installer les outils d’administration** dans l’Assistant déploiement.
    
7. Cliquez sur **Suivant** pour commencer l’installation.
    
8. Une fois l’installation terminée, cliquez sur **Terminer**. Les outils d’administration sont désormais ajoutés au serveur, comme illustré dans la figure.
    
    ![Outils d’administration de Skype entreprise Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Générateur de topologie Skype entreprise Server** Programme utilisé pour créer, déployer et gérer des topologies.
    
   - **Panneau de configuration de Skype entreprise Server** Programme utilisé pour administrer l’installation.
    

