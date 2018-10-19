---
title: Utilisation de PowerShell pour gérer des équipes
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Apprenez à utiliser Windows PowerShell pour gérer l’ensemble des fonctionnalités disponibles dans Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c8eb0c37f71972bb20fac60706ff7a369d971d4
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/19/2018
ms.locfileid: "25678345"
---
# <a name="using-powershell-to-manage-teams"></a>Utilisation de PowerShell pour gérer des équipes

Fonctionnalités dans les équipes peuvent être gérées à l’aide de PowerShell ou Microsoft Teams et Skype entreprise centre d’administration. 

> ! [Note] Toutes les fonctionnalités dans les équipes peuvent être gérés à l’aide du module de connecteur d’équipes. Vous devrez peut-être utiliser la Skype pour Business connector. Voir [télécharger et installer le Skype pour connecteur Business en ligne](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)

### <a name="step-1-prerequisites"></a>Étape 1 : conditions préalables

Gestion à distance de Microsoft Teams à l’aide de PowerShell est pris en charge uniquement sur les ordinateurs 64 bits qui exécute un des systèmes d’exploitation suivants :
  
- Windows 10
- Windows 8.1
- Windows 8 
- Windows Server 2012 R2
- Windows Server 2012
- Windows Server 2008
- Windows 7
    
En plus d’un système d’exploitation pris en charge, l’ordinateur doit également exécuter les éléments suivants :
  
- PowerShell version 3.0 ou ultérieure
    
- Module de connecteur équipes PowerShell


### <a name="step-2-install-powershell-30-or-higher"></a>Étape 2 : Installer PowerShell version 3.0 ou ultérieure
[Utilisez cette rubrique pour une assistance](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-3-0) 

### <a name="step-3-download-and-install-the-teams-connector-module"></a>Étape 3 : Télécharger et installer le module de connecteur d’équipes
[Utilisez cette rubrique pour une assistance](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

Installez le module le plus récent à partir de la galerie de PowerShell à l’aide : 
  
  Install-Module MicrosoftTeams

Ou, pour plus d’informations, le package peut être trouvé :https://www.powershellgallery.com/packages/MicrosoftTeams/

### <a name="step-4-connect-using-the-teams-connector-module"></a>Étape 4 : Se connecter en utilisant le module de connecteur d’équipes
[Utilisez cette rubrique pour une assistance](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

### <a name="related-topics"></a>Rubriques connexes
- [Gérer les fonctionnalités des équipes avec PowerShell](manage-features-with-powershell.md)
