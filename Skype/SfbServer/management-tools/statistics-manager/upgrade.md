---
title: Mise à niveau du Gestionnaire de statistiques pour Skype Entreprise Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Résumé : Lisez cette rubrique pour découvrir comment mettre à niveau le Gestionnaire de statistiques pour Skype Entreprise Server.'
---

# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>Mise à niveau du Gestionnaire de statistiques pour Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour découvrir comment mettre à niveau le Gestionnaire de statistiques pour Skype Entreprise Server.
  
Cette rubrique décrit comment mettre à niveau une installation existante du Gestionnaire de statistiques pour Skype Entreprise Server, un outil puissant qui vous permet d’afficher les données d’état et de performances Skype Entreprise Server en temps réel. Vous pouvez sonder les données de performances sur des centaines de serveurs toutes les quelques secondes et afficher les résultats instantanément sur le site web du Gestionnaire de statistiques. 
  
Pour plus d’informations sur le Gestionnaire de statistiques et les nouvelles fonctionnalités de la version 2.0, voir [Plan for Statistics Manager for Skype Entreprise Server](plan.md) and [Deploy Statistics Manager for Skype Entreprise Server](deploy.md).
  
Il existe deux méthodes pour la mise à niveau :
  
- **Mise à niveau automatisée.** Cette méthode utilise un script automatisé. Il s’agit de la méthode la plus simple et elle doit s’appliquer à tous les scénarios de mise à niveau.
    
- **Mise à niveau manuelle.** Cette méthode est fournie en tant que plan de sauvegarde dans les cas inhabituels d’échec de la mise à niveau automatisée.
    
## <a name="prerequisites"></a>Conditions préalables

Avant de mettre à niveau, assurez-vous que vous avez les informations suivantes :
  
- Empreinte numérique du certificat d’écoute actif
    
- Mot de passe du service d’écoute (entré lors de l’installation de l’écoute et de chaque agent)
    
- Configuration du certificat SSL pour le site web
    
## <a name="automated-upgrade"></a>Mise à niveau automatisée

Le script collecte les informations de certificat et le mot de passe d’écoute actuels, désinstalle l’ancienne version du produit, puis installe la nouvelle version du produit. L’instance Redis installée sur le serveur ne sera pas touché, de sorte que les données stockées dans le cache seront conservées pendant le processus de mise à niveau.
  
1. Placez les fichiers MSI de la nouvelle version de l’agent, de l’écoute et du site web avec le script Update-StatsMan.ps1 dans un dossier unique sur l’ordinateur d’écoute.
    
2. Ouvrez une fenêtre d’administration PowerShell. Mettre à niveau le composant d’écoute :
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> Le mot de passe du service Gestionnaire de statistiques s’affiche en texte clair sur la ligne de commande lors de sa passage au programme d’installation. Assurez-vous de protéger votre moniteur selon vos besoins. 
  
1. Lors de l’exécution du script, vous devez être invité à désinstaller l’ancienne version du produit. Réponse Oui.
    
2. Si le service d’écoute est en cours d’exécution, vous êtes invité à fermer l’application avant de continuer. Autorisez la fermeture de l’application (le service d’écoute du Gestionnaire de statistiques sera arrêté).
    
3. Poursuivez le processus d’installation. Notez que le mot de passe du service et l’empreinte numérique du certificat sont pré-rempli. Si ce n’est pas le cas, ajoutez les valeurs que vous avez enregistrées avant de continuer.
    
4. Ouvrez une fenêtre d’administration PowerShell. Mettre à niveau le composant Site web :
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. Lors de l’exécution du script, vous devez être invité à désinstaller l’ancienne version du produit. Réponse Oui.
    
6. Si le service Agent est en cours d’exécution, vous êtes invité à fermer l’application avant de continuer. Autorisez la fermeture de l’application (le service d’agent StatsMan est arrêté).
    
7. Poursuivez le processus d’installation. Notez que le mot de passe du service et l’empreinte numérique du certificat sont pré-rempli. Si ce n’est pas le cas, ajoutez les valeurs que vous avez enregistrées avant de continuer.
    
8. Ouvrez une fenêtre d’administration PowerShell. Mettre à niveau le composant Agent :
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. Lors de l’exécution du script, vous devez être invité à désinstaller l’ancienne version du produit. Réponse Oui.
    
10. Poursuivez le processus d’installation. Notez que le port du site web est pré-rempli. Si ce n’est pas le cas, ajoutez la valeur que vous avez enregistrée avant de continuer.
    
11. Vérifiez que le site web fonctionne comme prévu à l’aide du navigateur.
    
> [!NOTE]
> La mise à niveau de l’agent peut être utilisée avec le commutateur -NoPrompt. Cela permettra au processus de désinstallation/installation de s’exécuter en mode silencieux, ce qui permettra aux outils tels que PSExec d’exécuter la mise à niveau à distance sur un grand nombre de serveurs. 
  
### <a name="manual-upgrade"></a>Mise à niveau manuelle

Si, pour une raison quelconque, la mise à niveau automatisée échoue, vous pouvez toujours effectuer une mise à niveau manuelle comme suit :
  
1. Sur l’ordinateur d’écoute, désinstallez l’écoute, le site web et l’agent (s’il a été installé sur ce serveur) via le panneau de contrôle Programmes et fonctionnalités. 
    
    > [!NOTE]
    >  Maintenez Redis installé afin que les données dans le cache soient ensuite conservées tout au long du processus de mise à niveau.
  
2. Installez les nouvelles versions des composants, y compris les valeurs que vous avez enregistrées ci-dessus lorsque vous y êtes invité. Pour plus d’informations sur l’installation des composants, voir [Deploy Statistics Manager](deploy.md#BKMK_Deploy)

    
## <a name="for-more-information"></a>Pour plus d'informations
<a name="BKMK_Fixed"> </a>

Pour plus d'informations, consultez les articles suivants :
  
- [Planifier le gestionnaire de statistiques pour Skype Entreprise Server](plan.md)
    
- [Déploiement du gestionnaire de statistiques pour Skype Entreprise Server](deploy.md)
    
- [Dépannage du gestionnaire de statistiques pour Skype Entreprise Server](troubleshoot.md)
