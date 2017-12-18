---
title: "Déploiement du client Skype Entreprise dans Office 365"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- httpsfix
- LeftNav_IT_O365
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
description: "Learn how to plan and deploy Skype for Business in small, medium, and large organizations and making it available to your users. "
---

# Déploiement du client Skype Entreprise dans Office 365

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Cet article explique comment vous, l' **[Attribuer des rôles d'administrateur dans Office 365](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)**, pouvez déployer l'application Skype Entreprise sur les stations des utilisateurs de votre entreprise.
  
Avant de déployer Skype Entreprise à vos utilisateurs, vérifiez que vous avez terminé les étapes 1 à 3 dans l'article [Configurer Skype Entreprise Online](set-up-skype-for-business-online.md). De cette façon, Skype Entreprise devront être définies avec votre domaine, tout le monde auront leurs licences et vous aurez configuré par messagerie instantanée et [Configuration de la présence dans Skype Entreprise Online](configure-presence-in-skype-for-business-online.md) pour votre organisation.
  
> [!NOTE]
> Pour les utilisateurs d'installer l'application Skype Entreprise, ils doivent être des administrateurs locales sur leur ordinateur ou appareil. Ou, elles devront être partie d'un groupe local qui peut installer des applications sur leur ordinateur ou d'un appareil. Si vos utilisateurs ne sont pas autorisés à installer des logiciels sur leurs appareils mobiles, vous devez installer l'application Skype Entreprise pour les. 
  
## Pour la plupart des petites et moyennes entreprises

 **Instructions d'installation étape par étape :** Si vous avez une petite ou moyenne entreprise, nous vous recommandons de que vous demandez simplement à vos utilisateurs pour installer l'application Skype Entreprise sur leur ordinateur. Faire pointer vers ces instructions :[Installer Skype Entreprise](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb). S'ils utilisent Mac, orientez-les vers [Configuration de Skype Entreprise (Lync) pour Mac 2011 pour Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88). L'application Skype Entreprise est installée séparément du reste des applications Office.
  
 **Clients office 365 ProPlus :** Si votre entreprise utilise un plan Office 365 incluant Office 365 ProPlus, tels que le plan E3, l'application Skype Entreprise est installée en même temps vos utilisateurs téléchargement et installer Word, Excel, PowerPoint, etc.. Cela signifie également qu'ils ne peuvent pas désinstaller Skype Entreprise, sauf si elles désinstaller toutes d'Office.
  
### Choisir de mettre Skype Entreprise à la disposition ou non de vos utilisateurs

En tant que l' [Attribuer des rôles d'administrateur dans Office 365](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) , vous pouvez choisir si vous souhaitez rendre l'application Skype Entreprise disponible à vos utilisateurs.
  
