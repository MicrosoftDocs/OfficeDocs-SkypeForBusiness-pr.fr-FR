---
title: Déploiement du client Skype entreprise dans Office 365
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Découvrez comment planifier et déployer Skype entreprise dans les petites, moyennes et grandes organisations et comment le mettre à la disposition de vos utilisateurs. '
ms.openlocfilehash: 38c35344b6a19f99b153f214c42eacecb71d7c8a
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628450"
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a>Déploiement du client Skype entreprise dans Office 365

Cet article explique comment vous, l' **[administrateur](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)**, pouvez déployer l’application Skype entreprise pour les membres de votre organisation.
  
Avant de déployer Skype entreprise pour vos utilisateurs, assurez-vous que vous avez terminé les étapes 1-3 dans l’article [configuration de Skype entreprise Online](set-up-skype-for-business-online.md). De cette façon, Skype entreprise sera configuré avec votre domaine, tout le monde disposera de ses licences et vous aurez configuré la messagerie instantanée et [configurerez la présence dans Skype entreprise Online](configure-presence-in-skype-for-business-online.md) pour votre organisation.
  
> [!NOTE]
> Pour que les utilisateurs puissent installer l’application Skype entreprise, ils doivent être administrateur local sur leur ordinateur ou appareil. Elle doit également faire partie d’un groupe local qui peut installer des applications sur son PC ou ses appareils. Si les utilisateurs ne sont pas autorisés à installer le logiciel sur leurs appareils, vous devez installer l’application Skype entreprise. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Pour la plupart des petites et moyennes entreprises

 **Instructions d’installation détaillées :** Si votre entreprise est petite ou moyenne, il est recommandé de demander aux utilisateurs d’installer l’application Skype entreprise sur leur ordinateur. Pointez sur ces instructions : [Installez Skype entreprise](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb). S’ils utilisent des Mac, pointez-les pour [configurer Lync pour Mac 2011 pour Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88). L’application Skype entreprise est installée indépendamment du reste des applications Office.
  
 **Clients Office 365 ProPlus :** Si votre entreprise utilise un plan Office 365 incluant Office 365 ProPlus, comme le plan E3, l’application Skype entreprise est installée en même temps que vos utilisateurs pour télécharger et installer Word, Excel, PowerPoint, etc. Cela signifie également que les utilisateurs ne peuvent pas désinstaller Skype entreprise, sauf s’ils désinstallent la totalité d’Office.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Choisir de mettre Skype entreprise à la disposition de vos utilisateurs

En tant qu' [administrateur](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) , vous pouvez choisir de mettre l’application Skype entreprise à la disposition de vos utilisateurs.
  
