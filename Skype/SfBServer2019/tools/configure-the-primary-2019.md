---
title: Configurer le serveur d’administration principal
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé : configurez votre serveur d’administration principal, installez System Center Operations Manager et importez des packs d’administration pour Skype entreprise Server 2019.'
ms.openlocfilehash: 2ad04419ec60e7c752d22c4cdc5c4e82fdb853f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150551"
---
# <a name="configure-the-primary-management-server"></a>Configurer le serveur d’administration principal

**Résumé :** Configurez votre serveur d’administration principal, installez System Center Operations Manager et importez des packs d’administration pour Skype entreprise Server 2019.

Pour tirer pleinement parti des nouvelles fonctionnalités d’analyse d’intégrité incluses dans Skype entreprise Server 2019, vous devez d’abord désigner un ordinateur qui fera office de serveur d’administration principal. Vous devez ensuite installer System Center Operations Manager 2012 SP1 ou R2 ou System Center Operations Manager 2007 R2 sur cet ordinateur. En outre, vous devez d’abord installer une version prise en charge de SQL Server pour qu’elle fonctionne en tant que base de données principale Operations Manager.

Lors de l’installation de System Center Operations Manager, vous devrez installer tous les composants de ce produit, notamment :

- Base de données opérationnelle

- Serveur

- Console

- Applets de commande Windows PowerShell

- Console web

- Reporting

- Data Warehouse

> [!IMPORTANT]
> Le «[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)» doit être installé avant l’installation de System Center Operations Manager 2012.

Pour plus d’informations sur ces produits et leur installation, reportez-vous aux liens suivants :

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

N’oubliez pas que vous ne pouvez avoir qu’un seul serveur d’administration principal par déploiement de Skype entreprise Server.

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>Importation des packs d’administration de Skype entreprise Server 2019

Vous pouvez étendre les fonctionnalités de System Center Operations Manager en installant les packs d’administration (logiciels qui déterminent les éléments que System Center Operations Manager peut surveiller, la façon dont ces éléments doivent être surveillés et comment les alertes doivent être déclenchées et pourboire. Skype entreprise Server 2019 comprend deux packs d’administration System Center Operations Manager qui offrent les fonctionnalités suivantes :

- **Le pack d’administration des composants et des utilisateurs** (Microsoft.ls.2019.Monitoring.ComponentAndUser.MP) effectue le suivi des problèmes de Skype entreprise Server enregistrés dans les journaux des événements, enregistrés par des compteurs de performance ou enregistrés dans les bases de données des enregistrements des détails des appels ou de la qualité de l’expérience (QoE). Pour les problèmes critiques, System Center Operations Manager peut être configuré pour informer immédiatement les administrateurs via le courrier électronique, le message instantané ou la messagerie SMS. (SMS, ou Short message service, est la technologie utilisée pour envoyer des messages texte d’un appareil mobile à un autre.)

    > [!NOTE]
    >  Pour plus d’informations sur la configuration de la notification Operations Manager, voir Configuration de la [notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).

- **Le pack d’administration active Monitoring Management** (Microsoft.ls.2019.Monitoring.ActiveMonitoring.MP) teste de façon proactive les composants clés de Skype entreprise Server, tels que la connexion au système, l’échange de messages instantanés ou l’appel à un téléphone situé sur le réseau téléphonique commuté (PSTN). Ces tests sont effectués à l’aide des applets de commande de transaction synthétique Skype entreprise Server. Par exemple, l’applet de commande **Test-CsIM** est utilisée pour simuler une conversation de messagerie instantanée entre deux utilisateurs de test. Si cette conversation simulée échoue, une alerte est générée.

L’importation des packs d’administration est une étape essentielle. Si les packs d’administration ne sont pas importés, vous ne pourrez pas utiliser Operations Manager pour surveiller les événements Skype entreprise Server ou exécuter des transactions synthétiques de Skype entreprise Server.

Le pack d’administration des composants et des utilisateurs est utilisé pour surveiller uniquement Skype entreprise Server 2019. Si vous êtes dans un scénario de coexistence dans lequel Skype entreprise Server 2019 et Skype entreprise Server 2015 sont installés, vous devez continuer à utiliser les packs d’administration de Skype entreprise Server 2015 pour vos ordinateurs de Skype entreprise Server 2015.

> [!NOTE]
> Les packs d’administration de Skype entreprise Server 2019 incluent le pack d’administration des utilisateurs et des composants Skype entreprise Server 2019, ainsi que le pack d’administration active monitoring pour Skype entreprise Server 2019.

Vous pouvez utiliser l’un des outils suivants pour importer les packs d’administration :

- **System Center Operations Manager** Avec cette méthode, vous utilisez Operations Manager pour ajouter la surveillance pour Skype entreprise Server.

- **Environnement de gestion des opérations** Vous pouvez utiliser l’environnement de commande Operations Manager pour importer directement ou pour résoudre les problèmes que vous rencontrez lorsque vous importez des packs d’administration à l’aide de la console System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importation des packs d’administration à l’aide de System Center Operations Manager

1. Téléchargez le fichier SkypeForBusiness2019ManagementPacks. msi à partir des téléchargements Web Microsoft et installez le MSI.

2. Dans System Center Operations Manager, cliquez sur **administration**.

3. Dans le volet Administration, cliquez avec le bouton droit sur **Packs d’administration**, puis cliquez sur **Importer les packs d’administration**.

4. Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Ajouter**, puis sur **Ajouter à partir du disque**.

5. Dans la boîte de dialogue **connexion au catalogue en ligne** , cliquez sur **non**.

6. Dans la boîte de dialogue **Sélectionner les packs d’administration à importer** , recherchez et sélectionnez les fichiers Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp et Microsoft.ls.2019.Monitoring.ComponentAndUser.MP, puis cliquez sur **ouvrir**. Pour sélectionner plusieurs fichiers dans la boîte de dialogue, cliquez sur le premier fichier, puis maintenez la touche CTRL enfoncée et cliquez sur les fichiers suivants.

7. Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Installer**. Si vous obtenez un message d’erreur et que l’installation échoue, cela signifie que les fichiers des packs d’administration se trouvent dans un dossier protégé par le contrôle du compte d’utilisateur Windows. Si cela se produit, copiez les fichiers dans un autre dossier, puis redémarrez le processus d’importation et d’installation.

8. Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Fermer**. Le processus d’importation et d’installation peut nécessiter plusieurs minutes.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importation des packs d’administration à l’aide de l’environnement de commande Operations Manager

En règle générale, il est plus facile d’importer les packs d’administration à l’aide de la console Operations Manager. Toutefois, si une erreur se produit et que l’importation échoue, la console ne fournit pas toujours des rapports d’erreur appropriés. Par comparaison, l’environnement de commande Operations Manager fournit des informations détaillées. Si vous utilisez Operations Manager et que vous rencontrez des problèmes lors de l’importation d’un pack d’administration, importez le Pack à l’aide de l’environnement de commande Operations Manager. Les informations fournies par Operations Manager Shell peuvent vous aider à déterminer la cause de l’échec de l’importation.

1. Cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft System Center 2012**, sur **Operations Manager**, puis sur **environnement gestionnaire des opérations**.

2. Dans l’environnement de ligne de commande Operations Manager, tapez la commande suivante à l’invite de commandes, en utilisant le chemin d’accès réel à votre copie du fichier Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp, puis appuyez sur entrée :

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. Une fois le premier pack d’administration importé, répétez le processus, en utilisant le chemin d’accès à votre copie du fichier Microsoft.LS.2019.Monitoring.ComponentAndUser.mp :

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
