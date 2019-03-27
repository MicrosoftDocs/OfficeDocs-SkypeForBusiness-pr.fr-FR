---
title: Configuration du serveur d’administration principal
ms.reviewer: ''
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
description: 'Résumé : Configurer votre serveur d’administration principal, installer System Center Operations Manager et importer les packs d’administration pour Skype pour Business Server 2015.'
ms.openlocfilehash: 06dbf8161e2b241bb527c0ca02c9e8210055d409
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890078"
---
# <a name="configure-the-primary-management-server"></a>Configuration du serveur d’administration principal

**Résumé :** Configurer votre serveur d’administration principal, installer System Center Operations Manager et importer les packs d’administration pour Skype pour Business Server 2015.

Pour tirer pleinement parti des nouvelles fonctionnalités incluses dans Skype pour Business Server 2015 d’analyse d’intégrité, vous devez d’abord désigner un ordinateur en tant que votre serveur d’administration principal. Vous devez ensuite installer System Center Operations Manager 2012 SP1 ou R2 ou Microsoft System Center Operations Manager 2007 R2 sur cet ordinateur. En outre, vous devez d’abord installer une version prise en charge de SQL Server pour fonctionner en tant que votre base de données principale Operations Manager.

Lors de l’installation de System Center Operations Manager, vous devez installer tous les composants du produit, y compris :

- Base de données opérationnelle

- Serveur

- Console

- Applets de commande Windows PowerShell

- Console web

- Créateur de rapports

- Entrepôt de données

> [!IMPORTANT]
> Le «[Package redistribuable Microsoft Report Viewer 2010](https://www.microsoft.com/en-us/download/details.aspx?id=6442)» doit être installé avant d’installer System Center Operations Manager 2012.

Pour plus d’informations sur ces produits et leur installation, voir les liens suivants :

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/en-us/library/bb735860.aspx)

N’oubliez pas que vous pouvez avoir qu’un seul serveur d’administration racine par Skype pour le déploiement de serveur d’entreprise.

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>Importation de packs d’administration Skype Entreprise Server 2015

Vous pouvez étendre les fonctionnalités de System Center Operations Manager en installant les packs d’administration, logiciel qui détermine les éléments de System Center Operations Manager qui peut surveiller, comment ces éléments doivent être surveillées et comment les alertes doivent être déclenchées et indiqué. Skype pour Business Server 2015 comprend deux packs d’administration System Center Operations Manager qui fournissent les fonctionnalités suivantes :

- **Le composant et le Pack d’administration utilisateur** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) suit Skype pour les problèmes Business Server enregistré dans les journaux des événements, enregistré par les compteurs de performance ou enregistré dans les enregistrements des détails des appels (CDR) ou les bases de données de qualité de l’expérience (QoE). Pour les problèmes critiques, System Center Operations Manager peut être configuré pour avertir immédiatement les administrateurs par le biais de courrier électronique, messagerie instantanée ou messagerie SMS. (SMS ou Short Message Service, est la technologie utilisée pour envoyer des messages texte à partir d’un appareil mobile à un autre).

    > [!NOTE]
    >  Pour plus d’informations sur la configuration de notification Operations Manager, voir [Configuration des notifications](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).

- **Le Pack d’administration surveillance Active** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) proactive tests clé Skype pour les composants Business Server, comme connectant au système, échanger des messages instantanés ou effectuer des appels à un téléphone situé sur le réseau téléphonique commuté (PSTN ). Ces tests sont effectuées à l’aide de la Skype pour les applets de commande de transaction synthétique Business Server. Par exemple, l’applet de commande **Test-CsIM** est utilisé pour simuler une conversation par messagerie instantanée entre deux utilisateurs test. Si cette conversation simulée échoue, une alerte est générée.

L’importation des packs d’administration est une étape cruciale. S’ils ne sont pas importés, vous ne serez pas en mesure d’utiliser Operations Manager pour surveiller les événements Skype Entreprise Server ni exécuter les transactions synthétiques Skype Entreprise Server.

Le pack d’administration Composant et utilisateur permet de surveiller uniquement Skype Entreprise Server 2015. Si vous utilisez un scénario de coexistence dans lequel à la fois Skype Entreprise Server 2015 et Lync Server 2013 sont installés, vous devez continuer à utiliser les packs d’administration de Lync Server 2013 pour vos ordinateurs Lync Server 2013.

> [!NOTE]
> Les packs d’administration pour Skype Entreprise Server 2015 incluent le pack d’administration Composant et utilisateur Skype Entreprise Server 2015 et le pack d’administration Surveillance active Skype Entreprise Server 2015.

Vous pouvez utiliser l’un des outils suivants pour importer les packs d’administration :

- **System Center Operations Manager** Avec cette méthode, vous utilisez le Gestionnaire des opérations pour surveiller Skype pour Business Server.

- **Interface d’Operations Manager** Vous pouvez utiliser l’interface d’Operations Manager pour importer directement ou pour résoudre les problèmes que vous rencontrez lorsque vous importez des packs d’administration à l’aide de la console System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importation des packs d’administration avec System Center Operations Manager

1. Téléchargez SkypeForBusiness2015ManagementPacks.msi à partir du site web de téléchargement Microsoft, puis installez le fichier msi.

2. Dans System Center Operations Manager, cliquez sur **Administration**.

3. Dans le volet Administration, cliquez sur **Packs d’administration**, puis cliquez sur **Importer les Packs d’administration**.

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
