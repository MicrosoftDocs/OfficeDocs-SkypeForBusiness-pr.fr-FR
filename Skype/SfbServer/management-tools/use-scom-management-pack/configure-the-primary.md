---
title: Configuration du serveur d’administration principal
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 'Résumé : Configuration de votre serveur d’administration principal, installer System Center Operations Manager et importer des packs d’administration pour Skype pour Business Server 2015.'
ms.openlocfilehash: 6554ddc3fbe99ba70663b72794eb59dfc5d0d3e3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-primary-management-server"></a>Configuration du serveur d’administration principal
 
**Résumé :** Configurer votre serveur d’administration principal, installer System Center Operations Manager et importer des packs d’administration pour Skype pour Business Server 2015.
  
Pour tirer pleinement parti de la santé de nouveau incluses dans Skype pour Business Server 2015 des capacités d’analyse, vous devez d’abord désigner un ordinateur pour agir en tant que votre serveur d’administration principal. Vous devez ensuite installer System Center Operations Manager 2012 SP1 ou R2 ou System Center Operations Manager 2007 R2 sur l’ordinateur. En outre, vous devez d’abord installer une version prise en charge de SQL Server en tant que votre base de données back-end de Operations Manager.
  
Lors de l’installation de System Center Operations Manager, vous devez installer tous les composants du produit, y compris :
  
- Base de données opérationnelle
    
- Serveur
    
- Console
    
- Les applets de commande Windows PowerShell
    
- Console web
    
- Créateur de rapports
    
- Entrepôt de données
    
> [!IMPORTANT]
> Le «[Package redistribuable de Microsoft rapport Viewer 2010](https://www.microsoft.com/en-us/download/details.aspx?id=6442)» doit être installé avant d’installer System Center Operations Manager 2012. 
  
Pour plus d’informations sur ces produits et leur installation, voir les liens suivants :
  
- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)
    
- [System Center Operations Manager 2007](https://technet.microsoft.com/en-us/library/bb735860.aspx)
    
Gardez à l’esprit que vous pouvez avoir qu’un seul serveur d’administration racine par Skype pour le déploiement du serveur de l’entreprise.
  
## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>Importation de packs d’administration Skype Entreprise Server 2015

Vous pouvez étendre les fonctionnalités de System Center Operations Manager par l’installation des packs de gestion : logiciel qui dicte les éléments de System Center Operations Manager peut surveiller, comment les éléments doivent être surveillés et comment doivent se déclencher les alertes et signalé. Skype pour Business Server 2015 comprend deux packs d’administration System Center Operations Manager qui fournissent les fonctionnalités suivantes :
  
- **Le composant et le Pack d’administration utilisateur** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) effectue le suivi de Skype pour les problèmes de serveur d’entreprise enregistrées dans les journaux des événements, enregistré par les compteurs de performance ou enregistré dans les enregistrements de détail des appels (CDR) ou les bases de données de qualité d’expérience (QoE). Pour les problèmes critiques, System Center Operations Manager peut être configuré pour avertir immédiatement les administrateurs par courrier électronique, messagerie instantanée ou messagerie SMS. (SMS, ou Short Message Service, est la technologie utilisée pour envoyer des messages texte à partir d’un appareil mobile à un autre.)
    
    > [!NOTE]
    >  Pour plus d’informations sur la configuration de la notification d’Operations Manager, reportez-vous à la section [Configuration de la Notification](http://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409). 
  
- **Le Pack d’administration analyse Active** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) proactive tests clé Skype pour les composants Business Server, telles que l’ouverture de session dans le système, échangez des messages instantanés ou des appels à un téléphone sur le réseau téléphonique public commuté (RTPC ). Ces essais sont effectués à l’aide de la Skype pour les applets de commande de transactions synthétiques Business Server. Par exemple, l’applet de commande **Test-CsIM** permet de simuler une conversation entre deux utilisateurs de test de la messagerie instantanée. En cas d’échec de cette conversation simulée, une alerte est générée.
    
