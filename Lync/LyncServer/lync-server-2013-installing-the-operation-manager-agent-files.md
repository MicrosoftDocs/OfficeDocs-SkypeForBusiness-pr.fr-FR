---
title: 'Lync Server 2013 : installation des fichiers de l’agent Operation Manager'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f75e9b6f8c3f7eb7151cf0d67a62f5e2a03a65f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a><span data-ttu-id="fdcc2-102">Installation des fichiers de l’agent Operation Manager dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdcc2-102">Installing the Operation Manager agent files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdcc2-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="fdcc2-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="fdcc2-104">Pour installer les fichiers de l’agent Operations Manager sur l’ordinateur, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="fdcc2-104">To install the Operations Manager agent files on the computer, complete the following steps.</span></span>

1.  <span data-ttu-id="fdcc2-105">Sur le média de configuration de System Center, double-cliquez sur **SetupOM. exe**.</span><span class="sxs-lookup"><span data-stu-id="fdcc2-105">On your System Center setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="fdcc2-106">Dans installation de System Center Operation Manager, cliquez sur **installer l’agent Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="fdcc2-106">In System Center Operation Manager setup, click **Install Operations Manager Agent**.</span></span>

3.  <span data-ttu-id="fdcc2-107">Dans l’Assistant Configuration de System Center, dans la page Bienvenue dans l’Assistant **configuration de System Center Operations Manager** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fdcc2-107">In System Center Setup wizard, on the **Welcome to the System Center Operations Manager Setup** wizard page, click **Next**.</span></span>

4.  <span data-ttu-id="fdcc2-108">Dans la page **dossier de destination** , sélectionnez le dossier dans lequel les fichiers de l’agent Operations Manager seront installés, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fdcc2-108">On the **Destination Folder** page, select the folder where the Operations Manager Agent files will be installed, and then click **Next**.</span></span>

5.  <span data-ttu-id="fdcc2-109">Dans la page **configuration du groupe de gestion** , sélectionnez spécifier les informations du groupe d' **administration**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fdcc2-109">On the **Management Group Configuration** page, select **Specify Management Group information**, and then click **Next**.</span></span>

6.  <span data-ttu-id="fdcc2-110">Dans la page **configuration du groupe** de gestion, tapez le nom de votre groupe d’administration Operations Manager dans la zone Nom du groupe de **gestion** , puis tapez le nom d’hôte de votre serveur Operations Manager (par exemple, ATL-SCOM-001) dans la zone serveur de **gestion** .</span><span class="sxs-lookup"><span data-stu-id="fdcc2-110">On the **Management Group Configuration** page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="fdcc2-111">Si vous avez modifié le numéro de port utilisé par Operations Manager, entrez le nouveau numéro de port dans la zone port du serveur de gestion.</span><span class="sxs-lookup"><span data-stu-id="fdcc2-111">If you have changed the port number used by Operations Manager, then type the new port number in the Management Server Port box.</span></span> <span data-ttu-id="fdcc2-112">Dans le cas contraire, laissez le port à la valeur par défaut 5723, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fdcc2-112">Otherwise, leave the port at the default value of 5723 and click **Next**.</span></span>

7.  <span data-ttu-id="fdcc2-113">Sur la page **compte d’action** de l’agent, sélectionnez **système local**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fdcc2-113">On the **Agent Action Account** page, select **Local System**, and then click **Next**.</span></span>

8.  <span data-ttu-id="fdcc2-114">Sur la page **Microsoft Update** , sélectionnez **je ne veux pas utiliser Microsoft Update**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fdcc2-114">On the **Microsoft Update** page, select **I don't want to use Microsoft Update**, and then click **Next**.</span></span>

9.  <span data-ttu-id="fdcc2-115">Sur la page **prêt pour l’installation** , cliquez sur **installer**.</span><span class="sxs-lookup"><span data-stu-id="fdcc2-115">On the **Ready to Install** page, click **Install**.</span></span>

10. <span data-ttu-id="fdcc2-116">Dans la page **fin de l’Assistant Configuration de System Center Operations Manager** , cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="fdcc2-116">On the **Completing the System Center Operations Manager Setup wizard** page, click **Finish**.</span></span>

11. <span data-ttu-id="fdcc2-117">Cliquez sur **Quitter**.</span><span class="sxs-lookup"><span data-stu-id="fdcc2-117">Click **Exit**.</span></span>

<span data-ttu-id="fdcc2-118">Si vous utilisez System Center 2007 R2, vous pouvez vérifier que l’agent a été créé en cliquant sur **Démarrer**, sur **tous les programmes**, sur **System Center Operations Manager 2007 R2**, puis sur **Operations Manager Shell**.</span><span class="sxs-lookup"><span data-stu-id="fdcc2-118">If you are using System Center 2007 R2, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2007 R2**, and then clicking **Operations Manager Shell**.</span></span> <span data-ttu-id="fdcc2-119">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span><span class="sxs-lookup"><span data-stu-id="fdcc2-119">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-Agent 

<span data-ttu-id="fdcc2-120">La liste de tous vos agents Operations Manager s’affiche à l’écran.</span><span class="sxs-lookup"><span data-stu-id="fdcc2-120">A list of all your Operations Manager agents will appear onscreen.</span></span>

<span data-ttu-id="fdcc2-121">Si vous utilisez System Center 2012, exécutez la commande suivante à partir du shell Operations 2012 Manager :</span><span class="sxs-lookup"><span data-stu-id="fdcc2-121">If you are using System Center 2012, run this command from the Operations 2012 Manager Shell:</span></span>

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

