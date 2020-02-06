---
title: Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Résumé : cette rubrique vous explique comment mettre à niveau le gestionnaire de statistiques pour Skype entreprise Server.'
ms.openlocfilehash: 6d54261ce9148986df5342bc228fe70b1477e17a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816203"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server
 
**Résumé :** Pour plus d’informations sur la mise à niveau du gestionnaire de statistiques pour Skype entreprise Server, voir la rubrique.
  
Cette rubrique décrit la mise à niveau d’une installation de Statistics Manager pour Skype entreprise Server, un outil puissant qui vous permet d’afficher les données d’intégrité et de performances de Skype entreprise Server en temps réel. Vous pouvez interroger les données de performances sur des centaines de serveurs à des intervalles de quelques secondes et afficher les résultats instantanément sur le site Web de Gestionnaire de Statistiques. 
  
Pour plus d’informations sur le gestionnaire de statistiques et les nouvelles fonctionnalités dans la version 2,0, voir [plan pour le gestionnaire de statistiques pour Skype entreprise Server](plan.md) et [déploiement de statistiques pour Skype entreprise Server](deploy.md).
  
Il existe deux méthodes de mise à niveau :
  
- **Mise à niveau automatique.** Cette méthode utilise un script automatisé. Il s’agit de la méthode la plus simple qui s’applique à tous les scénarios de mise à niveau.
    
- **Mise à niveau manuelle.** Cette méthode est fournie en tant que plan de sauvegarde dans le cas où la mise à niveau automatisée échoue.
    
## <a name="prerequisites"></a>Conditions requises

Avant d’effectuer la mise à niveau, assurez-vous de disposer des informations suivantes :
  
- Empreinte numérique de certificat d’écouteur actif
    
- Mot de passe du service d’écoute (saisi lors de l’installation de l’écouteur et de chaque agent)
    
- Configuration du certificat SSL du site web
    
## <a name="automated-upgrade"></a>Mise à niveau automatique

Le script collecte les informations concernant votre certificat actuel ainsi que le mot de passe de l’écouteur et désinstalle l’ancienne version du produit avant d’installer la nouvelle. L’instance Redis installée sur le serveur n’en est pas affectée, de sorte que toutes les données stockées dans la mémoire cache sont conservées pendant le processus de mise à niveau.
  
1. Placez les fichiers MSI pour la nouvelle version de l’agent, de l’écouteur et du site Web, ainsi que le script Update-StatsMan. ps1 dans un dossier unique de l’ordinateur écouteur.
    
2. Ouvrez une fenêtre d’administration PowerShell. Mettez à niveau l’écouteur :
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> Le mot de passe du service Gestionnaire de statistiques est affiché en clair sur la ligne de commande au fur et à mesure qu’il est transmis au programme d’installation. Par conséquent, assurez-vous de protéger convenablement votre moniteur. 
  
1. Lors de l’exécution du script, une invite vous demande si vous souhaitez désinstaller l’ancienne version du produit. Répondez Oui.
    
2. Si le service d’écoute est en cours d’exécution, vous serez invité à fermer l’application avant de poursuivre. Autoriser la fermeture de l’application (le service d’écouteur du gestionnaire de statistiques sera arrêté).
    
3. Continuez le processus d’installation. Normalement, le mot de passe du service et l’empreinte numérique du certificat sont déjà renseignés. Si ce n’est pas le cas, ajoutez les valeurs que vous avez enregistrées avant de poursuivre.
    
4. Ouvrez une fenêtre d’administration PowerShell. Mettez à niveau le site web :
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. Lors de l’exécution du script, une invite vous demande si vous souhaitez désinstaller l’ancienne version du produit. Répondez Oui.
    
6. Si le service d’agent est en cours d’exécution, vous serez invité à fermer l’application avant de poursuivre. Autorisez la fermeture de l’application (le service d’agent StatsMan sera arrêté).
    
7. Continuez le processus d’installation. Normalement, le mot de passe du service et l’empreinte numérique du certificat sont déjà renseignés. Si ce n’est pas le cas, ajoutez les valeurs que vous avez enregistrées avant de poursuivre.
    
8. Ouvrez une fenêtre d’administration PowerShell. Mettez à niveau l’agent :
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. Lors de l’exécution du script, une invite vous demande si vous souhaitez désinstaller l’ancienne version du produit. Répondez Oui.
    
10. Continuez le processus d’installation. Normalement, le port du site web est déjà renseigné. Si ce n’est pas le cas, ajoutez la valeur que vous avez enregistrée avant de poursuivre.
    
11. Vérifiez que le site web fonctionne correctement à l’aide du navigateur.
    
> [!NOTE]
> La mise à niveau de l’agent peut être effectuée avec le commutateur -NoPrompt. Ainsi, le processus d’installation/désinstallation s’exécute silencieusement, ce qui permet à des outils tels que PSExec d’exécuter à distance la mise à niveau sur un grand nombre de serveurs. 
  
### <a name="manual-upgrade"></a>Mise à niveau manuelle

Si, pour une raison ou pour une autre, la mise à niveau automatique échoue, vous pouvez toujours effectuer une mise à niveau manuelle en procédant comme suit :
  
1. 	Sur l’ordinateur d’écoute, désinstallez l’écouteur, le site web et l’agent (s’il était installée sur ce serveur) à l’aide du panneau de commande Programmes et fonctionnalités.   
    
    > [!NOTE]
    >   Ne désinstallez pas Redis, afin que les données dans la mémoire cache soient conservées pendant le processus de mise à niveau.
  
2. 	Installez les nouvelles versions de ces composants, y compris les valeurs que vous avez enregistrées précédemment lorsqu’elles vous sont demandées. Pour plus d’informations sur l’installation des composants, consultez la rubrique [Deploy Statistics Manager](deploy.md#BKMK_Deploy)

    
## <a name="for-more-information"></a>Pour plus d'informations
<a name="BKMK_Fixed"> </a>

Pour plus d'informations, voir les articles suivants :
  
- [Planifier le gestionnaire de statistiques pour Skype Entreprise Server](plan.md)
    
- [Déploiement du gestionnaire de statistiques pour Skype Entreprise Server](deploy.md)
    
- [Dépannage du gestionnaire de statistiques pour Skype Entreprise Server](troubleshoot.md)
