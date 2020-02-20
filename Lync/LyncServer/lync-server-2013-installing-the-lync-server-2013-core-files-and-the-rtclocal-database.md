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
ms.openlocfilehash: 17b3b1925607a80f143c57e6185c7a709b19ee0c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="c4ec3-102">Installation des fichiers principaux de Lync Server 2013 et de la base de données RTCLocal</span><span class="sxs-lookup"><span data-stu-id="c4ec3-102">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4ec3-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="c4ec3-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="c4ec3-104">Pour installer les fichiers principaux de Lync Server 2013 sur un ordinateur, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c4ec3-104">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="c4ec3-105">La base de données RTCLocal est installée automatiquement quand vous installez les fichiers principaux.</span><span class="sxs-lookup"><span data-stu-id="c4ec3-105">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="c4ec3-106">Notez que vous n’avez pas besoin d’installer SQL Server sur les nœuds observateur.</span><span class="sxs-lookup"><span data-stu-id="c4ec3-106">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="c4ec3-107">Au lieu de cela, SQL Server Express est automatiquement installé pour vous.</span><span class="sxs-lookup"><span data-stu-id="c4ec3-107">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="c4ec3-108">Pour installer les fichiers principaux de Lync Server 2013 et la base de données RTCLocal :</span><span class="sxs-lookup"><span data-stu-id="c4ec3-108">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="c4ec3-109">Sur l’ordinateur sur lequel se trouve le nœud observateur, cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Accessoires**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="c4ec3-109">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="c4ec3-110">Dans la fenêtre de la console, tapez la commande suivante, puis appuyez sur entrée, en utilisant le chemin d’accès approprié à vos fichiers d’installation de Lync Server :</span><span class="sxs-lookup"><span data-stu-id="c4ec3-110">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="c4ec3-111">Pour vérifier que les composants principaux de Lync Server ont été correctement installés, cliquez sur **Démarrer**, sur **tous les programmes**, sur **Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c4ec3-111">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="c4ec3-112">Dans l’environnement de ligne de commande Lync Server 2013 Management Shell, tapez la commande Windows PowerShell suivante, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="c4ec3-112">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="c4ec3-113">La première fois que vous exécutez cette commande, elle ne renvoie aucune donnée, car vous n’avez encore configuré aucun nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="c4ec3-113">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="c4ec3-114">Tant que la commande s’exécute sans renvoyer d’erreur, vous pouvez supposer que l’installation de Lync Server a réussi.</span><span class="sxs-lookup"><span data-stu-id="c4ec3-114">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="c4ec3-115">Si votre ordinateur nœud observateur se trouve à l’intérieur de votre réseau de périmètre, vous pouvez exécuter la commande suivante pour vérifier l’installation de Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="c4ec3-115">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="c4ec3-116">Vous recevrez des informations semblables aux suivantes, selon le nombre de stratégies de code confidentiel configurées dans votre organisation :</span><span class="sxs-lookup"><span data-stu-id="c4ec3-116">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="c4ec3-117">Si des informations sur vos stratégies de code confidentiel sont affichées, cela signifie que vous avez correctement installé les composants principaux.</span><span class="sxs-lookup"><span data-stu-id="c4ec3-117">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

