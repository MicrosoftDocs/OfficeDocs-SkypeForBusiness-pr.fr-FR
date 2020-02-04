---
title: Installation des fichiers principaux de Lync Server 2013 et de la base de données RTCLocal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da8f0dd1fb83c595ed444a487d0321c571a09315
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="00fbd-102">Installation des fichiers principaux de Lync Server 2013 et de la base de données RTCLocal</span><span class="sxs-lookup"><span data-stu-id="00fbd-102">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00fbd-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="00fbd-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="00fbd-104">Pour installer les fichiers principaux de Lync Server 2013 sur un ordinateur, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="00fbd-104">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="00fbd-105">La base de données RTCLocal est automatiquement installée lors de l’installation des fichiers principaux.</span><span class="sxs-lookup"><span data-stu-id="00fbd-105">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="00fbd-106">Notez que vous n’avez pas besoin d’installer SQL Server sur les nœuds d’observation.</span><span class="sxs-lookup"><span data-stu-id="00fbd-106">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="00fbd-107">À la place, SQL Server Express est automatiquement installé pour vous.</span><span class="sxs-lookup"><span data-stu-id="00fbd-107">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="00fbd-108">Pour installer les fichiers principaux de Lync Server 2013 et la base de données RTCLocal :</span><span class="sxs-lookup"><span data-stu-id="00fbd-108">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="00fbd-109">Sur l’ordinateur du nœud d’observation, cliquez sur **Démarrer**, sur **tous les programmes**, sur **accessoires**, cliquez avec le bouton droit sur **invite de commandes**, puis cliquez sur **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="00fbd-109">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="00fbd-110">Dans la fenêtre de la console, tapez la commande suivante, puis appuyez sur entrée en utilisant le chemin approprié vers vos fichiers d’installation de Lync Server :</span><span class="sxs-lookup"><span data-stu-id="00fbd-110">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="00fbd-111">Pour vérifier que les composants principaux de Lync Server sont correctement installés, cliquez sur **Démarrer**, sur **tous les programmes**, sur **Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="00fbd-111">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="00fbd-112">Dans Lync Server 2013 Management Shell, tapez la commande Windows PowerShell suivante, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="00fbd-112">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="00fbd-113">Lorsque vous exécutez cette commande pour la première fois, aucune donnée n’est renvoyée, car vous n’avez pas encore configuré de nœuds FileSystemWatcher.</span><span class="sxs-lookup"><span data-stu-id="00fbd-113">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="00fbd-114">Tant que la commande est exécutée sans renvoyer d’erreur, vous pouvez supposer que le programme d’installation de Lync Server s’est terminé correctement.</span><span class="sxs-lookup"><span data-stu-id="00fbd-114">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="00fbd-115">Si votre ordinateur est situé à l’intérieur de votre réseau de périmètre, vous pouvez exécuter la commande suivante pour vérifier l’installation de Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="00fbd-115">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="00fbd-116">Vous recevrez des informations similaires à ce qui suit, en fonction du nombre de stratégies de code confidentiel (PIN) configurées pour une utilisation au sein de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="00fbd-116">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="00fbd-117">Si vous voyez des informations relatives à vos stratégies de code confidentiel, cela signifie que vous avez correctement installé les composants principaux.</span><span class="sxs-lookup"><span data-stu-id="00fbd-117">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

