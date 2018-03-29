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
description: 'Résumé : Lisez cette rubrique pour savoir comment mettre à niveau le Gestionnaire de statistiques pour Skype pour Business Server 2015.'
ms.openlocfilehash: e5a9dd230f16313388cbb9a51e50910979e6c79c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server-2015"></a>Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment mettre à niveau le Gestionnaire de statistiques pour Skype pour Business Server 2015.
  
Cette rubrique décrit comment mettre à niveau une installation existante du Gestionnaire des statistiques pour Skype pour Business Server, un outil puissant qui vous permet d’afficher les Skype pour les données de santé et les performances de serveur d’entreprise en temps réel. Vous pouvez interroger les données de performance sur des centaines de serveurs toutes les quelques secondes et afficher les résultats d’instantanément sur le site Web du Gestionnaire de statistiques. 
  
Pour plus d’informations sur le Gestionnaire de statistiques et les nouvelles fonctionnalités de la version 1.1, consultez [planification pour le Gestionnaire de statistiques pour Skype pour Business Server 2015](plan.md) et [Déployer le Gestionnaire de statistiques pour Skype pour Business Server 2015](deploy.md). Pour plus d'informations sur les problèmes connus résolus dans la version 1.1, reportez-vous à la rubrique [Problèmes connus résolus dans la version 1.1](upgrade.md#BKMK_Fixed).
  
Il existe deux méthodes de mise à niveau :
  
- **Mise à niveau automatique.** Cette méthode utilise un script automatisé. Elle est la méthode la plus simple et devrait être applicable à tous les scénarios de mise à niveau.
    
- **Mise à niveau manuelle.** Cette méthode est fournie sous la forme d’un plan de sauvegarde dans le cas rare que la mise à niveau automatique échoue.
    
## <a name="prerequisites"></a>Conditions requises

Avant d’effectuer la mise à niveau, assurez-vous de disposer des informations suivantes :
  
- Empreinte numérique de certificat d’écouteur actif
    
- Mot de passe du service d’écoute (saisi lors de l’installation de l’écouteur et de chaque agent)
    
- Configuration du certificat SSL du site web
    
## <a name="automated-upgrade"></a>Mise à niveau automatique

Le script collecte les informations concernant votre certificat actuel ainsi que le mot de passe de l’écouteur et désinstalle l’ancienne version du produit avant d’installer la nouvelle. L’instance Redis installée sur le serveur n’en est pas affectée, de sorte que toutes les données stockées dans la mémoire cache sont conservées pendant le processus de mise à niveau.
  
1. Placez les fichiers MSI pour la nouvelle version de l’agent, un récepteur et un site Web avec le script de mise à jour-StatsMan.ps1 dans un dossier unique sur l’ordinateur récepteur.
    
2. Ouvrez une fenêtre d’administration PowerShell. Mettez à niveau l’écouteur :
    
  ```
  .\Update-StatsMan.ps1 -Service Listener
  ```

> [!NOTE]
> Le mot de passe du service Gestionnaire de statistiques s’afficheront en texte clair sur la ligne de commande lorsqu’elle est transmise à l’installateur. Par conséquent, assurez-vous de protéger convenablement votre moniteur. 
  
1. Lors de l’exécution du script, une invite vous demande si vous souhaitez désinstaller l’ancienne version du produit. Répondez Oui.
    
2. Si le service d’écoute est en cours d’exécution, vous serez invité à fermer l’application avant de poursuivre. Autoriser l’application se ferme (l’écouteur statistiques Manager service va être arrêté).
    
3. Continuez le processus d’installation. Normalement, le mot de passe du service et l’empreinte numérique du certificat sont déjà renseignés. Si ce n’est pas le cas, ajoutez les valeurs que vous avez enregistrées avant de poursuivre.
    
3. Ouvrez une fenêtre d’administration PowerShell. Mettez à niveau le site web :
    
  ```
  .\Update-StatsMan.ps1 -Service Website
  ```

1. Lors de l’exécution du script, une invite vous demande si vous souhaitez désinstaller l’ancienne version du produit. Répondez Oui.
    
2. Si le service d’agent est en cours d’exécution, vous serez invité à fermer l’application avant de poursuivre. Autorisez la fermeture de l’application (le service d’agent StatsMan sera arrêté).
    
3. Continuez le processus d’installation. Normalement, le mot de passe du service et l’empreinte numérique du certificat sont déjà renseignés. Si ce n’est pas le cas, ajoutez les valeurs que vous avez enregistrées avant de poursuivre.
    
4. Ouvrez une fenêtre d’administration PowerShell. Mettez à niveau l’agent :
    
  ```
  .\Update-StatsMan.ps1 -Service Agent
  ```

1. Lors de l’exécution du script, une invite vous demande si vous souhaitez désinstaller l’ancienne version du produit. Répondez Oui.
    
2. Continuez le processus d’installation. Normalement, le port du site web est déjà renseigné. Si ce n’est pas le cas, ajoutez la valeur que vous avez enregistrée avant de poursuivre.
    
3. Vérifiez que le site web fonctionne correctement à l’aide du navigateur.
    
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
    
- L’interface utilisateur - principal filtre contrôle maintenant trie correctement avec des casses différentes (a été de pointe qui fait de certains serveurs n’étaient pas dans le système lorsqu’elles étaient)
    
- Server : les composants du serveur peuvent désormais être installés sur des serveurs qui ne sont pas en anglais.
    
- Serveur/Agent : dans certains cas, les composants de l’agent et du serveur ne pouvaient pas être installés à cause d’erreurs .NET dues à une version spécifique de .NET 4.0. Ce problème est résolu.
    
- Agent - l’enregistrement des événements étendu ajouté pour le StatsMan Agent. L’agent ne se bloque plus lorsqu’il est installé sur un serveur qui n’est pas dans la topologie ; cette situation est désormais consignée dans le journal d’événements, avec de nombreuses autres conditions d’erreurs possibles.
    
- L’interface utilisateur - les clients Web via le navigateur Chrome voir plusieurs invites d’ouverture de session lors de l’utilisation d’un ordinateur client non joints au même groupe de travail ou domaine que le serveur Web du Gestionnaire de statistiques. Désormais, une seule connexion par session suffit.
    
## <a name="for-more-information"></a>Pour plus d’informations
<a name="BKMK_Fixed"> </a>

Pour plus d'informations, voir les articles suivants :
  
- [Planification pour le Gestionnaire de statistiques pour Skype pour Business Server 2015](plan.md)
    
- [Déployer le Gestionnaire de statistiques pour Skype pour Business Server 2015](deploy.md)
    
- [Résoudre les problèmes de statistiques responsable Skype pour Business Server 2015](troubleshoot.md)
    
- [Skype pour Business Server Manager statistiques de blog](https://blogs.technet.microsoft.com/skypestatsman/)
    