- **Pour savoir si tous les utilisateurs de votre entreprise reçoivent le logiciel**: Connectez-vous au centre d’administration 365 Microsoft, accédez à **installer mon logiciel**, puis sélectionnez les logiciels que vous voulez rendre disponibles pour les utilisateurs.
    
    ![Choisissez le logiciel que vous voulez mettre à la disposition des membres de votre entreprise.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **Pour déterminer si des personnes spécifiques au sein de votre entreprise obtiennent le logiciel**: Connectez-vous au **Centre d’administration** > 365 Microsoft, accédez à utilisateurs**actifs**, sélectionnez la personne à laquelle vous voulez accorder l’accès au logiciel, puis cliquez sur **modifier** en regard de **licences de produits** , puis activez ou désactivez la licence.
    
    ![Sélectionnez les logiciels auxquels l’utilisateur doit accéder.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Si vous avez besoin de connaître les plans attribués aux membres de votre organisation, connectez-vous au centre d’administration 365 Microsoft > **utilisateurs** > **actifs**. Sélectionnez la personne dans la liste, puis cliquez sur **licences de produit**. Si vous utilisez le centre d’administration classique, reportez-vous à la section **licence attribuée**. 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Déploiement manuel de Skype entreprise pour vos utilisateurs
<a name="bkmk_manual_1"> </a>

Si vous souhaitez que les utilisateurs installent l’application Skype entreprise à partir d’un emplacement sur votre réseau plutôt que d’Internet, vous pouvez télécharger les fichiers d’installation. Pour ce faire, accédez à la section **déploiement manuel du logiciel utilisateur** du centre d’administration 365 Microsoft. Vous pouvez ensuite sélectionner **installer** et enregistrer le fichier Setup. exe sur un emplacement réseau.
  
Une autre option consiste à télécharger l’application Skype entreprise Basic pour vos utilisateurs. Vous pouvez télécharger [Microsoft Skype entreprise Basic (32 ou 64)](https://www.microsoft.com/download/details.aspx?id=49440).
  
Pour les applications Skype entreprise complètes et de base, une fois que vous avez téléchargé les fichiers d’installation, vous devez effectuer une expédition manuelle (par exemple, dans un message électronique) du chemin réseau vers les utilisateurs afin qu’ils puissent exécuter le programme d’installation pour installer l’application sur leur ordinateur.
  
Vous pouvez également utiliser ces téléchargements pour déployer l’application Skype entreprise auprès de vos utilisateurs à l’aide de vos outils et processus de déploiement de logiciels existants.
  
## <a name="for-larger-and-enterprise-organizations"></a>Pour les grandes organisations et les grandes entreprises

> [!NOTE]
> Cette section s’applique uniquement à l’application Skype entreprise disponible via les offres Office 365. Si votre organisation utilise une version sous licence en volume de l’application Skype entreprise, qui est basée sur Windows Installer (MSI), voir [personnaliser l’installation du client Windows dans Skype entreprise Server](https://technet.microsoft.com/library/jj204934.aspx).
  
Dans de nombreuses entreprises ou grandes organisations, les utilisateurs ne sont pas autorisés à installer le logiciel sur leur ordinateur. Au lieu de cela, les services informatiques déploient les logiciels nécessaires sur les ordinateurs des utilisateurs. Les services informatiques peuvent également vouloir contrôler la quantité de bande passante Internet ou réseau utilisée au sein de leur organisation, de sorte qu’ils souhaitent installer le logiciel à partir d’un emplacement proche sur leur réseau plutôt que sur Internet ou sur le réseau d’entreprise.
  
Dans Office 365, plusieurs options s’offrent à vous pour le déploiement de l’application Skype entreprise, si vous souhaitez contrôler l’endroit où elle est installée. Voici quelques-unes de ces options :
  
- Téléchargez l’application Skype entreprise sur votre réseau local à partir du centre d’administration Microsoft 365, comme décrit dans la rubrique [déploiement manuel de Skype entreprise pour vos utilisateurs](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).
    
- Utilisez l' **[outil déploiement d’Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** pour télécharger l’application Office 365 ProPlus ou l’application Skype entreprise sur votre réseau local. Ensuite, utilisez l’outil déploiement d’Office pour déployer l’application auprès de vos utilisateurs. L’outil déploiement d’Office vous donne la possibilité de contrôler certains aspects du déploiement, tels que les langues et la version (32 bits ou 64 bits).
    
- Utilisez vos outils et processus de déploiement de logiciels existants, tels que Microsoft Endpoint Configuration Manager, pour déployer Office 365 ProPlus ou l’application Skype entreprise pour vos utilisateurs. Vous pouvez utiliser vos outils et processus existants à l’aide de l' [outil déploiement d’Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) ou du logiciel que vous avez téléchargé à partir du centre d’administration Microsoft 365.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Plus d’informations sur l’utilisation de l’outil déploiement d’Office

Pour plus d’informations sur le téléchargement de l’outil déploiement d’Office et sur l’installation de l’application Skype entreprise et d’autres applications clientes Office 365, voir [gérer les paramètres de téléchargement de logiciels dans Office 365](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360).
  
Voici un aperçu des étapes nécessaires à l’utilisation de l’outil déploiement d’Office pour déployer une application :
  
1. **[Télécharger l’outil déploiement d’Office](https://www.microsoft.com/download/details.aspx?id=49117)** le plus récent à partir du centre de téléchargement Microsoft.
    
2. Créez le fichier Configuration. XML à utiliser avec l’outil déploiement d’Office qui inclut les paramètres de l’application cliente que vous souhaitez utiliser, par exemple, la définition de la version (32 bits ou 64 bits), la langue d’installation, etc.
    
3. Utilisez l’outil déploiement d’Office et le fichier de configuration. xml pour télécharger les fichiers d’installation sur votre réseau local ou interne à partir du réseau de distribution de contenu (CDN) Office.
    
4. Utilisez l’outil déploiement d’Office et le fichier de configuration. xml pour installer les applications client Office, dont l’application Skype entreprise.
    
Pour plus d’informations sur l’outil déploiement d’Office et le fichier Configuration. xml, reportez-vous aux articles suivants :
  
- [Vue d’ensemble de l’outil déploiement d’Office](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Paramètres de configuration. Xml](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>Plus d’informations sur l’utilisation de Microsoft Endpoint Configuration Manager

Vous pouvez utiliser vos outils et processus de déploiement de logiciels existants, tels que Microsoft Endpoint Configuration Manager, pour déployer l’application Skype entreprise. Vous pouvez utiliser ces outils et processus avec le logiciel que vous téléchargez à partir du centre d’administration Microsoft 365 ou de l’outil déploiement d’Office.
  
Pour plus d’informations sur l’utilisation du gestionnaire de configuration pour déployer un logiciel, reportez-vous aux articles suivants :
  
- [Créer des applications dans Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/create-applications)
    
- [Déploiement d’applications avec Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
    
Si vous déployez l’application Skype entreprise dans le cadre du déploiement d’Office 365 ProPlus, reportez-vous [à gérer office 365 ProPlus avec Configuration Manager](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates).
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Planification des mises à jour de l’application Skype entreprise

Dans le cadre du déploiement de l’application Skype entreprise, vous devez déterminer la façon dont vous voulez obtenir les mises à jour après l’installation de Skype entreprise. Ces mises à jour peuvent inclure de nouvelles fonctionnalités, des mises à jour de sécurité ou des mises à jour non liées à la sécurité, telles que des mises à jour qui permettent d’améliorer la stabilité et les performances. Les deux principaux points à prendre en considération sont les suivants :
  
- L’emplacement à partir duquel vous voulez obtenir les mises à jour
    
- À quelle fréquence souhaitez-vous obtenir les mises à jour de fonctionnalités ?
    
Vous pouvez contrôler la source et la fréquence des mises à jour, mais vous ne pouvez pas choisir des mises à jour spécifiques de la sécurité ou non liées à la sécurité.
  
 **Où obtenir les mises à jour de**
  
Par défaut, une fois l’application Skype entreprise installée, les mises à jour sont automatiquement téléchargées à partir d’Internet lorsqu’elles sont disponibles auprès de Microsoft. Si vous voulez plus de contrôle lors de la mise à jour des mises à jour ou des mises à jour de l’installation, vous pouvez utiliser l’outil déploiement d’Office ou une stratégie de groupe pour les configurer.
  
Par exemple, de nombreuses organisations souhaitent tester les mises à jour d’un groupe d’utilisateurs avant de les déployer au sein de l’organisation. Pour cela, vous pouvez utiliser l’outil déploiement d’Office ou une stratégie de groupe pour configurer l’application Skype entreprise de manière à obtenir les mises à jour à partir d’un emplacement spécifique de votre réseau, au lieu d’être automatiquement à partir d’Internet. Vous pouvez ensuite utiliser l’outil déploiement d’Office pour télécharger chaque mois les mises à jour sur votre réseau local.
  
Pour plus d’informations sur le fonctionnement des mises à jour pour le logiciel Office 365, consultez les articles suivants :
  
- [Présentation de la procédure de mise à jour d’Office 365 ProPlus](https://technet.microsoft.com/library/dn761709.aspx)
    
- [Choisir comment gérer les mises à jour d’Office 365 ProPlus](https://technet.microsoft.com/library/dn761707.aspx)
    
- [Configurer les paramètres de mise à jour pour Office 365 ProPlus](https://technet.microsoft.com/library/dn761708.aspx)
    
  **Fréquence d’obtention des mises à jour de fonctionnalités**
  
En plus de l’endroit où vous obtenez les mises à jour, vous pouvez également contrôler la fréquence à laquelle vous obtenez de nouvelles fonctionnalités pour le client Skype entreprise. Les deux choix possibles sont les suivants :
  
- Obtenez les mises à jour des fonctionnalités tous les mois, s’il existe de nouvelles fonctionnalités.
    
- Obtenez les mises à jour des fonctionnalités tous les six mois
    
Pour certaines organisations, le moment est venu de tester les nouvelles fonctionnalités, afin qu’elles ne soient disponibles qu’à deux fois par an au lieu de chaque mois.
  
Vous pouvez contrôler la fréquence des mises à jour des fonctionnalités en utilisant l’outil déploiement d’Office ou une stratégie de groupe pour configurer le canal de mise à jour. Le canal mensuel vous donne accès à des mises à jour mensuelles (approximativement), tandis que le canal semi-annuel vous donne des mises à jour des fonctionnalités tous les six mois. Pour plus d’informations sur les canaux, voir [Présentation des canaux de mise à jour d’Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).
  
## <a name="related-topics"></a>Rubriques connexes

[Configurer Skype entreprise Online](set-up-skype-for-business-online.md)
  
[Licences de compléments pour Skype Entreprise et Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
