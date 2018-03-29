---
title: Installer l’outil de planification dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Avant de commencer à concevoir et planification votre Skype pour Business Server 2015 infrastructure à l’aide de la Skype pour outil de planification de 2015 Business Server, vous devez d’abord installer l’outil de planification. L’outil de planification n’a pas besoin d’être déployés sur une station de travail ou un serveur faisant partie de l’infrastructure ou du domaine dans lequel vous envisagez d’installer Skype pour Business Server 2015. Le fichier Lisezmoi qui accompagne l’outil de planification décrit en détail les informations importantes sur l’installation et à l’aide de l’outil. Certaines des informations contenues dans le fichier Lisez-moi sont expliquées ici par souci de clarté.
ms.openlocfilehash: 1c5c56031890aaff035e237e2ff7ab6d89d6ba2b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Installer l’outil de planification dans Skype Entreprise Server 2015
 
Avant de commencer à concevoir et planification votre Skype pour Business Server 2015 infrastructure à l’aide de la Skype pour outil de planification de 2015 Business Server, vous devez d’abord installer l’outil de planification. L’outil de planification n’a pas besoin d’être déployés sur une station de travail ou un serveur faisant partie de l’infrastructure ou du domaine dans lequel vous envisagez d’installer Skype pour Business Server 2015. Le fichier Lisezmoi qui accompagne l’outil de planification décrit en détail les informations importantes sur l’installation et à l’aide de l’outil. Certaines des informations contenues dans le fichier Lisez-moi sont expliquées ici par souci de clarté.
  
> [!IMPORTANT]
> L’outil de planification nécessite l’installation par un utilisateur disposant de droits d’administrateur et les autorisations sur l’ordinateur sur lequel l’outil doit être installé. 
  
Les systèmes d’exploitation pris en charge pour l’installation et le fonctionnement de l’outil de planification sont les suivantes :
  
- Windows 10 
    
- Windows 8
    
- Windows 8.1
    
- Windows Server 2012
    
- Windows Server 2012 R2
    
- Windows 7, édition 32 bits
    
- Windows 7, édition 64 bits avec WOW (Windows on Win32)
    
- Windows Server 2008 R2 avec WOW
    
En outre, l’outil de planification nécessite Microsoft.NET Framework 4.5.
  
Une fois que les spécifications de préinstallation sont respectées, vous pouvez ensuite installer l’outil de planification.
  
## 

### <a name="to-install-the-planning-tool"></a>Pour installer l’outil de planification

1. Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.
    
2. À l’aide de l’Explorateur Windows ou dans une fenêtre de commande, recherchez le répertoire où vous avez téléchargé les fichiers d’installation de l’outil de planification.
    
3. Recherchez le fichier SkypeForBusinessPlanningTool.msi. Dans l’Explorateur Windows, double-cliquez sur le fichier. Dans la fenêtre de commande, tapez le nom du fichier, puis appuyez sur **Entrée** pour exécuter le fichier.
    
4. Dans la page d’accueil de l’**Assistant Configuration de l’outil de planification de Skype Entreprise Server 2015**, cliquez sur **Suivant**.
    
5. Passez en revue le **Contrat de Licence Utilisateur Final**, sélectionnez **J’accepte les termes du contrat de licence** si vous choisissez d’accepter les termes d’utilisation contenus dans le contrat de licence, puis cliquez sur **Suivant**.
    
6. Choisissez où vous souhaitez installer les fichiers de l’outil de planification. L’emplacement d’installation par défaut est C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. Si vous souhaitez choisir un autre emplacement, cliquez sur **Modifier**. Dans **Modifier le dossier de destination**, accédez à l’emplacement d’installation des fichiers ou tapez-le directement dans le champ, cliquez sur **OK**, puis sur **Suivant**.
    
7. Le programme d’installation est maintenant prêt à installer l’outil de planification. Cliquez sur **Installer** pour commencer le processus d’installation.
    
8. L’installation débute et la progression s’affiche. Une fois l’installation terminée, cliquez sur **Terminer**.
    
