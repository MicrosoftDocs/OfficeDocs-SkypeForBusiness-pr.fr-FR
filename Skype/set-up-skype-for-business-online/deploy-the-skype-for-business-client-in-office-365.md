---
title: "Déployer le Skype pour client d’entreprise dans Office 365"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Découvrez comment planifier et déployer Skype pour l’entreprise dans les petites, moyennes et grandes entreprises et le rendre accessible à vos utilisateurs. "
ms.openlocfilehash: bbcbc632110ea466d6a3fdf566c6f3498e3bd751
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a>Déployer le Skype pour client d’entreprise dans Office 365

Cet article décrit les options pour comment, l' **[administration](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)**, déployer le Skype pour application métier aux personnes de votre organisation.
  
Avant de déployer Skype pour entreprise à vos utilisateurs, vérifiez que vous avez effectué les étapes 1 à 3 dans l’article [paramétrer Skype pour l’activité en ligne](set-up-skype-for-business-online.md). De cette façon, Skype pour entreprises est mis en place avec votre domaine, tout le monde auront leurs licences et vous aurez configuré messagerie instantanée et [présence de configurer dans Skype pour l’activité en ligne](configure-presence-in-skype-for-business-online.md) pour votre organisation.
  
> [!NOTE]
> Pour les utilisateurs à installer le Skype pour l’application d’entreprise, ils doivent être des administrateurs locaux sur leurs PC ou un périphérique. Ou bien, ils devront faire partie d’un groupe local qui peut installer des applications sur leur PC ou des périphériques. Si vos utilisateurs ne sont pas autorisés à installer des logiciels sur leurs périphériques, vous devrez installer le Skype pour application métier pour eux. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Pour la plupart des entreprises de petite et moyenne taille

 **Instructions d’installation étape par étape :** Si vous avez une petite ou moyenne entreprise, il est recommandé que vous demandez simplement à vos utilisateurs d’installer le Skype pour l’application d’entreprise sur leur PC. Les pointer à ces instructions : [Installation de Skype pour les entreprises](https://support.office.com/en-us/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb?ui=en-US&rs=en-US&ad=US). Si elles sont à l’aide de Macs, pointez les [Configurer Lync pour Mac 2011 pour Office 365](https://support.office.com/en-us/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88?ui=en-US&rs=en-US&ad=US). Le Skype pour l’application d’entreprise est installé séparément du reste des applications Office.
  
 **Les clients office 365 ProPlus :** Si votre entreprise utilise un plan d’Office 365 incluant Office 365 ProPlus, tel que le plan de E3, le Skype pour l’application d’entreprise est installé en même temps que vos utilisateurs à télécharger et installer Word, Excel, PowerPoint, etc.. Cela signifie également qu’ils ne peut pas désinstaller Skype pour les entreprises, sauf si elles désinstaller tout Office.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Indiquez si vous souhaitez rendre Skype pour entreprise disponible aux utilisateurs

Tant que l' [administrateur](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US) , vous pouvez choisir s’il faut rendre le Skype pour application métier disponibles aux utilisateurs.
  
- **Pour contrôler si tous les employés de votre société Obtient le logiciel**: se connecter à Office 365 admin center, accédez à **installation de mon logiciel**et puis sélectionnez le logiciel que vous souhaitez être disponible pour les utilisateurs.
    
    ![Choisir les logiciels que vous souhaitez rendre disponibles aux personnes de votre société.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **Pour contrôler si certaines personnes de votre société obtenir le logiciel**: se connecter à Office 365 centre d’administration, ouvrez **utilisateurs** > **utilisateurs actifs**, sélectionnez la personne à qui vous souhaitez donner accès au logiciel, puis cliquez sur **Modifier** en regard des **licences de produit** et activer la licence ou désactiver.
    
    ![Choisir les logiciels que l’utilisateur d’accéder.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Si vous avez besoin voir quels sont les projets associés à des personnes de votre organisation, vous connecter au centre d’administration d’Office 365 Nouveau > **utilisateurs** > **utilisateurs actifs**. Sélectionnez la personne dans la liste, puis regardez sous **licences de produits**. Si vous utilisez le centre d’administration Office 365 classique, regardez sous **licence d’affecté**. 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Déploiement manuel à vos utilisateurs de Skype pour les entreprises
<a name="bkmk_manual_1"> </a>

Si vous souhaitez que vos utilisateurs d’installer le Skype pour l’application d’entreprise à partir d’un emplacement sur votre réseau et non à partir d’Internet, vous pouvez télécharger les fichiers d’installation. Pour ce faire, accédez à la section **déployer manuellement le logiciel utilisateur** du Centre Office 365 admin. Vous pouvez ensuite sélectionnez **installer** et enregistrer le fichier .exe d’installation vers un emplacement réseau.
  
Une autre option consiste à télécharger le Skype pour l’application de base de Business pour vos utilisateurs. Vous pouvez télécharger [Skype Microsoft pour Business Basic (32 ou 64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=49440).
  
Pour les deux le complet et basic Skype pour les applications métier, après avoir téléchargé les fichiers d’installation, vous devrez envoyer manuellement (par exemple, dans l’e-mail) le chemin d’accès réseau aux utilisateurs afin qu’ils peuvent exécuter le programme d’installation pour installer l’application sur leur ordinateur.
  
Vous pouvez également utiliser ces téléchargements pour déployer le Skype pour l’application d’entreprise à vos utilisateurs à l’aide de vos outils de déploiement de logiciels existants et les processus.
  
## <a name="for-larger-and-enterprise-organizations"></a>Pour les grandes entreprises,

> [!NOTE]
> Cette section s’applique uniquement à la Skype pour application métier disponible par le biais de plans d’Office 365. Si votre organisation utilise une version de licence en volume de la Skype pour l’application d’entreprise, qui est basé sur Windows Installer (MSI), consultez [Personnaliser l’installation du client dans Skype pour Business Server 2015](https://technet.microsoft.com/en-us/library/jj204934.aspx). 
  
Dans de nombreuses entreprises ou les organisations de grande taille, les utilisateurs ne sont pas autorisés à installer des logiciels sur leurs ordinateurs. Au lieu de cela, les départements informatiques déploiement le logiciel sur les ordinateurs des utilisateurs. Les départements informatiques peuvent également contrôler la quantité de la bande passante Internet ou réseau utilisée dans leur organisation, afin qu’elles souhaitent installer le logiciel sur Internet ou sur le réseau d’entreprise à partir d’un emplacement proche sur leur réseau et non à partir de.
  
Avec Office 365, vous disposez de plusieurs options pour déployer la Skype pour l’application d’entreprise si vous souhaitez contrôler où il est installé dans. Certaines de ces options sont les suivantes :
  
- Télécharger le Skype pour application métier à votre réseau local à partir du centre d’administration Office 365, comme indiqué dans [déploiement manuel Skype pour entreprise à vos utilisateurs](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).
    
- Pour télécharger Office 365 ProPlus ou le Skype pour application métier à votre réseau local, utilisez l' **[Outil de déploiement de Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** . Ensuite, utilisez l’outil de déploiement de Microsoft Office pour déployer l’application à vos utilisateurs. L’outil de déploiement de Office vous offre la possibilité de contrôler certains aspects du déploiement, telles que les langues et la version (32 bits ou 64 bits).
    
- Utiliser vos processus, tels que System Center Configuration Manager et les outils de déploiement de logiciel existants pour déployer Office 365 ProPlus ou le Skype pour l’application d’entreprise à vos utilisateurs. Vous pouvez utiliser votre processus et les outils existants avec l' [Outil de déploiement de Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) ou le logiciel que vous avez téléchargé à partir du centre d’administration Office 365.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Plus d’informations sur l’utilisation de l’outil de déploiement de Microsoft Office

Pour plus d’informations sur le téléchargement de l’outil de déploiement de Microsoft Office et plus d’informations sur l’installation de la Skype pour application métier et d’autres applications de client Office 365, voir [Gérer les logiciels d’utilisateur dans Office 365](https://support.office.com/en-us/article/c13051e6-f75c-4737-bc0d-7685dcedf360).
  
Voici une vue d’ensemble des étapes impliquées dans l’utilisation de l’outil de déploiement de Microsoft Office pour déployer une application :
  
1. **[Télécharger l’outil de déploiement d’Office plus récente](https://www.microsoft.com/en-us/download/details.aspx?id=49117)** à partir du Microsoft Download Center.
    
2. Créez le fichier configuration.xml pour être utilisé avec l’outil de déploiement d’Office avec les paramètres d’application client que vous souhaitez définir la version (32 bits ou 64 bits), de la langue d’installation, etc..
    
3. Pour télécharger les fichiers d’installation à votre réseau interne ou externe de l’Office réseau CDN (Content Delivery), utilisez l’outil de déploiement de Microsoft Office et le fichier configuration.xml.
    
4. Outil de déploiement de Office utiliser et le configuration.xml pour installer les applications client Office, y compris le Skype pour l’application d’entreprise.
    
Pour plus d’informations sur l’utilisation de l’outil de déploiement d’Office et le fichier configuration.xml, consultez les articles suivants :
  
- [Présentation de l’outil de déploiement Office](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Paramètres de configuration.Xml](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-system-center-configuration-manager"></a>Plus d’informations sur l’utilisation de System Center Configuration Manager

Pour déployer le Skype pour l’application d’entreprise, vous pouvez utiliser vos processus, tels que Microsoft System Center Configuration Manager et les outils de déploiement de logiciels existants. Vous pouvez utiliser ces outils et les processus avec le logiciel que vous téléchargez à partir du centre d’administration Office 365 ou avec l’outil de déploiement de Microsoft Office.
  
Pour plus d’informations sur l’utilisation de Configuration Manager pour déployer des logiciels, consultez les articles suivants :
  
- [Comment faire pour créer des Applications dans Configuration Manager](https://technet.microsoft.com/en-us/library/gg682159.aspx)
    
- [Comment faire pour déployer des Applications dans Configuration Manager](https://technet.microsoft.com/en-us/library/gg682082.aspx)
    
Si vous déployez le Skype pour l’application d’entreprise dans le cadre du déploiement d’Office 365 ProPlus, voir [Déployer Office 365 ProPlus à l’aide de System Center Configuration Manager](https://technet.microsoft.com/en-us/library/dn708063.aspx).
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Planification des mises à jour à la Skype pour l’application d’entreprise

Dans le cadre du déploiement de la Skype pour l’application d’entreprise, vous devez prendre en compte la façon dont vous souhaitez obtenir des mises à jour après avoir installé Skype pour les entreprises. Ces mises à jour peuvent inclure des mises à jour de sécurité, de nouvelles fonctionnalités ou des mises à jour non relative à la sécurité, telles que les mises à jour qui offrent des améliorations de stabilité ou de performances. Les deux principales choses à prendre en compte sont les suivants :
  
- Où vous souhaitez obtenir des mises à jour
    
- La fréquence à laquelle vous souhaitez obtenir des mises à jour de la fonctionnalité
    
Alors que vous pouvez contrôler où obtenir des mises à jour et la fréquence à laquelle vous obtenez les mises à jour de la fonctionnalité, vous ne pouvez pas choisir les mises à jour de sécurité spécifique ou les mises à jour de sécurité vous obtenez.
  
 **Où obtenir des mises à jour à partir de**
  
Par défaut, après avoir installé le Skype pour une application métier, mises à jour téléchargerons automatiquement à partir d’Internet lorsqu’ils sont disponibles auprès de Microsoft. Si vous souhaitez plus de contrôle sur lorsque des mises à jour se produisent ou lorsque les mises à jour sont installées à partir de, vous pouvez utiliser l’outil de déploiement de Office ou de la stratégie de groupe configurer.
  
Par exemple, de nombreuses organisations souhaitent tester les mises à jour avec un groupe d’utilisateurs avant de les déployer dans toute l’organisation. Vous pouvez le faire à l’aide de l’outil de déploiement de Office ou de la stratégie de groupe pour configurer la Skype pour l’application d’entreprise pour obtenir automatiquement des mises à jour à partir d’un emplacement spécifique sur votre réseau, plutôt qu’à partir d’Internet. Ensuite, vous pouvez utiliser l’outil de déploiement de Microsoft Office pour télécharger les mises à jour tous les mois pour votre réseau local.
  
Pour plus d’informations sur le fonctionnement des mises à jour pour les logiciels Office 365, voir les articles suivants :
  
- [Vue d’ensemble du processus de mise à jour pour Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761709.aspx)
    
- [Choisir comment gérer les mises à jour pour Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [Configurer les paramètres de mise à jour pour Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761708.aspx)
    
 **La fréquence des mises à jour de la fonctionnalité**
  
En plus de vous où obtenez des mises à jour à partir de, vous pouvez également contrôler la fréquence à laquelle vous obtenez les nouvelles fonctionnalités pour le Skype pour client d’entreprise. Les deux choix sont les suivants :
  
- Obtenir des mises à jour de la fonctionnalité tous les mois, s’il existe des nouvelles fonctionnalités
    
- Obtenir des mises à jour de fonctionnalités tous les six mois
    
Pour certaines organisations, ils souhaitent tester les nouvelles fonctionnalités, afin qu’elles souhaitent obtenir des mises à jour de la fonctionnalité uniquement deux fois par an au lieu de chaque mois.
  
Vous pouvez contrôler la fréquence à laquelle vous obtenez des mises à jour de la fonctionnalité à l’aide de l’outil de déploiement de Office ou de la stratégie de groupe pour configurer le canal de mise à jour. L’offre mensuelle canal vous fonctionnalité mises à jour de chaque mois (environ), tandis que le canal de contrat semestriel offre des fonctionnalités mises à jour tous les six mois. Pour plus d’informations sur les chaînes, consultez [vue d’ensemble de canaux de mise à jour pour Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).
  
## <a name="related-topics"></a>Rubriques connexes

[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)
  
Pour en savoir plus, reportez-vous à la rubrique [Conférence rendez-vous dans Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  

