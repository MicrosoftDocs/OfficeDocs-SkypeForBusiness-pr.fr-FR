---
title: 'Lync Server 2013 : importation des packs d’administration Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2c6dd42056fe665c0d4ec53d28103745ace2c84
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a><span data-ttu-id="d36a4-102">Importation des packs d’administration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d36a4-102">Importing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d36a4-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="d36a4-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d36a4-104">Vous pouvez étendre les fonctionnalités de System Center Operations Manager en installant les packs d’administration (logiciels qui déterminent les éléments que System Center Operations Manager peut surveiller, ainsi que la façon dont ces éléments doivent être surveillés et comment les alertes doivent être déclenchées et pourboire.</span><span class="sxs-lookup"><span data-stu-id="d36a4-104">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, and how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="d36a4-105">Lync Server 2013 comprend deux packs d’administration System Center Operations Manager qui offrent les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="d36a4-105">Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="d36a4-106">Le pack d’administration des composants et des utilisateurs (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) effectue le suivi des problèmes Lync Server enregistrés dans les journaux des événements, enregistrés par des compteurs de performance ou consignés dans les enregistrements des détails des appels ou sur la qualité de l’expérience (QoE). bases.</span><span class="sxs-lookup"><span data-stu-id="d36a4-106">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="d36a4-107">Pour les problèmes critiques, System Center Operations Manager peut être configuré pour informer immédiatement les administrateurs via la messagerie électronique, la messagerie instantanée ou la messagerie SMS (Short Message Service).</span><span class="sxs-lookup"><span data-stu-id="d36a4-107">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="d36a4-108">SMS est la technologie utilisée pour envoyer des messages texte entre appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="d36a4-108">SMS is the technology used to send text messages from one mobile device to another.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d36a4-109">Pour plus d’informations sur la configuration de la notification Operations Manager, voir la page relative à <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A>la configuration de la notification dans la bibliothèque TechNet à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="d36a4-109">For details about configuring Operations Manager notification, see the Configuring Notification in the TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="d36a4-110">Le pack d’administration active Monitoring (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) teste de façon proactive les principaux composants de Lync Server, tels que la connexion au système, l’échange de messages instantanés ou l’appel à un téléphone situé sur le switch public. réseau téléphonique (PSTN).</span><span class="sxs-lookup"><span data-stu-id="d36a4-110">The Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="d36a4-111">Ces tests sont effectués à l’aide des applets de commande de transaction synthétique Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d36a4-111">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="d36a4-112">Par exemple, vous pouvez utiliser l’applet de commande **Test-CsIM** pour simuler une conversation par message instantané entre deux utilisateurs test.</span><span class="sxs-lookup"><span data-stu-id="d36a4-112">For example, you can use the **Test-CsIM** cmdlet to simulate an instant messaging (IM) conversation between a pair of test users.</span></span> <span data-ttu-id="d36a4-113">Si cette conversation simulée échoue, une alerte est générée.</span><span class="sxs-lookup"><span data-stu-id="d36a4-113">If this simulated messaging conversation fails an alert is generated.</span></span>

<span data-ttu-id="d36a4-114">Vous devez importer les packs d’administration.</span><span class="sxs-lookup"><span data-stu-id="d36a4-114">You need to import the management packs.</span></span> <span data-ttu-id="d36a4-115">Si vous n’importez pas les packs d’administration, vous ne pouvez pas utiliser Operations Manager pour surveiller les événements Lync Server ou exécuter des transactions synthétiques Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d36a4-115">If you do not import the management packs, you cannot use Operations Manager to monitor Lync Server events or run Lync Server synthetic transactions.</span></span>

<span data-ttu-id="d36a4-116">Le pack d’administration des composants et des utilisateurs est utilisé uniquement pour analyser Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d36a4-116">The Component and User Management Pack is only used to monitor Lync Server 2013.</span></span> <span data-ttu-id="d36a4-117">Si vous êtes dans un scénario de coexistence dans lequel Lync Server 2013 et Lync Server 2010 sont installés, vous devez continuer à utiliser les packs d’administration Lync Server 2010 pour vos ordinateurs Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d36a4-117">If you are in a coexistence scenario, where you have both Lync Server 2013 and Lync Server 2010 installed, you should continue to use the Lync Server 2010 management packs for your Lync Server 2010 computers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d36a4-118">Les packs d’administration de Lync Server 2010 incluent le pack d’administration de surveillance Lync Server 2010 et le pack d’administration d’analyse de la conversation de groupe Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d36a4-118">Management packs for Lync Server 2010 include the Lync Server 2010 Monitoring Management Pack and the Lync Server 2010 Group Chat Monitoring Management Pack.</span></span>