9. L’outil de planification est prêt à l’emploi.
    
## <a name="optional-software"></a>Optional Software
<a name="Optional_Software"> </a>

Le Skype pour outil de planification de 2015 Business Server conçu pour l’exportation vers Microsoft Excel et Microsoft Visio. Alors que ces applications ne sont pas requises pour le fonctionnement de l’outil de planification, leur ajouter une valeur significative à la documentation de votre conception et le déploiement.
  
### <a name="microsoft-excel"></a>Microsoft Excel

L’exportation de votre conception vers Microsoft Excel permet de créer un rapport sous forme de feuille de calcul à quatre onglets :
  
- Résumé - affiche des informations sur la configuration du site, y compris les informations de profil de serveur, les paramètres de capacité et nombre d’utilisateurs.
    
- Profil matériel - affiche un rapport sur les configurations matérielles recommandées pour les serveurs qui sont spécifiés dans la topologie, y compris le CPU, mémoire, disque et interface réseau. La quantité et les caractéristiques conseillées pour les composants serveur y figurent également. Par ailleurs, chaque serveur est défini par site afin de fournir une représentation complète de la configuration serveur requise pour chaque site.
    
- Exigences des ports - affiche un rapport de tous les ports qui sont activés et l’association (livres de DNS) d’équilibrage de charge de système de nom de domaine et les équilibreurs de charge matériels (HUMIDIFICATION à HLB). Vous devez utiliser ce rapport pour planifier votre pare-feu et les configurations de l’équilibrage de la charge DNS et des programmes d’équilibrage de la charge matérielle.
    
- Rapport de synthèse - affiche le récapitulatif des paramètres qui sont requis pour configurer votre réseau de serveur de transport Edge.
    
- Certificats - affiche le nom de l’objet et le sujet autres noms qui sont requises pour les certificats nécessaires pour obtenir les serveurs Edge.
    
- Rapport - affiche les ports source et de destination et les adresses IP pour les interfaces à la fois interne et externe du pare-feu.
    
- DNS - affiche le nom de domaine pleinement qualifié (FQDN) et les adresses IP/VIP requis pour chaque entrée DNS que vous créez.
    
### <a name="microsoft-visio"></a>Microsoft Visio

L’exportation de votre conception vers Microsoft Visio crée un diagramme à utiliser dans la documentation de votre topologie et infrastructure configurée. Le diagramme importé peut être modifié et réorganisé pour répondre aux besoins de votre documentation. Un diagramme Visio classique inclut les éléments suivants :
  
> [!NOTE]
> Si votre conception est assez grande pour demander plus de trois serveurs frontaux, une page supplémentaire sera créée pour le pool de Front-End, serveurs frontaux, l’ordinateur qui exécute SQL Server, adresses IP et noms de domaine complets. 
  
- Topologie globale - diagramme de Skype configuré pour des sites entreprise serveur 2015.
    
- Onglet du nom de site - affiche la topologie de configuration de site avec le serveur de transport Edge, pare-feu, public switched téléphone réseau (RTPC) avec les passerelles et le déploiement de serveur interne. Déploiement interne se compose de serveurs configurés et pools pools, y compris la partie frontale, les serveurs SQL Server, Active Directory Domain Services, directeurs, Exchange la messagerie unifiée (MU), les serveurs de boîtes aux lettres Exchange, Office Web Apps serveurs, Serveurs de médiation et des serveurs de conversation permanent.
    
- Diagramme de réseau - diagramme décrivant la configuration de serveur de transport Edge avec les adresses IP et les noms de domaine complets associés du contour. L’équilibrage de la charge DNS et les programmes d’équilibrage de la charge matérielle sont également inclus. En outre, les directeurs et le pool de serveur frontal ou de Front-End sont affichés, avec associé DNS LB ou HUMIDIFICATION à HLB et l’adresse IP (l’outil de planification prend en charge les adresses IPv4 et IPv6) et le nom de domaine complet.
    
## <a name="see-also"></a>Voir aussi
<a name="Optional_Software"> </a>

#### 

[L’installation de l’outil de planification](http://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)