- **Pour contrôler si tous les membres de votre société Obtient le logiciel**: signer dans à la Centre d'administration Office 365, accédez à **installer mon logiciel**, puis sélectionnez le logiciel que vous souhaitez soit disponible pour les utilisateurs.
    
    ![Choose the software you want to make available to the people in your company.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **Pour contrôler si certaines personnes de votre société obtenir les logiciels**: se connecter à la Centre d'administration Office 365, accédez à **utilisateurs** > **utilisateurs actifs**, sélectionnez la personne qui vous voulez accorder l'accès au logiciel, puis cliquez sur **Modifier** en regard de ** Licences de produits** et activer ou désactiver les la licence.
    
    ![Choose which software you want the user to access.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Si vous avez besoin de voir quelles offres sont affectées aux personnes de votre organisation, connectez-vous à la nouvelle Centre d'administration Office 365 > **utilisateurs** > **utilisateurs actifs**. Sélectionnez la personne dans la liste, puis regardez sous **licences de produits**. Si vous utilisez le classique Centre d'administration Office 365, regardez sous **licence attribuée**. 
  
### Déploiement manuel de Skype Entreprise pour vos utilisateurs
<a name="bkmk_manual_1"> </a>

Si vous souhaitez que vos utilisateurs pour installer l'application Skype Entreprise à partir d'un emplacement sur votre réseau et non à partir d'Internet, vous pouvez télécharger les fichiers d'installation. Pour ce faire, accédez à la section **déployer manuellement le logiciel de l'utilisateur** de la Centre d'administration Office 365. Vous pouvez puis sélectionnez **installer** et enregistrez le fichier .exe d'installation vers un emplacement réseau.
  
Une autre option consiste à télécharger l'application de base de Skype Entreprise pour vos utilisateurs. Vous pouvez télécharger [Microsoft Skype pour Business Basic (32 ou 64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=49440).
  
Pour les deux apps complète et base Skype Entreprise, après avoir téléchargé les fichiers d'installation, vous devrez envoyer manuellement (par exemple, dans un courrier électronique) le chemin d'accès réseau aux utilisateurs pour leur peuvent d'exécuter le programme d'installation pour installer l'application sur leur ordinateur.
  
Vous pouvez également utiliser ces téléchargements pour déployer l'application Skype Entreprise sur les ordinateurs de vos utilisateurs à l'aide de vos outils et processus de déploiement de logiciels existants.
  
## Pour les grandes organisations et les grandes entreprises

> [!NOTE]
>  Cette rubrique s'applique uniquement à l'application Skype Entreprise disponible dans le cadre des plans Office 365. Si votre entreprise utilise une version sous licence en volume de l'application Skype Entreprise basée sur Windows Installer (MSI), reportez-vous à la rubrique[Personnalisation de l'installation du client dans Skype Entreprise Server 2015](https://technet.microsoft.com/fr-fr/library/jj204934.aspx). 
  
Dans nombreuses entreprises ou entreprises de grande taille, les utilisateurs ne sont pas autorisés à installer le logiciel sur leur ordinateur. À la place, les services informatiques déploiement les logiciels nécessaires sur les ordinateurs des utilisateurs. Les services informatiques peuvent également contrôler la quantité de la bande passante Internet ou réseau utilisée dans leur organisation, afin qu'ils souhaitent installer un logiciel d'un emplacement à proximité sur leur réseau plutôt que de via Internet ou sur le réseau d'entreprise.
  
Avec Office 365, vous disposez de plusieurs options pour le déploiement de l'application Skype Entreprise si vous souhaitez contrôler où il est installé dans. Certaines de ces options sont les suivantes :
  
- Téléchargez l'application Skype Entreprise à votre réseau local à partir de la Centre d'administration Office 365, comme indiqué dans [déploiement manuellement Skype entreprise pour vos utilisateurs](8c563b81-22c9-4024-9efe-9fe28c7bbc96.md#bkmk_manual).
    
- Utilisez l' **[Outil déploiement d'Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** pour télécharger Office 365 ProPlus ou l'application Skype Entreprise à votre réseau local. Ensuite, utilisez l'outil déploiement d'Office pour déployer l'application à vos utilisateurs. L'outil déploiement d'Office vous donne la possibilité de contrôler certains aspects du déploiement, telles que les langues et version (32 bits ou 64 bits).
    
- Utiliser vos processus, tels que le Gestionnaire de Configuration système Centre et outils de déploiement de logiciel existants pour déployer Office 365 ProPlus ou l'application Skype Entreprise à vos utilisateurs. Vous pouvez utiliser vos processus et outils existants avec l' [Outil déploiement d'Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) ou avec le logiciel que vous avez téléchargé à partir de la Centre d'administration Office 365.
    
### En savoir plus sur l'utilisation de l'outil Déploiement d'Office

Pour en savoir plus sur le téléchargement de l'outil Déploiement d'Office et sur l'installation de l'application Skype Entreprise et d'autres applications client Office 365, reportez-vous à la rubrique [Gestion des logiciels des utilisateurs dans Office 365](https://support.office.com/article/365-c13051e6-f75c-4737-bc0d-7685dcedf360.aspx).
  
Voici une vue d'ensemble des étapes impliqués dans à l'aide de l'outil déploiement d'Office pour déployer une application :
  
1. **[Téléchargez l'outil déploiement d'Office la plus récente](https://go.microsoft.com/fwlink/p/?LinkID=626065)** à partir du Microsoft Download Center.
    
2. Créez le fichier de configuration .xml à utiliser avec l'outil Déploiement d'Office qui contient les paramètres d'application client de votre choix, comme la définition de la version (32 bits ou 64 bits), la langue d'installation, etc.
    
3. Utilisez l'outil déploiement d'Office et le fichier configuration.xml pour télécharger les fichiers d'installation sur votre réseau interne ou dans le réseau de remise contenu Office (CDN).
    
4. Utiliser l'outil déploiement d'Office et la configuration.xml pour installer les applications clientes Office, y compris l'application Skype Entreprise.
    
Pour en savoir plus sur l'outil Déploiement d'Office et le fichier de configuration .xml, reportez-vous aux articles suivants :
  
- [Présentation de l'outil Déploiement d'Office](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Paramètres de configuration .xml](https://technet.microsoft.com/library/jj219426.aspx)
    
### Plus d'informations sur l'utilisation de System Center Configuration Manager

Vous pouvez utiliser vos processus, tels que le Gestionnaire de Configuration système Centre et outils de déploiement de logiciel existants pour déployer l'application Skype Entreprise. Vous pouvez utiliser ces outils et les processus avec le logiciel que vous téléchargez à partir de la Centre d'administration Office 365 ou avec l'outil déploiement d'Office.
  
Pour plus d'informations sur l'utilisation du Gestionnaire de Configuration pour déployer des logiciels, consultez les articles suivants :
  
- [Comment créer des applications dans le Gestionnaire de configuration](https://technet.microsoft.com/fr-fr/library/gg682159.aspx)
    
- [Comment déployer des applications dans le Gestionnaire de configuration](https://technet.microsoft.com/fr-fr/library/gg682082.aspx)
    
Si vous déployez l'application Skype Entreprise dans le cadre du déploiement d'Office 365 ProPlus, voir [Déployer Office 365 ProPlus à l'aide de System Center Configuration Manager](https://technet.microsoft.com/en-us/library/dn708063.aspx).
  
## Planification des mises à jour de l'application Skype Entreprise

Dans le cadre du déploiement de l'application Skype Entreprise, vous devez prendre en considération la manière dont vous souhaitez obtenir des mises à jour après l'installation de Skype entreprise. Ces mises à jour peuvent inclure les nouvelles fonctionnalités, mises à jour de sécurité ou mises à jour non relative à la sécurité, tels que les mises à jour améliorent les performances ou la stabilité. Deux éléments que vous devez prendre en considération sont :
  
- L'endroit où vous souhaitez obtenir des mises à jour de
    
- La fréquence à laquelle vous souhaitez obtenir des mises à jour de la fonctionnalité
    
Bien que vous pouvez contrôler l'endroit où vous obtenez mises à jour à partir d'et à quelle fréquence mises à jour de la fonctionnalité, vous ne pouvez pas choisir les mises à jour de sécurité spécifiques ou les mises à jour de sécurité non pouvez-vous.
  
 **Source d'obtention des mises à jour**
  
Par défaut, une fois l'application Skype Entreprise est installée, mises à jour sont automatiquement téléchargés à partir d'Internet lorsqu'ils sont disponibles auprès de Microsoft. Si vous souhaitez davantage de contrôle sur lorsque des mises à jour se produisent ou lorsque les mises à jour sont installés à partir de, vous pouvez utiliser l'outil déploiement d'Office ou de la stratégie de groupe pour configurer qui.
  
Par exemple, de nombreuses organisations souhaitent tester les mises à jour avec un groupe d'utilisateurs avant de les déployer dans toute l'organisation. Vous pouvez le faire à l'aide de l'outil déploiement d'Office ou de la stratégie de groupe pour configurer l'application Skype Entreprise pour obtenir les mises à jour à partir d'un emplacement spécifique sur votre réseau, au lieu d'automatiquement sur Internet. Ensuite, vous pouvez utiliser l'outil déploiement d'Office pour télécharger les mises à jour chaque mois sur votre réseau local.
  
Pour plus d'informations sur le fonctionnement des mises à jour pour les logiciels Office 365, voir les articles suivants :
  
- [Présentation de la procédure de mise à jour d'Office 365 ProPlus](https://technet.microsoft.com/library/dn761709.aspx)
    
- [Choisir comment gérer les mises à jour pour Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [Configuration des paramètres de mise à jour pour Office 365 ProPlus](https://technet.microsoft.com/fr-fr/library/dn761708.aspx)
    
 **Définition de la fréquence de mise à jour des fonctionnalités**
  
Outre l'endroit où vous obtenez des mises à jour à partir de, vous pouvez également contrôler la fréquence à laquelle vous obtenez des nouvelles fonctionnalités pour le Skype entreprise. Les deux choix sont les suivantes :
  
- Obtenir des mises à jour de la fonctionnalité chaque mois, si les nouvelles fonctionnalités
    
- Obtenir des mises à jour de fonctionnalités tous les six mois
    
Pour certaines organisations, ils souhaitent tester les nouvelles fonctionnalités, afin qu'ils souhaitent obtenir des mises à jour de la fonctionnalité uniquement deux fois par an au lieu de chaque mois.
  
Vous pouvez contrôler la fréquence à laquelle vous obtenez des mises à jour de la fonctionnalité à l'aide de l'outil déploiement d'Office ou de la stratégie de groupe pour configurer le canal de mise à jour. Le donne canal mensuelle vous fonctionnalité mises à jour tous les mois (environ), tandis que le canal contrat semestriel offre des fonctionnalités mises à jour tous les six mois. Pour plus d'informations sur les canaux, voir [vue d'ensemble des canaux de mise à jour pour Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).
  
## Rubriques connexes

[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)
  
[Skype pour les entreprises et Microsoft Teams module complémentaire licences](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

