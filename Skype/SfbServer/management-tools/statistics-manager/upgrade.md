---
title: Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/10/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Résumé : Lisez cette rubrique pour savoir comment mettre à niveau des statistiques de gestionnaire de Skype pour Business Server 2015.'
ms.openlocfilehash: d10dd5cd92fc0d7dbbb3285c43df78e8149f58c0
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295705"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server-2015"></a>Upgrade Statistics Manager for Skype for Business Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment mettre à niveau des statistiques de gestionnaire de Skype pour Business Server 2015.
  
Cette rubrique décrit comment mettre à niveau une installation existante du Gestionnaire de statistiques de Skype pour Business Server, un outil puissant qui vous permet d’afficher Skype pour les données de performances et d’intégrité Business Server en temps réel. Vous pouvez interroger les données de performance sur des centaines de serveurs après quelques secondes et afficher les résultats instantanément sur le site Web de gestionnaire de statistiques. 
  
Pour plus d’informations sur les statistiques Manager et les nouvelles fonctionnalités de la version 1.1, voir [planification pour le Gestionnaire de statistiques de Skype pour Business Server 2015](plan.md) et [Déployer des statistiques responsable Skype pour Business Server 2015](deploy.md). Pour plus d'informations sur les problèmes connus résolus dans la version 1.1, reportez-vous à la rubrique [Problèmes connus résolus dans la version 1.1](upgrade.md#BKMK_Fixed).
  
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
    
## <a name="known-issues-fixed-in-release-11"></a>Problèmes connus résolus dans la version 1.1
<a name="BKMK_Fixed"> </a>

Les problèmes connus suivants ont été corrigés dans la version 1.1 :
  
- L’interface utilisateur/serveur/Agent - nombreuses la fiabilité et performances
    
- L’interface utilisateur - contrôle de filtre principal maintenant trie correctement avec différents cas (a été entraînant des personnes à prendre en compte certains serveurs n’ont pas été dans le système lorsqu’elles étaient)
    
- Server : les composants du serveur peuvent désormais être installés sur des serveurs qui ne sont pas en anglais.
    
- Serveur/Agent : dans certains cas, les composants de l’agent et du serveur ne pouvaient pas être installés à cause d’erreurs .NET dues à une version spécifique de .NET 4.0. Ce problème est résolu.
    
- Agent - enregistrement des événements étendu ajoutée pour le StatsMan Agent. L’agent ne se bloque plus lorsqu’il est installé sur un serveur qui n’est pas dans la topologie ; cette situation est désormais consignée dans le journal d’événements, avec de nombreuses autres conditions d’erreurs possibles.
    
- L’interface utilisateur - les clients Web à l’aide du navigateur Chrome voir plusieurs invites d’ouverture de session lorsqu’à l’aide d’un ordinateur client non lié à la même groupe de travail ou domaine que le serveur Web de gestionnaire de statistiques. Désormais, une seule connexion par session suffit.
    
## <a name="for-more-information"></a>Pour plus d’informations
<a name="BKMK_Fixed"> </a>

Pour plus d’informations, voir les articles suivants :
  
- [Plan for Statistics Manager for Skype for Business Server 2015](plan.md)
    
- [Deploy Statistics Manager for Skype for Business Server 2015](deploy.md)
    
- [Troubleshoot Statistics Manager for Skype for Business Server 2015](troubleshoot.md)
    
- [Blog du gestionnaire de statistiques Skype Entreprise Server](https://blogs.technet.microsoft.com/skypestatsman/)
    