</div>

<span data-ttu-id="d36a4-119">Vous pouvez utiliser l’un des outils suivants pour importer les packs d’administration :</span><span class="sxs-lookup"><span data-stu-id="d36a4-119">You can use one of the following tools to import management packs:</span></span>

  - <span data-ttu-id="d36a4-120">**System Center Operations Manager**   avec cette méthode, vous utilisez Operations Manager pour ajouter la surveillance de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d36a4-120">**System Center Operations Manager**   With this method, you use the Operations Manager to add monitoring for Lync Server.</span></span>

  - <span data-ttu-id="d36a4-121">**Microsoft Operations Manager Shell**   vous pouvez utiliser l’environnement de Shell Operations Manager pour importer directement ou pour résoudre les problèmes que vous rencontrez lorsque vous importez des packs d’administration à l’aide de la console System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d36a4-121">**Operations Manager Shell**   You can use the Operations Manager Shell to import directly or to troubleshoot any issues you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="d36a4-122">Importation des packs d’administration à l’aide de System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="d36a4-122">Importing the Management Packs by Using System Center Operations Manager</span></span>

1.  <span data-ttu-id="d36a4-123">Téléchargez les fichiers Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp et Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span><span class="sxs-lookup"><span data-stu-id="d36a4-123">Download the files Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span></span>

2.  <span data-ttu-id="d36a4-124">Dans System Center Operations Manager, cliquez sur **administration**.</span><span class="sxs-lookup"><span data-stu-id="d36a4-124">In System Center Operations Manager, click **Administration**.</span></span>

3.  <span data-ttu-id="d36a4-125">Dans le volet **Administration**, cliquez avec le bouton droit sur **Packs d’administration**, puis cliquez sur **Importer les packs d’administration**.</span><span class="sxs-lookup"><span data-stu-id="d36a4-125">In the **Administration** pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4.  <span data-ttu-id="d36a4-126">Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Ajouter**, puis sur **Ajouter à partir du disque**.</span><span class="sxs-lookup"><span data-stu-id="d36a4-126">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5.  <span data-ttu-id="d36a4-127">Dans la boîte de dialogue **connexion au catalogue en ligne** , cliquez sur **Annuler** pour empêcher le gestionnaire des opérations de passer en mode connexion afin de déterminer s’il existe des dépendances pour les packs de gestion Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d36a4-127">In the **Online Catalog Connection** dialog box, click **Cancel** to prevent Operations Manager from going online to see if any dependencies exist for the Lync Server management packs.</span></span> <span data-ttu-id="d36a4-128">Si vous utilisez System Center Operations Manager 2012, cliquez sur **non**.</span><span class="sxs-lookup"><span data-stu-id="d36a4-128">If you are using System Center Operations Manager 2012, click **No**.</span></span>

6.  <span data-ttu-id="d36a4-p107">Dans la boîte de dialogue **Sélectionner les packs d’administration à importer**, recherchez et sélectionnez les fichiers **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** et **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp**, puis cliquez sur **Ouvrir**. Pour sélectionner plusieurs fichiers dans la boîte de dialogue, cliquez sur le premier fichier, maintenez la touche Ctrl enfoncée et cliquez sur un autre fichier.</span><span class="sxs-lookup"><span data-stu-id="d36a4-p107">In the **Select Management Packs to import** dialog box, locate and select the files **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** and **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** and then click **Open**. To select multiple files in the dialog box, click the first file, hold down the Ctrl key and then click the second file.</span></span>

7.  <span data-ttu-id="d36a4-p108">Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Installer**. Si vous obtenez un message d’erreur et que l’installation échoue, cela signifie que les fichiers des packs d’administration se trouvent dans un dossier protégé par le contrôle du compte d’utilisateur Windows. Si cela se produit, copiez les fichiers dans un autre dossier et redémarrez le processus d’importation et d’installation.</span><span class="sxs-lookup"><span data-stu-id="d36a4-p108">In the **Select Management Packs** dialog box, click **Install**. If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control. If this occurs, copy the files to a different folder and then restart the import and installation process.</span></span>

