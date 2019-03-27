---
title: Déployer le Skype pour client d’entreprise dans Office 365
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Découvrez comment planifier et déployer Skype pour les entreprises de petites, moyennes et grandes entreprises et la disposition de vos utilisateurs. '
ms.openlocfilehash: 6dccd022d82519c1dfdce13f767e5b0a2531eb10
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896792"
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a>Déployer le Skype pour client d’entreprise dans Office 365

Cet article décrit les options pour vous, l' **[administrateur](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)** pourrez comment déployer le Skype pour l’application de gestion aux personnes dans votre organisation.
  
Avant de déployer Skype pour métiers à vos utilisateurs, vérifiez que vous avez effectué les étapes 1 à 3 dans l’article [configurer Skype pour Business Online](set-up-skype-for-business-online.md). De cette manière, Skype pour les entreprises va être configuré avec votre domaine, tout le monde auront leurs licences et vous aurez configuré messagerie instantanée et [présence Configure Skype pour Business Online](configure-presence-in-skype-for-business-online.md) pour votre organisation.
  
> [!NOTE]
> Pour les utilisateurs à installer le Skype pour l’application de gestion, ils doivent être des administrateurs locaux sur leur PC ou un périphérique. Ou bien, ils devront faire partie d’un groupe local qui permettre installer des applications sur leur PC ou des périphériques. Si vos utilisateurs ne sont pas autorisés à installer les logiciels sur leurs appareils, vous devez installer le Skype pour l’application de gestion pour les. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Pour la plupart des petites et moyennes entreprises

 **Instructions d’installation pas à pas :** Si vous avez une petite ou moyenne entreprise, il est recommandé que vous demandez simplement à vos utilisateurs d’installer le Skype pour l’application de gestion sur leur PC. Qu’ils pointent vers ces instructions : [Installer le Skype pour les entreprises](https://support.office.com/en-us/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb?ui=en-US&rs=en-US&ad=US). Si vous utilisez Mac, qu’ils pointent vers [Configurer Lync pour Mac 2011 pour Office 365](https://support.office.com/en-us/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88?ui=en-US&rs=en-US&ad=US). Le Skype pour l’application de gestion est installé séparément du reste des applications Office.
  
 **Les clients office 365 ProPlus :** Si votre entreprise utilise un plan Office 365 qui inclut Office 365 ProPlus, telles que le plan E3, le Skype pour l’application de gestion est installé en même temps que vos utilisateurs à télécharger et installer Word, Excel, PowerPoint, etc.. Cela signifie également qu’ils ne peuvent pas désinstaller Skype pour les entreprises, sauf si elles désinstaller tous les d’Office.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Indiquez si vous souhaitez mettre à la disposition de vos utilisateurs Skype pour les entreprises

En tant que l' [administrateur](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US) , vous pouvez choisir s’il faut mettre le Skype pour l’application de gestion disponibles de vos utilisateurs.
  
- **Pour contrôler si tout le monde dans votre société Obtient le logiciel**: se connecter à l’Office 365 centre d’administration, accédez à **Mon logiciel**, puis sélectionnez le logiciel que vous voulez être disponibles pour les utilisateurs.
    
    ![Choix du logiciel que vous souhaitez rendre disponibles aux personnes de votre société.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **Pour contrôler si des personnes spécifiques de votre société obtenir le logiciel**: se connecter à l’Office 365 centre d’administration, ouvrez **utilisateurs** > **utilisateurs actifs**, sélectionnez la personne que vous souhaitez autoriser à accéder au logiciel, puis cliquez sur **Modifier** en regard de **licences** et d’activer ou désactiver les la licence.
    
    ![Choisir les logiciels que l’utilisateur à accéder.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Si vous avez besoin voir quels sont les projets sont affectées à des personnes dans votre organisation, connectez-vous à nouveau Office 365 admin center > **utilisateurs** > **utilisateurs actifs**. Sélectionnez la personne dans la liste, puis recherchez sous **licences de produits**. Si vous utilisez le centre d’administration Office 365 classique, regardez sous **licence affecté**. 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Déploiement manuel de Skype pour les entreprises à vos utilisateurs
<a name="bkmk_manual_1"> </a>

Si vous souhaitez que vos utilisateurs d’installer le Skype pour l’application de gestion à partir d’un emplacement sur votre réseau et non à partir d’Internet, vous pouvez télécharger les fichiers d’installation. Pour ce faire, accédez à la section **déployer manuellement des logiciels utilisateur** du centre d’administration Office 365. Vous pouvez ensuite sélectionnez **installer** et enregistrer le fichier .exe du programme d’installation vers un emplacement réseau.
  
Une autre option consiste à télécharger le Skype pour une application métier base pour vos utilisateurs. Vous pouvez télécharger [Microsoft Skype pour Business Basic (32 ou 64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=49440).
  
Pour les deux le complète et de base Skype pour les applications métier, une fois que vous avez téléchargé les fichiers d’installation, vous devrez envoyer manuellement (par exemple, dans le message électronique) le chemin d’accès réseau aux utilisateurs afin qu’ils peuvent exécuter le programme d’installation pour installer l’application sur leur ordinateur.
  
Vous pouvez également utiliser ces téléchargements pour déployer le Skype pour l’application de gestion à vos utilisateurs à l’aide de vos processus et outils de déploiement de logiciels existants.
  
## <a name="for-larger-and-enterprise-organizations"></a>De plus grande et les entreprises

> [!NOTE]
> Cette section s’applique uniquement à la Skype pour l’application de gestion disponible dans Office 365 plans. Si votre organisation utilise une version de licence en volume de la Skype pour une application métier, qui est basé sur Windows Installer (MSI), voir [installation de client personnaliser Skype pour Business Server 2015](https://technet.microsoft.com/en-us/library/jj204934.aspx). 
  
Dans nombreuses entreprises ou les grandes organisations, les utilisateurs ne sont pas autorisés à installer des logiciels sur leur ordinateur. Au lieu de cela, les départements informatiques déploiement les logiciels nécessaires sur les ordinateurs des utilisateurs. LES départements informatiques peuvent également contrôler la quantité de bande passante de réseau ou Internet utilisée dans leur organisation, afin qu’ils souhaitent installer le logiciel d’un emplacement à proximité sur leur réseau plutôt qu’à partir de sur Internet ou sur le réseau d’entreprise.
  
Avec Office 365, vous disposez de plusieurs options pour le déploiement de la Skype pour l’application de gestion si vous souhaitez contrôler où il est installé dans. Certaines de ces options sont les suivantes :
  
- Téléchargez le Skype pour l’application de gestion sur votre réseau local à partir du centre d’administration Office 365, comme indiqué dans [déploiement manuellement Skype pour les entreprises à vos utilisateurs](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).
    
- Utiliser l' **[Outil déploiement d’Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** pour télécharger Office 365 ProPlus ou le Skype pour l’application de gestion sur votre réseau local. Ensuite, utilisez l’outil de déploiement d’Office pour déployer l’application à vos utilisateurs. L’outil de déploiement Office vous donne la possibilité de contrôler certains aspects du déploiement, telles que les langues et la version (32 bits ou 64 bits).
    
- Utilisez vos outils de déploiement de logiciels existants et les processus, tels que Microsoft System Center Configuration Manager, pour déployer Office 365 ProPlus ou le Skype pour l’application de gestion à vos utilisateurs. Vous pouvez utiliser vos processus et les outils existants avec l' [Outil de déploiement Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) ou avec le logiciel que vous avez téléchargé à partir du centre d’administration Office 365.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Plus d’informations sur l’utilisation de l’outil de déploiement d’Office

Pour plus d’informations sur le téléchargement de l’outil de déploiement d’Office et plus d’informations sur l’installation de la Skype pour l’application de gestion et les autres applications client Office 365, voir [Gérer les logiciels des utilisateurs dans Office 365](https://support.office.com/en-us/article/c13051e6-f75c-4737-bc0d-7685dcedf360).
  
Voici une vue d’ensemble des étapes nécessaires pour déployer une application à l’aide de l’outil de déploiement d’Office :
  
1. **[Télécharger l’outil de déploiement d’Office plus récente](https://www.microsoft.com/en-us/download/details.aspx?id=49117)** à partir du Microsoft Download Center.
    
2. Créez le fichier configuration.xml à utiliser avec l’outil de déploiement d’Office avec les paramètres d’application client que vous le souhaitez, telles que la définition de la version (32 bits ou 64 bits), la langue d’installation, etc..
    
3. Utilisez l’outil de déploiement d’Office et le fichier configuration.xml pour télécharger les fichiers d’installation sur votre réseau interne ou externe à partir de l’Office réseau CDN (Content Delivery).
    
4. Utiliser Office Deployment Tool et le configuration.xml pour installer les applications client Office, y compris le Skype pour l’application de gestion.
    
Pour plus d’informations sur l’utilisation de l’outil déploiement d’Office et le fichier configuration.xml, voir les articles suivants :
  
- [Présentation de l’outil de déploiement Office](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Paramètres configuration.Xml](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-system-center-configuration-manager"></a>Plus d’informations sur l’utilisation de System Center Configuration Manager

Vous pouvez utiliser vos processus, telles que Microsoft System Center Configuration Manager et les outils de déploiement de logiciels existants pour déployer le Skype pour l’application de gestion. Vous pouvez utiliser ces outils et les processus avec le logiciel que vous téléchargez à partir du centre d’administration Office 365 ou avec l’outil de déploiement d’Office.
  
Pour plus d’informations sur l’utilisation du Gestionnaire de Configuration pour déployer des logiciels, consultez les articles suivants :
  
- [Comment créer des Applications dans le Gestionnaire de Configuration](https://technet.microsoft.com/en-us/library/gg682159.aspx)
    
- [Comment déployer des Applications dans le Gestionnaire de Configuration](https://technet.microsoft.com/en-us/library/gg682082.aspx)
    
Si vous déployez le Skype pour l’application de gestion dans le cadre du déploiement d’Office 365 ProPlus, voir [Déployer Office 365 ProPlus à l’aide de System Center Configuration Manager](https://technet.microsoft.com/en-us/library/dn708063.aspx).
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Planification des mises à jour le Skype pour l’application de gestion

Dans le cadre du déploiement de la Skype pour l’application de gestion, vous devez prendre en compte la manière dont vous souhaitez obtenir des mises à jour après avoir installé Skype pour les entreprises. Ces mises à jour peuvent inclure les nouvelles fonctionnalités, des mises à jour de sécurité ou des mises à jour de sécurité, telles que des mises à jour qui fournissent des améliorations de la stabilité ou de performances. Les deux principaux éléments que vous devez prendre en compte est les suivants :
  
- Où vous souhaitez obtenir des mises à jour
    
- La fréquence à laquelle vous souhaitez obtenir des mises à jour de la fonctionnalité
    
Alors que vous pouvez contrôler où obtenir des mises à jour et la fréquence à laquelle vous obtenez des mises à jour de la fonctionnalité, vous ne pouvez pas choisir les mises à jour de sécurité spécifiques ou les mises à jour de sécurité vous obtenez.
  
 **Obtention des mises à jour**
  
Par défaut, après l’installation, la Skype pour l’application de gestion des mises à jour seront être téléchargés automatiquement à partir d’Internet lorsqu’ils sont disponibles auprès de Microsoft. Si vous souhaitez plus de contrôle sur la survenue de mises à jour ou bien où les mises à jour sont installés à partir de, vous pouvez utiliser l’outil déploiement d’Office ou de la stratégie de groupe pour configurer qui.
  
Par exemple, de nombreuses organisations souhaitent tester les mises à jour avec un groupe d’utilisateurs avant de les déployer dans toute l’organisation. Vous pouvez procéder à l’aide de l’outil déploiement d’Office ou de la stratégie de groupe pour configurer le Skype pour l’application de gestion pour obtenir les mises à jour à partir d’un emplacement spécifique sur votre réseau, au lieu d’automatiquement à partir d’Internet. Ensuite, vous pouvez utiliser l’outil de déploiement d’Office pour télécharger les mises à jour chaque mois sur votre réseau local.
  
Pour plus d’informations sur le fonctionnement des mises à jour pour le logiciel Office 365, voir ces articles :
  
- [Vue d’ensemble du processus de mise à jour pour Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761709.aspx)
    
- [Choisir comment gérer les mises à jour pour Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [Configurer les paramètres de mise à jour pour Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761708.aspx)
    
  **La fréquence d’obtenir des mises à jour de la fonctionnalité**
  
Outre où obtenir des mises à jour, vous pouvez également contrôler la fréquence à laquelle vous obtenez les nouvelles fonctionnalités pour la Skype pour client d’entreprise. Les deux options sont les suivantes :
  
- Obtenir des mises à jour de la fonctionnalité tous les mois, s’il existe des nouvelles fonctionnalités
    
- Obtenir les fonctionnalités mises à jour tous les six mois
    
Pour certaines organisations, qu’ils souhaitent tester les nouvelles fonctionnalités, afin qu’ils souhaitent obtenir des mises à jour de la fonctionnalité uniquement deux fois par an au lieu de chaque mois.
  
Vous pouvez contrôler la fréquence à laquelle vous obtenez les mises à jour de la fonctionnalité à l’aide de l’outil déploiement d’Office ou de la stratégie de groupe pour configurer le canal de mise à jour. Le permet de canal mensuel vous fonctionnalités mises à jour tous les mois (environ), tandis que le canal annuel séparées offre des fonctionnalités mises à jour tous les six mois. Pour plus d’informations sur les canaux, voir [vue d’ensemble des canaux de mise à jour pour Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).
  
## <a name="related-topics"></a>Rubriques connexes

[Configurer Skype entreprise Online](set-up-skype-for-business-online.md)
  
[Licences de compléments pour Skype Entreprise et Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
