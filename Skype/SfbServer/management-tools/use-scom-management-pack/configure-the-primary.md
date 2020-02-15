---
title: Configurer le serveur d’administration principal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 'Résumé : configurez votre serveur d’administration principal, installez System Center Operations Manager et importez des packs d’administration pour Skype entreprise Server 2015.'
ms.openlocfilehash: 08c1967965248d26844433030e4bf77501882cd8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005959"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="9b345-103">Configurer le serveur d’administration principal</span><span class="sxs-lookup"><span data-stu-id="9b345-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="9b345-104">**Résumé :** Configurez votre serveur d’administration principal, installez System Center Operations Manager et importez des packs d’administration pour Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9b345-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2015.</span></span>

<span data-ttu-id="9b345-105">Pour tirer pleinement parti des nouvelles fonctionnalités d’analyse d’intégrité incluses dans Skype entreprise Server 2015, vous devez d’abord désigner un ordinateur qui fera office de serveur d’administration principal.</span><span class="sxs-lookup"><span data-stu-id="9b345-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2015, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="9b345-106">Vous devez ensuite installer System Center Operations Manager 2012 SP1 ou R2 ou System Center Operations Manager 2007 R2 sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="9b345-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="9b345-107">En outre, vous devez d’abord installer une version prise en charge de SQL Server pour qu’elle fonctionne en tant que base de données principale Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="9b345-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="9b345-108">Lors de l’installation de System Center Operations Manager, vous devrez installer tous les composants de ce produit, notamment :</span><span class="sxs-lookup"><span data-stu-id="9b345-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="9b345-109">Base de données opérationnelle</span><span class="sxs-lookup"><span data-stu-id="9b345-109">Operational database</span></span>

- <span data-ttu-id="9b345-110">Serveur</span><span class="sxs-lookup"><span data-stu-id="9b345-110">Server</span></span>

- <span data-ttu-id="9b345-111">Console</span><span class="sxs-lookup"><span data-stu-id="9b345-111">Console</span></span>

- <span data-ttu-id="9b345-112">Applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b345-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="9b345-113">Console web</span><span class="sxs-lookup"><span data-stu-id="9b345-113">Web console</span></span>

- <span data-ttu-id="9b345-114">Reporting</span><span class="sxs-lookup"><span data-stu-id="9b345-114">Reporting</span></span>

- <span data-ttu-id="9b345-115">Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="9b345-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b345-116">Le «[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)» doit être installé avant l’installation de System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="9b345-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="9b345-117">Pour plus d’informations sur ces produits et leur installation, reportez-vous aux liens suivants :</span><span class="sxs-lookup"><span data-stu-id="9b345-117">For details about these products and their installation, see the following links:</span></span>

