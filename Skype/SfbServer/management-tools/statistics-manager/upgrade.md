---
title: Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Résumé : Lisez cette rubrique pour savoir comment mettre à niveau des statistiques de gestionnaire de Skype pour Business Server.'
ms.openlocfilehash: 8ff7eeb9c0abbd0482248f9b69db4013edda6495
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198453"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour savoir comment mettre à niveau des statistiques de gestionnaire de Skype pour Business Server.
  
Cette rubrique décrit comment mettre à niveau une installation existante du Gestionnaire de statistiques de Skype pour Business Server, un outil puissant qui vous permet d’afficher Skype pour les données de performances et d’intégrité Business Server en temps réel. Vous pouvez interroger les données de performances sur des centaines de serveurs à des intervalles de quelques secondes et afficher les résultats instantanément sur le site Web de Gestionnaire de Statistiques. 
  
Pour plus d’informations sur les statistiques Manager et les nouvelles fonctionnalités dans la version 2.0, voir [Planifier pour le Gestionnaire de statistiques de Skype pour Business Server](plan.md) et [Déployer des statistiques responsable Skype pour Business Server](deploy.md).
  
Il existe deux méthodes de mise à niveau :
  
- **Mise à niveau automatique.** Cette méthode utilise un script automatisé. Il est la méthode la plus simple et s’applique à tous les scénarios de mise à niveau.
    
- **Mise à niveau manuelle.** Cette méthode est fournie en tant qu’un plan de sauvegarde dans le cas inhabituel qui échoue la mise à niveau automatisée.
    
## <a name="prerequisites"></a>Conditions requises

Avant d’effectuer la mise à niveau, assurez-vous de disposer des informations suivantes :
  
- Empreinte numérique de certificat d’écouteur actif
    
- Mot de passe du service d’écoute (saisi lors de l’installation de l’écouteur et de chaque agent)
    
- Configuration du certificat SSL du site web
    
## <a name="automated-upgrade"></a>Mise à niveau automatique

Le script collecte les informations concernant votre certificat actuel ainsi que le mot de passe de l’écouteur et désinstalle l’ancienne version du produit avant d’installer la nouvelle. L’instance Redis installée sur le serveur n’en est pas affectée, de sorte que toutes les données stockées dans la mémoire cache sont conservées pendant le processus de mise à niveau.
  
1. Placez les fichiers MSI pour la nouvelle version de l’agent, le port d’écoute et le site Web ainsi que le script de mise à jour-StatsMan.ps1 dans un seul dossier sur l’ordinateur du port d’écoute.
    
2. Ouvrez une fenêtre d’administration PowerShell. Mettez à niveau l’écouteur :
    
   ```
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> Le mot de passe du service Gestionnaire de statistiques s’affichera en texte clair sur la ligne de commande, comme il est passé pour le programme d’installation. Par conséquent, assurez-vous de protéger convenablement votre moniteur. 
  
1. Lors de l’exécution du script, une invite vous demande si vous souhaitez désinstaller l’ancienne version du produit. Répondez Oui.
    
2. Si le service d’écoute est en cours d’exécution, vous serez invité à fermer l’application avant de poursuivre. Autoriser l’application à fermer (le Gestionnaire de statistiques de port d’écoute service va s’arrêter).
    
3. Continuez le processus d’installation. Normalement, le mot de passe du service et l’empreinte numérique du certificat sont déjà renseignés. Si ce n’est pas le cas, ajoutez les valeurs que vous avez enregistrées avant de poursuivre.
    
4. Ouvrez une fenêtre d’administration PowerShell. Mettez à niveau le site web :
    
   ```
   .\Update-StatsMan.ps1 -Service Website
   ```

5. Lors de l’exécution du script, une invite vous demande si vous souhaitez désinstaller l’ancienne version du produit. Répondez Oui.
    
6. Si le service d’agent est en cours d’exécution, vous serez invité à fermer l’application avant de poursuivre. Autorisez la fermeture de l’application (le service d’agent StatsMan sera arrêté).
    
7. Continuez le processus d’installation. Normalement, le mot de passe du service et l’empreinte numérique du certificat sont déjà renseignés. Si ce n’est pas le cas, ajoutez les valeurs que vous avez enregistrées avant de poursuivre.
    
8. Ouvrez une fenêtre d’administration PowerShell. Mettez à niveau l’agent :
    
   ```
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
