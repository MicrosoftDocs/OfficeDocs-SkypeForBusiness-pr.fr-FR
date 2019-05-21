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
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="d8a30-103">Configuration du serveur d’administration principal</span><span class="sxs-lookup"><span data-stu-id="d8a30-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="d8a30-104">**Résumé:** Configurer votre serveur de gestion principal, installer System Center Operations Manager et importer des modules de gestion pour Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d8a30-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2015.</span></span>

<span data-ttu-id="d8a30-105">Pour tirer pleinement parti des nouvelles fonctionnalités de surveillance de l’intégrité intégrées à Skype entreprise Server 2015, vous devez d’abord désigner un ordinateur pour agir en tant que serveur d’administration principal.</span><span class="sxs-lookup"><span data-stu-id="d8a30-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2015, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="d8a30-106">Vous devez ensuite installer System Center Operations Manager 2012 SP1 ou R2 ou System Center Operations Manager 2007 R2 sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="d8a30-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="d8a30-107">Par ailleurs, vous devez commencer par installer une version prise en charge de SQL Server pour pouvoir fonctionner en tant que base de données principale Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d8a30-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="d8a30-108">Lorsque vous installez System Center Operations Manager, vous devez installer tous les composants de ce produit, y compris:</span><span class="sxs-lookup"><span data-stu-id="d8a30-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="d8a30-109">Base de données opérationnelle</span><span class="sxs-lookup"><span data-stu-id="d8a30-109">Operational database</span></span>

- <span data-ttu-id="d8a30-110">Serveur</span><span class="sxs-lookup"><span data-stu-id="d8a30-110">Server</span></span>

- <span data-ttu-id="d8a30-111">Console</span><span class="sxs-lookup"><span data-stu-id="d8a30-111">Console</span></span>

- <span data-ttu-id="d8a30-112">Cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8a30-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="d8a30-113">Console web</span><span class="sxs-lookup"><span data-stu-id="d8a30-113">Web console</span></span>

- <span data-ttu-id="d8a30-114">Créateur de rapports</span><span class="sxs-lookup"><span data-stu-id="d8a30-114">Reporting</span></span>

- <span data-ttu-id="d8a30-115">Entrepôt de données</span><span class="sxs-lookup"><span data-stu-id="d8a30-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8a30-116">Le «[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=6442)» doit être installé avant que vous installiez System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="d8a30-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="d8a30-117">Pour plus d’informations sur ces produits et leur installation, voir les liens suivants :</span><span class="sxs-lookup"><span data-stu-id="d8a30-117">For details about these products and their installation, see the following links:</span></span>