8.  <span data-ttu-id="d36a4-p109">Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Fermer**. Notez que le processus d’importation et d’installation peut prendre plusieurs minutes.</span><span class="sxs-lookup"><span data-stu-id="d36a4-p109">In the **Select Management Packs** dialog box, click **Close**. Note that the import and installation process might require several minutes to complete.</span></span>

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="d36a4-136">Importation des packs d’administration à l’aide de l’environnement de commande Operations Manager</span><span class="sxs-lookup"><span data-stu-id="d36a4-136">Importing Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="d36a4-137">En règle générale, il est plus facile d’importer les packs d’administration à l’aide du gestionnaire des opérations. Toutefois, si une erreur se produit et que l’importation échoue, la console ne fournit pas toujours des rapports d’erreur appropriés.</span><span class="sxs-lookup"><span data-stu-id="d36a4-137">In general it is easier to import the management packs by using the Operations Manager.However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="d36a4-138">Par comparaison, le shell Operations Manager fournit des informations détaillées.</span><span class="sxs-lookup"><span data-stu-id="d36a4-138">By comparison, the Operations Manager Shell, provides detailed information.</span></span> <span data-ttu-id="d36a4-139">Si vous utilisez Operations Manager et que vous rencontrez des problèmes lors de l’importation d’un pack d’administration, importez le Pack à l’aide de l’environnement de commande Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d36a4-139">If you are using Operations Manager and you run into problems importing a management pack, import the pack by using the Operations Manager Shell .</span></span> <span data-ttu-id="d36a4-140">Operations Manager Shell fournit des informations supplémentaires qui peuvent vous aider à déterminer la cause de l’échec de l’importation.</span><span class="sxs-lookup"><span data-stu-id="d36a4-140">The Operations Manager Shell provides more information that might help you determine why the import failed.</span></span>

<span data-ttu-id="d36a4-141">Si vous utilisez System Center Operations Manager 2007 R2, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d36a4-141">If you are using System Center Operations Manager 2007 R2, complete the following procedure:</span></span>

1.  <span data-ttu-id="d36a4-142">Cliquez sur **Démarrer**, sur **tous les programmes**, sur **System Center Operations Manager 2007 R2**, puis sur **environnement gestionnaire des opérations**.</span><span class="sxs-lookup"><span data-stu-id="d36a4-142">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007 R2**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="d36a4-143">Dans l’environnement de ligne de commande Operations Manager, tapez la commande suivante à l’invite de commandes, en utilisant le chemin d’accès réel à votre copie du fichier Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="d36a4-143">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  <span data-ttu-id="d36a4-144">Une fois le premier pack d’administration importé, répétez la procédure à l’aide du chemin vers votre copie du fichier Microsoft.LS.2013.Monitoring.ComponentAndUser.mp :</span><span class="sxs-lookup"><span data-stu-id="d36a4-144">After you import the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  <span data-ttu-id="d36a4-145">Fermez le shell d’Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d36a4-145">Close the Operations Manager Shell.</span></span>

<span data-ttu-id="d36a4-146">Si vous utilisez System Center Operations Manager 2012, effectuez la procédure suivante à la place :</span><span class="sxs-lookup"><span data-stu-id="d36a4-146">If you are using System Center Operations Manager 2012, complete this procedure instead:</span></span>

1.  <span data-ttu-id="d36a4-147">Cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft System Center 2012**, sur **Operations Manager**, puis sur **environnement gestionnaire des opérations**.</span><span class="sxs-lookup"><span data-stu-id="d36a4-147">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="d36a4-148">Dans l’environnement de ligne de commande Operations Manager, tapez la commande suivante à l’invite de commandes, en utilisant le chemin d’accès réel à votre copie du fichier Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="d36a4-148">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  <span data-ttu-id="d36a4-149">Une fois le premier pack d’administration importé, répétez la procédure à l’aide du chemin vers votre copie du fichier Microsoft.LS.2013.Monitoring.ComponentAndUser.mp :</span><span class="sxs-lookup"><span data-stu-id="d36a4-149">After you have imported the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