L’importation des packs d’administration est une étape cruciale. S’ils ne sont pas importés, vous ne serez pas en mesure d’utiliser Operations Manager pour surveiller les événements Skype Entreprise Server ni exécuter les transactions synthétiques Skype Entreprise Server. 
  
Le pack d’administration Composant et utilisateur permet de surveiller uniquement Skype Entreprise Server 2015. Si vous utilisez un scénario de coexistence dans lequel à la fois Skype Entreprise Server 2015 et Lync Server 2013 sont installés, vous devez continuer à utiliser les packs d’administration de Lync Server 2013 pour vos ordinateurs Lync Server 2013.
  
> [!NOTE]
> Les packs d’administration pour Skype Entreprise Server 2015 incluent le pack d’administration Composant et utilisateur Skype Entreprise Server 2015 et le pack d’administration Surveillance active Skype Entreprise Server 2015. 
  
Vous pouvez utiliser l’un des outils suivants pour importer les packs d’administration :
  
- **System Center Operations Manager** Avec cette méthode, le Gestionnaire des opérations vous permet d’ajouter la surveillance pour Skype pour Business Server.
    
- **Interface d’Operations Manager** Vous pouvez utiliser l’interface de Operations Manager pour importer directement, ou pour résoudre les problèmes que vous rencontrez lors de l’importation des packs d’administration à l’aide de la console System Center Operations Manager.
    
### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importation des packs d’administration avec System Center Operations Manager

1. Téléchargez SkypeForBusiness2015ManagementPacks.msi à partir du site web de téléchargement Microsoft, puis installez le fichier msi.
    
2. Dans System Center Operations Manager, cliquez sur **Administration**.
    
3. Dans le volet d’Administration, cliquez sur **Packs d’administration**, puis cliquez sur **Importer des Packs d’administration**.
    
4. Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Ajouter**, puis sur **Ajouter à partir du disque**.
    
5. Dans la boîte de dialogue **Connexion au catalogue en ligne**, cliquez sur **Aucune**.
    
6. Dans la boîte de dialogue **Sélectionner les packs d’administration à importer**, recherchez et sélectionnez les fichiers Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, puis cliquez sur **Ouvrir**. Pour sélectionner plusieurs fichiers dans la boîte de dialogue, cliquez sur le premier fichier, maintenez la touche Ctrl enfoncée et cliquez sur les autres fichiers.
    
7. Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Installer**. Si vous obtenez un message d’erreur et que l’installation échoue, cela signifie que les fichiers des packs d’administration se trouvent dans un dossier protégé par le contrôle du compte d’utilisateur Windows. Si cela se produit, copiez les fichiers dans un autre dossier et redémarrez le processus d’importation et d’installation.
    
8. Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Fermer**. Le processus d’importation et d’installation peut prendre plusieurs minutes.
    
## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importation des packs d’administration avec l’interpréteur de commandes d’Operations Manager

En général, il est plus facile d’importer les packs d’administration avec la console Operations Manager. Cependant, si une erreur se produit et que l’importation échoue, la console ne fournit pas forcément des rapports d’erreurs clairs. En revanche, l’interpréteur de commandes d’Operations Manager fournit des informations détaillées. Si vous utilisez Operations Manager et que vous rencontrez des problèmes lors de l’importation d’un pack d’administration, importez le pack avec l’interpréteur de commandes d’Operations Manager. Ce dernier fournit davantage d’informations susceptibles de vous aider à identifier les problèmes d’importation.
  
1. Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft System Center 2012**, sur **Operations Manager**, puis sur **Interpréteur de commandes d’Operations Manager**.
    
2. Dans l’interpréteur de commandes, tapez la commande suivante à l’invite de commandes, en utilisant le chemin d’accès réel à votre copie du fichier Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, puis appuyez sur Entrée :
    
  ```
  Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
  ```

3. Une fois le premier pack d’administration importé, répétez la procédure à l’aide du chemin vers votre copie du fichier Microsoft.LS.2015.Monitoring.ComponentAndUser.mp :
    
  ```
  Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
  ```


