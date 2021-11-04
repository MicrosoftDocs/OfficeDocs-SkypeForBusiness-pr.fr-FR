---
title: Comment configurer le serveur d’administration principal
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 'Résumé : Configurez votre serveur de gestion principal, installez System Center Operations Manager et importez des packs d’administration pour Skype Entreprise Server 2015.'
ms.openlocfilehash: 98a6cb9f18a5ff3fe008e7d07f5101884e5aa0f0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774594"
---
# <a name="how-to-configure-the-primary-management-server"></a>Comment configurer le serveur d’administration principal

**Résumé :** Configurez votre serveur de gestion principal, installez System Center Operations Manager et importez des packs d’administration pour Skype Entreprise Server 2015.

Pour tirer pleinement parti des nouvelles fonctionnalités d’analyse d’état incluses dans Skype Entreprise Server 2015, vous devez d’abord désigner un ordinateur qui jouera le rôle de serveur de gestion principal. Vous devez ensuite installer System Center Operations Manager 2012 SP1 ou R2 ou System Center Operations Manager 2007 R2 sur cet ordinateur. En outre, vous devez d’abord installer une version prise en charge de SQL Server pour qu’elle fonctionne comme votre base de données principale Operations Manager.

Lorsque vous installez System Center Operations Manager, vous devez installer tous les composants de ce produit, notamment :

- Base de données opérationnelle

- Serveur

- Console

- Applets de commande Windows PowerShell

- Console web

- Reporting

- Data Warehouse

> [!IMPORTANT]
> Le Microsoft Report Viewer Redistributable Package 2010 doit être installé avant d’installer System Center Operations Manager 2012.

Pour plus d’informations sur ces produits et leur installation, [voir System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))


N’oubliez pas que vous ne pouvez avoir qu’un seul serveur d’administration racine par Skype Entreprise Server déploiement.

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>Importation des packs d Skype Entreprise Server 2015

Vous pouvez étendre les fonctionnalités de System Center Operations Manager en installant des packs d’administration : logiciels qui déterminent les éléments que System Center Operations Manager peut surveiller, comment ces éléments doivent être surveillés et comment les alertes doivent être déclenchées et signalées. Skype Entreprise Server 2015 inclut deux packs d’System Center Operations Manager qui fournissent les fonctionnalités suivantes :

-  Le pack d’administration des composants et des utilisateurs (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) suit les problèmes de Skype Entreprise Server enregistrés dans les journaux des événements, enregistrés par des compteurs de performance ou enregistrés dans les enregistrements des détails des appels (CDR) ou les bases de données de qualité de l’expérience (QoE). Pour les problèmes critiques, System Center Operations Manager peut être configuré pour avertir immédiatement les administrateurs par courrier électronique, message instantané ou messagerie SMS. (SMS, ou Short Message Service, est la technologie utilisée pour envoyer des messages texte d’un appareil mobile à un autre.)

    > [!NOTE]
    >  Pour plus d’informations sur la configuration de la notification Operations Manager, voir [Configuring Notification](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10)).

- Le pack d’administration **Active Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) teste de manière proactive les composants de Skype Entreprise Server clés, tels que la signature du système, l’échange de messages instantanés ou l’appel à un téléphone situé sur le réseau téléphonique commuté (RSTN). Ces tests sont effectués à l’aide Skype Entreprise Server cmdlets de transaction synthétique. Par exemple, l’applet de commande **Test-CsIM** est utilisée pour simuler une conversation de messagerie instantanée entre deux utilisateurs de test. Si cette conversation simulée échoue, une alerte est générée.

L’importation des packs d’administration est une étape cruciale. Si les packs d’administration ne sont pas importés, vous ne pourrez pas utiliser Operations Manager pour surveiller Skype Entreprise Server événements ou exécuter Skype Entreprise Server transactions synthétiques.

Le pack d’administration Des composants et des utilisateurs est utilisé pour surveiller uniquement Skype Entreprise Server 2015. Si vous êtes dans un scénario de coexistence où Skype Entreprise Server 2015 et Lync Server 2013 sont installés, vous devez continuer à utiliser les packs d’administration Lync Server 2013 pour vos ordinateurs Lync Server 2013.

> [!NOTE]
> Les packs d’administration pour Skype Entreprise Server 2015 incluent le pack d’administration Skype Entreprise Server 2015 Component and User Management Pack et le pack d’administration Active Monitoring Skype Entreprise Server 2015.

Vous pouvez utiliser l’un des outils suivants pour importer les packs d’administration :

- **System Center Operations Manager** Avec cette méthode, vous utilisez Operations Manager pour ajouter la surveillance des Skype Entreprise Server.

- **interpréteur de commandes d'Operations Manager** Vous pouvez utiliser le interpréteur de commandes d'Operations Manager pour importer directement ou pour résoudre les problèmes que vous rencontrez lorsque vous importez des packs d’administration à l’aide de la console System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importation des packs d’administration à l’aide System Center Operations Manager

1. Téléchargez le SkypeForBusiness2015ManagementPacks.msi à partir des téléchargements Web De Microsoft et installez le msi.

2. Dans System Center Operations Manager, cliquez sur **Administration.**

3. Dans le volet Administration, cliquez avec le bouton droit sur **Packs d’administration**, puis cliquez sur **Importer les packs d’administration**.

4. Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Ajouter**, puis sur **Ajouter à partir du disque**.

5. Dans la boîte **de dialogue Connexion au** catalogue en ligne, cliquez sur **Non**.

6. Dans la boîte de dialogue Sélectionner les **packs** d’administration à importer, recherchez et sélectionnez les fichiers Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp et Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, puis cliquez sur **Ouvrir.** Pour sélectionner plusieurs fichiers dans la boîte de dialogue, cliquez sur le premier fichier, maintenez la touche Ctrl plus bas, puis cliquez sur les fichiers suivants.

7. Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Installer**. Si vous obtenez un message d’erreur et que l’installation échoue, cela signifie que les fichiers des packs d’administration se trouvent dans un dossier protégé par le contrôle du compte d’utilisateur Windows. Si cela se produit, copiez les fichiers dans un autre dossier, puis redémarrez le processus d’importation et d’installation.

8. Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Fermer**. Le processus d’importation et d’installation peut nécessiter plusieurs minutes.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importation des packs d’administration à l’aide du interpréteur de commandes d'Operations Manager

En règle générale, il est plus facile d’importer les packs d’administration à l’aide de la console Operations Manager. Toutefois, si une erreur se produit et que l’importation échoue, la console ne fournit pas toujours de rapports d’erreurs adéquats. En comparaison, le interpréteur de commandes d'Operations Manager fournit des informations détaillées. Si vous utilisez Operations Manager et que vous rencontrez des problèmes lors de l’importation d’un pack d’administration, importez-le à l’aide du interpréteur de commandes d'Operations Manager. Les informations fournies par interpréteur de commandes d'Operations Manager peuvent vous aider à déterminer la raison de l’échec de l’importation.

1. Cliquez **sur** Démarrer, **sur** Tous les programmes, sur Microsoft **System Center 2012,** sur **Operations Manager,** puis sur **interpréteur de commandes d'Operations Manager**.

2. Dans interpréteur de commandes d'Operations Manager, tapez la commande suivante à l’invite de commandes, en utilisant le chemin d’accès réel à votre copie du fichier Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, puis appuyez sur Entrée :

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. Une fois que vous avez importé le premier pack d’administration, répétez le processus en utilisant le chemin d’accès à votre copie du fichier Microsoft.LS.2015.Monitoring.ComponentAndUser.mp :

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```