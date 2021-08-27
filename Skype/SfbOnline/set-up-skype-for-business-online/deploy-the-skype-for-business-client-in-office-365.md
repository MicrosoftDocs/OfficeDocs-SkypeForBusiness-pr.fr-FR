---
title: Déployer le client Skype Entreprise client dans Microsoft 365 or Office 365
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Découvrez comment planifier et déployer des Skype Entreprise dans les petites, moyennes et grandes organisations et comment les mettre à la disposition de vos utilisateurs. '
ms.openlocfilehash: 3cfa319536c521ee4d0e3b297fd978071c93105d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589176"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>Déployer le client Skype Entreprise client dans Microsoft 365 ou Office 365

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Cet article explique les options **[](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** qui s’offrent à vous, en votre nom, pour déployer l’application Skype Entreprise aux membres de votre organisation.
  
Avant de déployer Skype Entreprise vers vos utilisateurs, assurez-vous d’avoir effectué les étapes 1 à 3 de l’article Configurer [Skype Entreprise Online.](set-up-skype-for-business-online.md) Ainsi, Skype Entreprise sera configuré avec votre domaine, chacun aura sa licence, et vous aurez configuré la messagerie instantanée et la configuration de la présence dans [Skype Entreprise Online](configure-presence-in-skype-for-business-online.md) pour votre organisation.
  
> [!NOTE]
> Pour installer l’Skype Entreprise, les utilisateurs doivent être administrateur local sur leur PC ou appareil. Sinon, il doit faire partie d’un groupe local qui peut installer des applications sur son PC ou appareil. Si vos utilisateurs ne sont pas autorisés à installer des logiciels sur leurs appareils, vous devez installer l’application Skype Entreprise pour eux. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Pour la plupart des petites et moyennes entreprises

 **Instructions d’installation détaillées :** Si vous avez une petite ou moyenne entreprise, nous vous recommandons de simplement demander à vos utilisateurs d’installer l’application Skype Entreprise sur leur PC. Pointez-les vers ces instructions : [Installez Skype Entreprise.](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb) S’ils utilisent des Mac, pointez-les vers Configurer [Lync pour Mac 2011 pour Office 365.](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88) L Skype Entreprise applyse de messagerie est installée séparément du reste Office applications.
  
 **Applications Microsoft 365 pour les grandes entreprises clients :** Si votre entreprise utilise une offre Office 365 qui inclut Applications Microsoft 365 pour les grandes entreprises, telle que l’offre E3, l’application Skype Entreprise est installée en même temps que vos utilisateurs téléchargent et installent Word, Excel, PowerPoint, etc. Cela signifie également qu’ils ne peuvent pas désinstaller Skype Entreprise, sauf s’ils désinstallent tous les Office.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Choisir de mettre des Skype Entreprise à la disposition de vos utilisateurs

En tant [qu’administrateur,](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) vous pouvez choisir de mettre l’application Skype Entreprise à la disposition de vos utilisateurs.
  
- **Pour contrôler si tous** les membres de votre entreprise ont accès au logiciel : connectez-vous au Centre d’administration Microsoft 365, allez à Installer mon **logiciel,** puis sélectionnez le logiciel que vous souhaitez mettre à la disposition des utilisateurs.
    
    ![Choisissez le logiciel que vous voulez mettre à la disposition des personnes de votre entreprise.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- Pour contrôler si des personnes spécifiques de votre entreprise obtiennent le logiciel : connectez-vous au Centre d’administration Microsoft 365, accédez à Utilisateurs actifs, sélectionnez la personne à qui vous voulez accorder l’accès au logiciel, puis cliquez sur Modifier en fonction des  >   **licences** de produit et activez ou désactiver la licence. 
    
    ![Choisissez les logiciels que vous souhaitez que l’utilisateur accède.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Pour savoir quels plans sont affectés aux membres de votre organisation, connectez-vous au Centre d’administration Microsoft 365 > **Utilisateurs**  >  actifs. Sélectionnez la personne dans la liste, puis regardez sous **Licences de produit.** Si vous utilisez le Centre d’administration classique, regardez sous **Licence affectée.** 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Déploiement manuel de Skype Entreprise vers vos utilisateurs
<a name="bkmk_manual_1"> </a>

Si vous souhaitez que vos utilisateurs installent l’application Skype Entreprise à partir d’un emplacement sur votre réseau plutôt que d’Internet, vous pouvez télécharger les fichiers d’installation. Pour ce faire, voir la section **Déployer manuellement** les logiciels des utilisateurs du Centre d’administration Microsoft 365. Vous pouvez ensuite sélectionner **Installer et** enregistrer le fichier d.exe dans un emplacement réseau.
  
Vous pouvez également télécharger l’application Skype Entreprise Basic pour vos utilisateurs. Vous pouvez télécharger [Microsoft Skype Entreprise Basic (32 ou 64 bits).](https://www.microsoft.com/download/details.aspx?id=49440)
  
Pour les applications de Skype Entreprise complètes et de base, après avoir téléchargé les fichiers d’installation, vous devrez envoyer manuellement (par courrier électronique, par exemple) le chemin d’accès réseau aux utilisateurs afin qu’ils peuvent exécuter le programme d’installation pour installer l’application sur leur ordinateur.
  
Vous pouvez également utiliser ces téléchargements pour déployer l’application Skype Entreprise sur les ordinateurs de vos utilisateurs à l’aide de vos outils et processus de déploiement de logiciels existants.
  
## <a name="for-larger-and-enterprise-organizations"></a>Pour les grandes organisations et les grandes entreprises

> [!NOTE]
> Cette section s’applique uniquement à l’application Skype Entreprise disponible via Office 365 plans proposés. Si votre organisation utilise une version sous licence en volume de l’application Skype Entreprise (basée sur Windows Installer (MSI), voir Personnaliser l’installation du client Windows dans [Skype Entreprise Server.](../../SfbServer/deploy/deploy-clients/customize-windows-client-installation.md)
  
Dans de nombreuses entreprises ou grandes organisations, les utilisateurs ne sont pas autorisés à installer des logiciels sur leurs ordinateurs. Les services informatiques déploient les logiciels nécessaires sur les ordinateurs des utilisateurs. Les services informatiques souhaitent peut-être également contrôler la quantité d’Internet ou de bande passante réseau utilisée dans leur organisation, de sorte qu’ils préfèrent installer un logiciel à partir d’un emplacement à proximité de leur réseau plutôt que via Internet ou sur le réseau d’entreprise.
  
Avec Office 365, vous avez plusieurs options pour déployer l’application Skype Entreprise si vous voulez contrôler la provenance de son installation. Voici quelques-unes de ces options :
  
- Téléchargez l’Skype Entreprise sur votre réseau local à partir du Centre d’administration Microsoft 365, comme décrit dans la section Déploiement Skype Entreprise [manuellement pour vos utilisateurs.](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)
    
- Utilisez **[l Office de déploiement pour](https://go.microsoft.com/fwlink/p/?LinkID=626065)** télécharger l’Applications Microsoft 365 pour les grandes entreprises ou l’Skype Entreprise sur votre réseau local. Ensuite, utilisez l’Office déploiement pour déployer l’application sur les ordinateurs de vos utilisateurs. L Office de déploiement vous permet de contrôler certains aspects du déploiement, tels que les langues et la version (32 bits ou 64 bits).
    
- Utilisez vos outils et processus de déploiement de logiciels existants, tels que Microsoft Endpoint Configuration Manager, pour déployer Applications Microsoft 365 pour les grandes entreprises ou l’application Skype Entreprise vos utilisateurs. Vous pouvez utiliser vos outils [](https://go.microsoft.com/fwlink/p/?LinkID=626065) et processus existants avec l’outil Déploiement Office ou avec les logiciels que vous avez téléchargés à partir du Centre d’administration Microsoft 365.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Plus d’informations sur l’utilisation de l Office de déploiement

Pour plus d’informations sur le téléchargement de l’outil Déploiement d’Office et sur l’installation de l’application Skype Entreprise et d’autres applications clientes Office 365, voir Gérer les paramètres de téléchargement de [logiciels dans Office 365.](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)
  
Voici un aperçu des étapes à suivre dans l’utilisation de l’outil Déploiement d Office pour déployer une application :
  
1. **[Téléchargez la version la plus Office l’outil Déploiement](https://www.microsoft.com/download/details.aspx?id=49117)** à partir du Centre de téléchargement Microsoft.
    
2. Créez le fichier configuration.xml à utiliser avec l’outil Déploiement d’Office qui possède les paramètres d’application client de votre souhaitez, tels que la définition de la version (32 bits ou 64 bits), la langue d’installation, etc.
    
3. Utilisez l’Office déploiement et le fichier configuration.xml pour télécharger les fichiers d’installation sur votre réseau local ou interne à partir du Office réseau de distribution de contenu (CDN).
    
4. Utilisez Office outil Déploiement et la configuration.xml installer les applications clientes Office, notamment l’Skype Entreprise client.
    
Pour plus d’informations sur l’utilisation de l Office de déploiement et configuration.xml fichiers, consultez les articles suivants :
  
- [Office Vue d’ensemble de l’outil Déploiement](/deployoffice/overview-office-deployment-tool)
    
- [Configuration.xml de configuration](/deployoffice/office-deployment-tool-configuration-options)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>Plus d’informations sur l’utilisation de Microsoft Endpoint Configuration Manager

Vous pouvez utiliser vos outils et processus de déploiement de logiciels existants, tels que Microsoft Endpoint Configuration Manager, pour déployer l’Skype Entreprise logiciel. Vous pouvez utiliser ces outils et processus avec le logiciel que vous téléchargez à partir du Centre d’administration Microsoft 365 ou avec l Office de déploiement.
  
Pour plus d’informations sur l’utilisation de Configuration Manager pour déployer un logiciel, consultez les articles suivants :
  
- [Créer des applications dans Configuration Manager](/configmgr/apps/deploy-use/create-applications)
    
- [Déployer des applications avec Configuration Manager](/configmgr/apps/deploy-use/deploy-applications)
    
Si vous déployez l’application Skype Entreprise dans le cadre du déploiement d’Applications Microsoft 365 pour les grandes entreprises, voir Gérer Applications Microsoft 365 pour les grandes entreprises [avec Configuration Manager.](/configmgr/sum/deploy-use/manage-office-365-proplus-updates)
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Planification des mises à jour de l Skype Entreprise appl

Dans le cadre du déploiement de l Skype Entreprise, vous devez envisager la manière dont vous souhaitez obtenir les mises à jour une fois que Skype Entreprise est installé. Ces mises à jour peuvent inclure de nouvelles fonctionnalités, des mises à jour de sécurité ou d’autres mises à jour telles que des améliorations de la stabilité ou des performances. Les deux principaux facteurs à prendre en compte sont les éléments :
  
- D’où voulez-vous obtenir les mises à jour ?
    
- À quelle fréquence souhaitez-vous obtenir les mises à jour des fonctionnalités ?
    
Vous pouvez contrôler la provenance et la fréquence des mises à jour, mais vous ne pouvez pas choisir des mises à jour spécifiques de la sécurité ou autres.
  
 **Où obtenir des mises à jour**
  
Par défaut, une fois Skype Entreprise l’application installée, les mises à jour sont téléchargées automatiquement à partir d’Internet lorsqu’elles sont disponibles auprès de Microsoft. Si vous souhaitez contrôler plus en détail quand les mises à jour se produisent ou à partir d’où elles sont installées, vous pouvez utiliser l’outil Déploiement d’Office ou une stratégie de groupe pour configurer cela.
  
Par exemple, de nombreuses organisations souhaitent tester les mises à jour avec un groupe d’utilisateurs avant de les déployer dans l’ensemble de l’organisation. Pour ce faire, utilisez l’outil Déploiement d’Office ou une stratégie de groupe pour configurer l’application Skype Entreprise afin d’obtenir les mises à jour à partir d’un emplacement spécifique de votre réseau, plutôt que automatiquement à partir d’Internet. Ensuite, vous pouvez utiliser l Office de déploiement pour télécharger les mises à jour tous les mois sur votre réseau local.
  
Pour plus d’informations sur le fonctionnement des mises à jour Office 365 logiciels, consultez les articles suivants :
  
- [Vue d’ensemble du processus de mise à jour Applications Microsoft 365 pour les grandes entreprises](/deployoffice/overview-update-process-microsoft-365-apps)
    
- [Choisir comment gérer les mises à jour pour les Applications Microsoft 365 pour les grandes entreprises](/deployoffice/choose-how-manage-updates-microsoft-365-apps)
    
- [Configurer les paramètres de mise à jour pour Applications Microsoft 365 pour les grandes entreprises](/deployoffice/configure-update-settings-microsoft-365-apps)
    
  **Fréquence d’accès aux mises à jour des fonctionnalités**
  
En plus de la provenance des mises à jour, vous pouvez également contrôler la fréquence d’accès aux nouvelles fonctionnalités du client Skype Entreprise client. Les deux choix possibles sont les suivants :
  
- Obtenir des mises à jour mensuelles des fonctionnalités en cas de nouvelles fonctionnalités
    
- Obtenir des mises à jour des fonctionnalités tous les six mois
    
Certaines organisations ont besoin de temps pour tester les nouvelles fonctionnalités, et souhaitent donc obtenir des mises à jour deux fois par an seulement, plutôt que tous les mois.
  
Vous pouvez contrôler la fréquence d’installation des mises à jour de fonctionnalités à l’aide de l Office de déploiement de l’appareil ou d’une stratégie de groupe pour configurer le canal de mise à jour. Le Canal mensuel propose des mises à jour mensuelles (environ), tandis que le canal Semi-Annual vous propose des mises à jour tous les six mois. Pour plus d’informations sur les canaux, voir [Vue d’ensemble des canaux de mise à jour Applications Microsoft 365 pour les grandes entreprises.](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)
  
## <a name="related-topics"></a>Rubriques connexes

[Configurer Skype entreprise Online](set-up-skype-for-business-online.md)
  
[Licences de compléments pour Skype Entreprise et Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
