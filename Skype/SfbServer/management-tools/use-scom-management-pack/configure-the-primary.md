---
title: Configuration du serveur d’administration principal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 'Résumé: configurez votre serveur de gestion principal, installez System Center Operations Manager et importez les modules de gestion pour Skype entreprise Server 2015.'
ms.openlocfilehash: a89ee8ca7c7f5601d9219ef49643adc2ebf99883
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277670"
---
# <a name="configure-the-primary-management-server"></a>Configuration du serveur d’administration principal

**Résumé:** Configurer votre serveur de gestion principal, installer System Center Operations Manager et importer des modules de gestion pour Skype entreprise Server 2015.

Pour tirer pleinement parti des nouvelles fonctionnalités de surveillance de l’intégrité intégrées à Skype entreprise Server 2015, vous devez d’abord désigner un ordinateur pour agir en tant que serveur d’administration principal. Vous devez ensuite installer System Center Operations Manager 2012 SP1 ou R2 ou System Center Operations Manager 2007 R2 sur cet ordinateur. Par ailleurs, vous devez commencer par installer une version prise en charge de SQL Server pour pouvoir fonctionner en tant que base de données principale Operations Manager.

Lorsque vous installez System Center Operations Manager, vous devez installer tous les composants de ce produit, y compris:

- Base de données opérationnelle

- Serveur

- Console

- Cmdlets Windows PowerShell

- Console web

- Créateur de rapports

- Entrepôt de données

> [!IMPORTANT]
> Le «[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=6442)» doit être installé avant que vous installiez System Center Operations Manager 2012.

Pour plus d’informations sur ces produits et leur installation, voir les liens suivants :

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/en-us/library/bb735860.aspx)

Gardez à l’esprit que vous ne pouvez avoir qu’un seul serveur de gestion racine par déploiement de Skype entreprise Server.

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>Importation de packs d’administration Skype Entreprise Server 2015

Vous pouvez développer les fonctionnalités de System Center Operations Manager en installant des packs d’administration (logiciels qui déterminent les éléments que System Center Operations Manager peut surveiller, la façon dont ces éléments doivent être surveillés et la façon dont les alertes doivent être déclenchées et relat. Skype entreprise Server 2015 inclut deux packs d’administration System Center Operations Manager qui fournissent les fonctionnalités suivantes:

- **Composant et Pack de gestion des utilisateurs** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) effectue le suivi des problèmes liés à Skype entreprise Server enregistrés dans les journaux d’événements, inscrits par des compteurs de performance ou enregistrés dans les bases de données d’enregistrements des détails des appels ou de la qualité des appels. Pour les problèmes critiques, System Center Operations Manager peut être configuré pour notifier immédiatement les administrateurs par courrier électronique, message instantané ou messagerie SMS. (SMS ou service de messagerie courte est la technologie utilisée pour envoyer des messages texte d’un appareil mobile à un autre.)

    > [!NOTE]
    >  Pour plus d’informations sur la configuration de la notification Operations Manager, consultez la rubrique Configuration de la [notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).

- **Pack d’administration de la surveillance active** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) teste de manière proactive les composants clés de Skype entreprise Server comme la connexion au système, l’échange de messages instantanés ou l’appel d’appels vers un téléphone situé sur le réseau téléphonique public commuté (RTC). ). Ces tests sont effectués à l’aide des cmdlets de transaction synthétique de Skype entreprise Server. Par exemple, l’applet de **contrôle test-CsIM** est utilisée pour simuler une conversation par messagerie instantanée entre deux utilisateurs de test. En cas d’échec de cette conversation, une alerte est générée.

L’importation des packs d’administration est une étape cruciale. S’ils ne sont pas importés, vous ne serez pas en mesure d’utiliser Operations Manager pour surveiller les événements Skype Entreprise Server ni exécuter les transactions synthétiques Skype Entreprise Server.

Le pack d’administration Composant et utilisateur permet de surveiller uniquement Skype Entreprise Server 2015. Si vous utilisez un scénario de coexistence dans lequel à la fois Skype Entreprise Server 2015 et Lync Server 2013 sont installés, vous devez continuer à utiliser les packs d’administration de Lync Server 2013 pour vos ordinateurs Lync Server 2013.

> [!NOTE]
> Les packs d’administration pour Skype Entreprise Server 2015 incluent le pack d’administration Composant et utilisateur Skype Entreprise Server 2015 et le pack d’administration Surveillance active Skype Entreprise Server 2015.

Vous pouvez utiliser l’un des outils suivants pour importer les packs d’administration :

- **System Center Operations Manager** Avec cette méthode, vous utilisez le gestionnaire des opérations pour ajouter une surveillance pour Skype entreprise Server.

- **Operations Manager Shell** Vous pouvez utiliser le shell Operations Manager pour importer directement, ou pour résoudre les éventuels problèmes rencontrés lors de l’importation de modules de gestion à l’aide de la console System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importation des packs d’administration avec System Center Operations Manager

1. Téléchargez SkypeForBusiness2015ManagementPacks.msi à partir du site web de téléchargement Microsoft, puis installez le fichier msi.

2. Dans System Center Operations Manager, cliquez sur **administration**.

3. Dans le volet administration, cliquez avec le bouton droit sur **modules de gestion**, puis cliquez sur Importer des **modules de gestion**.

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
