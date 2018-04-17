---
title: Installation des composants prérequis pour Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Résumé : En savoir plus sur les serveurs et les rôles de serveur que vous devez configurer avant d’installer Skype pour Business Server 2015. Téléchargez une version d’évaluation gratuite de Skype pour 2015 de serveur d’entreprise depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 6f84b4f0a95c45297ad809e6b04217e711c3dd5e
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a>Installation des composants prérequis pour Skype Entreprise Server 2015
 
**Résumé :** Obtenir des informations sur les serveurs et les rôles de serveur que vous devez configurer avant d’installer Skype pour Business Server 2015. Téléchargez une version d’évaluation gratuite de Skype pour 2015 de serveur d’entreprise à partir du [Centre d’évaluation de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
L’installation des conditions préalables consiste à mettre en place Windows Server en installant les fonctionnalités et rôles requis pour chaque serveur de la topologie. Les conditions sont basées sur le rôle que le serveur va jouer dans la topologie. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Cependant, vous devez suivre les étapes 6, 7, et 8 dans l’ordre et après avoir effectué les étapes 1 à 5, comme expliqué sur le diagramme. L’installation des conditions préalables est présentée dans l’étape 1 sur 8.
  
![Schéma de vue d’ensemble - Composants prérequis pour l’installation.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Mise en place de Windows Server

Skype pour Business Server 2015 nécessite le système d’exploitation Windows et un certain nombre de conditions préalables avant de pouvoir l’installer. Pour plus d’informations sur la planification de la configuration requise, voir [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  
> [!TIP]
> Cette procédure se base sur Windows Server 2012 R2. Si vous utilisez une version différente de Windows Server, la procédure peut être légèrement différente. 
  
> [!IMPORTANT]
> Avant de commencer, assurez-vous que le serveur Windows est à jour à l’aide de Windows Update. 
  
![Windows Server à jour.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Regardez la vidéo des étapes pour **installer les composants requis** :
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Installez les fonctionnalités et rôles requis pour les serveurs frontaux

1. Ouvrez le Gestionnaire de serveur et cliquez sur **Ajouter des rôles et fonctionnalités**.
    
2. Lisez la page **Avant de commencer** pour vous familiariser avec l’installation des rôles et fonctionnalités dans Windows Server, puis cliquez sur **Suivant**.
    
3. Sélectionnez une **Installation basée sur un rôle ou une fonctionnalité**, et cliquez sur **Suivant**.
    
4. Sélectionnez le serveur sur lequel vous fera l’installation Skype pour Business Server 2015, puis cliquez sur **suivant**.
    
5. Sélectionnez le rôle du **Serveur Web (IIS)**, et lorsque la fenêtre des fonctionnalités requises s’ouvre, cliquez sur **Ajouter des fonctionnalités**, puis sur **Suivant**.
    
6. Assurez-vous que les fonctions logicielles répertoriées dans le [logiciel qui doit être installé avant un Skype pour le déploiement de Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) sont sur le serveur qui exécutera Skype pour Business Server 2015. Voici une liste abrégée :
    
   - Fonctionnalités du.NET Framework
    
   - Services WCF
    
   - Activation HTTP
    
    > [!NOTE]
    > L’activation HTTP requiert des fonctionnalités supplémentaires. Cliquez sur **Ajouter des fonctionnalités** dans la boîte de dialogue d’avertissement qui s’ouvre lorsque vous sélectionnez l’activation HTTP.
  
   - Media Foundation (requis par les serveurs Standard Edition et les serveurs frontaux utilisés pour la conférence).
    
   - Outils d’administration de serveur distant
    
   - Outils d’administration de rôles
    
   - SERVICES AD DS 
    
   - AD LDS
    
   - Windows Identity Foundation 3.5
    
7. Cliquez sur **Suivant** pour continuer avec l’assistant.
    
8. Lisez les remarques sur le **Rôle de serveur web (IIS)**, puis cliquez sur **Suivant**.
    
9. Sélectionnez les **services de rôle de serveur web (IIS)** suivants.
    
   - Fonctionnalités HTTP communes
    
   - Document par défaut
    
   - Exploration des répertoires
    
   - Erreurs HTTP
    
   - Contenu statique
    
   - Intégrité et diagnostics
    
   - Journalisation HTTP
    
   - Outils de journalisation
    
   - Suivi
    
   - Performances
    
   - Compression du contenu statique
    
   - Compression du contenu dynamique
    
   - Sécurité
    
   - Filtrage des demandes
    
   - Authentification par mappage de certificat client
    
   - Authentification Windows
    
   - Développement d’applications
    
   - .NET Extensibility 3.5
    
   - .NET Extensibility 4.5
    
   - ASP.NET 3.5
    
   - ASP.NET 4.5
    
   - Extensions ISAPI
    
   - Filtres ISAPI
    
   - Outils de gestion
    
   - Console de gestion des services Internet (IIS)
    
   - Scripts et outils de gestion des services Internet (IIS)
    
10. Cliquez sur **Suivant** pour continuer avec l’assistant.
    
11. Vérifiez les choix d’installation pour vous assurer que toutes les conditions sont sélectionnées, puis cliquez sur **Installer**.
    
    > [!CAUTION]
    > Windows Server 2012 R2 n’installe pas tous les fichiers source pour les fonctionnalités requises par défaut. Si le serveur n’est pas connecté à internet, vous devrez installer le média Windows Server 2012 R2 et sélectionner **Spécifier un autre chemin d’accès source** afin d’installer les fonctionnalités requises. Les fichiers source se trouvent dans le répertoire sources\sxs. Par exemple, si le média Windows Server 2012 R2 se trouve dans le lecteur D, sélectionnez le chemin d’accès vers `d:\sources\sxs`. > Il est important que vous avez les dernières mises à jour à partir de Windows Update. Si vous n’êtes pas connecté à internet, vous devrez installer manuellement toutes les mises à jour appropriées et toutes les conditions préalables pour les mises à jour requises. 
  
12. Lorsque la boîte de dialogue indiquera que l’installation a bien été effectuée, vous devrez redémarrer le serveur pour terminer le processus.
    
13. Réexécutez **Windows Update** pour vérifier les mises à jour pour les rôles et services qui ont été installés.
    
14. Si vous utilisez Skype pour le panneau de configuration de Business Server sur ce serveur vous devez également installer Silverlight. Pour installer Silverlight, consultez [Microsoft Silverlight](https://www.microsoft.com/silverlight/).
    
Vous pouvez installer les conditions préalables en exécutant la commande PowerShell suivante. Veuillez noter que la commande recherche des fichiers source dans un ordre spécifique. Si vous êtes connecté à internet, la commande aura accès à Windows Update. Si vous n’êtes pas connecté à internet, vous devrez vous assurer que les fichiers source sont accessibles à la commande. Pour plus d’informations sur l’utilisation de PowerShell pour installer des rôles et fonctionnalités, consultez [installer ou désinstaller des rôles, Services de rôle ou fonctionnalités](https://technet.microsoft.com/en-us/library/hh831809.aspx) et [Installation-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx). N’oubliez pas de réexécuter Windows Update après avoir installé les conditions préalables, même si vous utilisez la commande PowerShell.
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> Les conditions préalables pour les serveurs ayant d’autres rôles que celui de serveur frontal (notamment les rôles de directeur, de conversation permanente, ou Edge) ont leurs propres conditions préalables. Pour plus d’informations sur les composants d’exacts requis par chaque type de serveur, consultez [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  