- [<span data-ttu-id="d8a30-118">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="d8a30-118">System Center Operations Manager 2012</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [<span data-ttu-id="d8a30-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="d8a30-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/en-us/library/bb735860.aspx)

<span data-ttu-id="d8a30-120">Gardez à l’esprit que vous ne pouvez avoir qu’un seul serveur de gestion racine par déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d8a30-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a><span data-ttu-id="d8a30-121">Importation de packs d’administration Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="d8a30-121">Importing the Skype for Business Server 2015 Management Packs</span></span>

<span data-ttu-id="d8a30-122">Vous pouvez développer les fonctionnalités de System Center Operations Manager en installant des packs d’administration (logiciels qui déterminent les éléments que System Center Operations Manager peut surveiller, la façon dont ces éléments doivent être surveillés et la façon dont les alertes doivent être déclenchées et relat.</span><span class="sxs-lookup"><span data-stu-id="d8a30-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="d8a30-123">Skype entreprise Server 2015 inclut deux packs d’administration System Center Operations Manager qui fournissent les fonctionnalités suivantes:</span><span class="sxs-lookup"><span data-stu-id="d8a30-123">Skype for Business Server 2015 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="d8a30-124">**Composant et Pack de gestion des utilisateurs** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) effectue le suivi des problèmes liés à Skype entreprise Server enregistrés dans les journaux d’événements, inscrits par des compteurs de performance ou enregistrés dans les bases de données d’enregistrements des détails des appels ou de la qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="d8a30-124">**The Component and User Management Pack** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="d8a30-125">Pour les problèmes critiques, System Center Operations Manager peut être configuré pour notifier immédiatement les administrateurs par courrier électronique, message instantané ou messagerie SMS.</span><span class="sxs-lookup"><span data-stu-id="d8a30-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="d8a30-126">(SMS ou service de messagerie courte est la technologie utilisée pour envoyer des messages texte d’un appareil mobile à un autre.)</span><span class="sxs-lookup"><span data-stu-id="d8a30-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="d8a30-127">Pour plus d’informations sur la configuration de la notification Operations Manager, consultez la rubrique Configuration de la [notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="d8a30-127">For details about configuring Operations Manager notification, see [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span></span>

- <span data-ttu-id="d8a30-128">**Pack d’administration de la surveillance active** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) teste de manière proactive les composants clés de Skype entreprise Server comme la connexion au système, l’échange de messages instantanés ou l’appel d’appels vers un téléphone situé sur le réseau téléphonique public commuté (RTC). ).</span><span class="sxs-lookup"><span data-stu-id="d8a30-128">**The Active Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="d8a30-129">Ces tests sont effectués à l’aide des cmdlets de transaction synthétique de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d8a30-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="d8a30-130">Par exemple, l’applet de **contrôle test-CsIM** est utilisée pour simuler une conversation par messagerie instantanée entre deux utilisateurs de test.</span><span class="sxs-lookup"><span data-stu-id="d8a30-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="d8a30-131">En cas d’échec de cette conversation, une alerte est générée.</span><span class="sxs-lookup"><span data-stu-id="d8a30-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="d8a30-p105">L’importation des packs d’administration est une étape cruciale. S’ils ne sont pas importés, vous ne serez pas en mesure d’utiliser Operations Manager pour surveiller les événements Skype Entreprise Server ni exécuter les transactions synthétiques Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d8a30-p105">Importing the management packs is a crucial step. If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="d8a30-p106">Le pack d’administration Composant et utilisateur permet de surveiller uniquement Skype Entreprise Server 2015. Si vous utilisez un scénario de coexistence dans lequel à la fois Skype Entreprise Server 2015 et Lync Server 2013 sont installés, vous devez continuer à utiliser les packs d’administration de Lync Server 2013 pour vos ordinateurs Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8a30-p106">The Component and User Management Pack is used to monitor only Skype for Business Server 2015. If you are in a coexistence scenario where both Skype for Business Server 2015 and Lync Server 2013 are installed, you should continue to use the Lync Server 2013 management packs for your Lync Server 2013 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="d8a30-136">Les packs d’administration pour Skype Entreprise Server 2015 incluent le pack d’administration Composant et utilisateur Skype Entreprise Server 2015 et le pack d’administration Surveillance active Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d8a30-136">Management packs for Skype for Business Server 2015 include the Skype for Business Server 2015 Component and User Management Pack and the Skype for Business Server 2015 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="d8a30-137">Vous pouvez utiliser l’un des outils suivants pour importer les packs d’administration :</span><span class="sxs-lookup"><span data-stu-id="d8a30-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="d8a30-138">**System Center Operations Manager** Avec cette méthode, vous utilisez le gestionnaire des opérations pour ajouter une surveillance pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d8a30-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="d8a30-139">**Operations Manager Shell** Vous pouvez utiliser le shell Operations Manager pour importer directement, ou pour résoudre les éventuels problèmes rencontrés lors de l’importation de modules de gestion à l’aide de la console System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d8a30-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="d8a30-140">Importation des packs d’administration avec System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="d8a30-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="d8a30-141">Téléchargez SkypeForBusiness2015ManagementPacks.msi à partir du site web de téléchargement Microsoft, puis installez le fichier msi.</span><span class="sxs-lookup"><span data-stu-id="d8a30-141">Download the SkypeForBusiness2015ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="d8a30-142">Dans System Center Operations Manager, cliquez sur **administration**.</span><span class="sxs-lookup"><span data-stu-id="d8a30-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="d8a30-143">Dans le volet administration, cliquez avec le bouton droit sur **modules de gestion**, puis cliquez sur Importer des **modules de gestion**.</span><span class="sxs-lookup"><span data-stu-id="d8a30-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="d8a30-144">Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Ajouter**, puis sur **Ajouter à partir du disque**.</span><span class="sxs-lookup"><span data-stu-id="d8a30-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="d8a30-145">Dans la boîte de dialogue **Connexion au catalogue en ligne**, cliquez sur **Aucune**.</span><span class="sxs-lookup"><span data-stu-id="d8a30-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="d8a30-p107">Dans la boîte de dialogue **Sélectionner les packs d’administration à importer**, recherchez et sélectionnez les fichiers Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, puis cliquez sur **Ouvrir**. Pour sélectionner plusieurs fichiers dans la boîte de dialogue, cliquez sur le premier fichier, maintenez la touche Ctrl enfoncée et cliquez sur les autres fichiers.</span><span class="sxs-lookup"><span data-stu-id="d8a30-p107">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, and then click **Open**. To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="d8a30-p108">Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Installer**. Si vous obtenez un message d’erreur et que l’installation échoue, cela signifie que les fichiers des packs d’administration se trouvent dans un dossier protégé par le contrôle du compte d’utilisateur Windows. Si cela se produit, copiez les fichiers dans un autre dossier et redémarrez le processus d’importation et d’installation.</span><span class="sxs-lookup"><span data-stu-id="d8a30-p108">In the **Select Management Packs** dialog box, click **Install**. If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control. If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="d8a30-p109">Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Fermer**. Le processus d’importation et d’installation peut prendre plusieurs minutes.</span><span class="sxs-lookup"><span data-stu-id="d8a30-p109">In the **Select Management Packs** dialog box, click **Close**. The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="d8a30-153">Importation des packs d’administration avec l’interpréteur de commandes d’Operations Manager</span><span class="sxs-lookup"><span data-stu-id="d8a30-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="d8a30-p110">En général, il est plus facile d’importer les packs d’administration avec la console Operations Manager. Cependant, si une erreur se produit et que l’importation échoue, la console ne fournit pas forcément des rapports d’erreurs clairs. En revanche, l’interpréteur de commandes d’Operations Manager fournit des informations détaillées. Si vous utilisez Operations Manager et que vous rencontrez des problèmes lors de l’importation d’un pack d’administration, importez le pack avec l’interpréteur de commandes d’Operations Manager. Ce dernier fournit davantage d’informations susceptibles de vous aider à identifier les problèmes d’importation.</span><span class="sxs-lookup"><span data-stu-id="d8a30-p110">In general, it is easier to import the management packs by using the Operations Manager console. However, if an error occurs and the import fails, the console does not always provide adequate error reports. By comparison, the Operations Manager Shell provides detailed information. If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell. The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="d8a30-159">Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft System Center 2012**, sur **Operations Manager**, puis sur **Interpréteur de commandes d’Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="d8a30-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="d8a30-160">Dans l’interpréteur de commandes, tapez la commande suivante à l’invite de commandes, en utilisant le chemin d’accès réel à votre copie du fichier Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="d8a30-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="d8a30-161">Une fois le premier pack d’administration importé, répétez la procédure à l’aide du chemin vers votre copie du fichier Microsoft.LS.2015.Monitoring.ComponentAndUser.mp :</span><span class="sxs-lookup"><span data-stu-id="d8a30-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:</span></span>

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