- [<span data-ttu-id="9b345-118">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="9b345-118">System Center Operations Manager 2012</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [<span data-ttu-id="9b345-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="9b345-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/library/bb735860.aspx)

<span data-ttu-id="9b345-120">N’oubliez pas que vous ne pouvez avoir qu’un seul serveur d’administration principal par déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9b345-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a><span data-ttu-id="9b345-121">Importation des packs d’administration de Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="9b345-121">Importing the Skype for Business Server 2015 Management Packs</span></span>

<span data-ttu-id="9b345-122">Vous pouvez étendre les fonctionnalités de System Center Operations Manager en installant les packs d’administration (logiciels qui déterminent les éléments que System Center Operations Manager peut surveiller, la façon dont ces éléments doivent être surveillés et comment les alertes doivent être déclenchées et pourboire.</span><span class="sxs-lookup"><span data-stu-id="9b345-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="9b345-123">Skype entreprise Server 2015 comprend deux packs d’administration System Center Operations Manager qui offrent les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="9b345-123">Skype for Business Server 2015 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="9b345-124">**Le pack d’administration des composants et des utilisateurs** (Microsoft.ls.2015.Monitoring.ComponentAndUser.MP) effectue le suivi des problèmes de Skype entreprise Server enregistrés dans les journaux des événements, enregistrés par des compteurs de performance ou enregistrés dans les bases de données des enregistrements des détails des appels ou de la qualité de l’expérience (QoE).</span><span class="sxs-lookup"><span data-stu-id="9b345-124">**The Component and User Management Pack** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="9b345-125">Pour les problèmes critiques, System Center Operations Manager peut être configuré pour informer immédiatement les administrateurs via le courrier électronique, le message instantané ou la messagerie SMS.</span><span class="sxs-lookup"><span data-stu-id="9b345-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="9b345-126">(SMS, ou Short message service, est la technologie utilisée pour envoyer des messages texte d’un appareil mobile à un autre.)</span><span class="sxs-lookup"><span data-stu-id="9b345-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="9b345-127">Pour plus d’informations sur la configuration de la notification Operations Manager, voir Configuration de la [notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="9b345-127">For details about configuring Operations Manager notification, see [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span></span>

- <span data-ttu-id="9b345-128">**Le pack d’administration active Monitoring Management** (Microsoft.ls.2015.Monitoring.ActiveMonitoring.MP) teste de façon proactive les composants clés de Skype entreprise Server, tels que la connexion au système, l’échange de messages instantanés ou l’appel à un téléphone situé sur le réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="9b345-128">**The Active Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="9b345-129">Ces tests sont effectués à l’aide des applets de commande de transaction synthétique Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9b345-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="9b345-130">Par exemple, l’applet de commande **Test-CsIM** est utilisée pour simuler une conversation de messagerie instantanée entre deux utilisateurs de test.</span><span class="sxs-lookup"><span data-stu-id="9b345-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="9b345-131">Si cette conversation simulée échoue, une alerte est générée.</span><span class="sxs-lookup"><span data-stu-id="9b345-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="9b345-132">L’importation des packs d’administration est une étape essentielle.</span><span class="sxs-lookup"><span data-stu-id="9b345-132">Importing the management packs is a crucial step.</span></span> <span data-ttu-id="9b345-133">Si les packs d’administration ne sont pas importés, vous ne pourrez pas utiliser Operations Manager pour surveiller les événements Skype entreprise Server ou exécuter des transactions synthétiques de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9b345-133">If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="9b345-134">Le pack d’administration des composants et des utilisateurs est utilisé pour surveiller uniquement Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9b345-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2015.</span></span> <span data-ttu-id="9b345-135">Si vous êtes dans un scénario de coexistence dans lequel Skype entreprise Server 2015 et Lync Server 2013 sont installés, vous devez continuer à utiliser les packs d’administration Lync Server 2013 pour vos ordinateurs Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b345-135">If you are in a coexistence scenario where both Skype for Business Server 2015 and Lync Server 2013 are installed, you should continue to use the Lync Server 2013 management packs for your Lync Server 2013 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="9b345-136">Les packs d’administration de Skype entreprise Server 2015 incluent le pack d’administration des utilisateurs et des composants Skype entreprise Server 2015, ainsi que le pack d’administration active monitoring pour Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9b345-136">Management packs for Skype for Business Server 2015 include the Skype for Business Server 2015 Component and User Management Pack and the Skype for Business Server 2015 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="9b345-137">Vous pouvez utiliser l’un des outils suivants pour importer les packs d’administration :</span><span class="sxs-lookup"><span data-stu-id="9b345-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="9b345-138">**System Center Operations Manager** Avec cette méthode, vous utilisez Operations Manager pour ajouter la surveillance pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9b345-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="9b345-139">**Environnement de gestion des opérations** Vous pouvez utiliser l’environnement de commande Operations Manager pour importer directement ou pour résoudre les problèmes que vous rencontrez lorsque vous importez des packs d’administration à l’aide de la console System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="9b345-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="9b345-140">Importation des packs d’administration à l’aide de System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="9b345-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="9b345-141">Téléchargez le fichier SkypeForBusiness2015ManagementPacks. msi à partir des téléchargements Web Microsoft et installez le MSI.</span><span class="sxs-lookup"><span data-stu-id="9b345-141">Download the SkypeForBusiness2015ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="9b345-142">Dans System Center Operations Manager, cliquez sur **administration**.</span><span class="sxs-lookup"><span data-stu-id="9b345-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="9b345-143">Dans le volet Administration, cliquez avec le bouton droit sur **Packs d’administration**, puis cliquez sur **Importer les packs d’administration**.</span><span class="sxs-lookup"><span data-stu-id="9b345-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="9b345-144">Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Ajouter**, puis sur **Ajouter à partir du disque**.</span><span class="sxs-lookup"><span data-stu-id="9b345-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="9b345-145">Dans la boîte de dialogue **connexion au catalogue en ligne** , cliquez sur **non**.</span><span class="sxs-lookup"><span data-stu-id="9b345-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="9b345-146">Dans la boîte de dialogue **Sélectionner les packs d’administration à importer** , recherchez et sélectionnez les fichiers Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp et Microsoft.ls.2015.Monitoring.ComponentAndUser.MP, puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="9b345-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="9b345-147">Pour sélectionner plusieurs fichiers dans la boîte de dialogue, cliquez sur le premier fichier, puis maintenez la touche CTRL enfoncée et cliquez sur les fichiers suivants.</span><span class="sxs-lookup"><span data-stu-id="9b345-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="9b345-148">Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="9b345-148">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="9b345-149">Si vous obtenez un message d’erreur et que l’installation échoue, cela signifie que les fichiers des packs d’administration se trouvent dans un dossier protégé par le contrôle du compte d’utilisateur Windows.</span><span class="sxs-lookup"><span data-stu-id="9b345-149">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="9b345-150">Si cela se produit, copiez les fichiers dans un autre dossier, puis redémarrez le processus d’importation et d’installation.</span><span class="sxs-lookup"><span data-stu-id="9b345-150">If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="9b345-151">Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="9b345-151">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="9b345-152">Le processus d’importation et d’installation peut nécessiter plusieurs minutes.</span><span class="sxs-lookup"><span data-stu-id="9b345-152">The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="9b345-153">Importation des packs d’administration à l’aide de l’environnement de commande Operations Manager</span><span class="sxs-lookup"><span data-stu-id="9b345-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="9b345-154">En règle générale, il est plus facile d’importer les packs d’administration à l’aide de la console Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="9b345-154">In general, it is easier to import the management packs by using the Operations Manager console.</span></span> <span data-ttu-id="9b345-155">Toutefois, si une erreur se produit et que l’importation échoue, la console ne fournit pas toujours des rapports d’erreur appropriés.</span><span class="sxs-lookup"><span data-stu-id="9b345-155">However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="9b345-156">Par comparaison, l’environnement de commande Operations Manager fournit des informations détaillées.</span><span class="sxs-lookup"><span data-stu-id="9b345-156">By comparison, the Operations Manager Shell provides detailed information.</span></span> <span data-ttu-id="9b345-157">Si vous utilisez Operations Manager et que vous rencontrez des problèmes lors de l’importation d’un pack d’administration, importez le Pack à l’aide de l’environnement de commande Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="9b345-157">If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell.</span></span> <span data-ttu-id="9b345-158">Les informations fournies par Operations Manager Shell peuvent vous aider à déterminer la cause de l’échec de l’importation.</span><span class="sxs-lookup"><span data-stu-id="9b345-158">The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="9b345-159">Cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft System Center 2012**, sur **Operations Manager**, puis sur **environnement gestionnaire des opérations**.</span><span class="sxs-lookup"><span data-stu-id="9b345-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="9b345-160">Dans l’environnement de ligne de commande Operations Manager, tapez la commande suivante à l’invite de commandes, en utilisant le chemin d’accès réel à votre copie du fichier Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="9b345-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="9b345-161">Une fois le premier pack d’administration importé, répétez le processus, en utilisant le chemin d’accès à votre copie du fichier Microsoft.LS.2015.Monitoring.ComponentAndUser.mp :</span><span class="sxs-lookup"><span data-stu-id="9b345-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
