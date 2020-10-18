---
title: 'Lync Server 2013 : installation de l’outil de planification'
description: 'Lync Server 2013 : installation de l’outil de planification.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Planning Tool
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615046(v=OCS.15)
ms:contentKeyID: 51541525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11836e2c86cb01d6f911670a9eeafef0c31c0af4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575060"
---
# <a name="installing-the-planning-tool-in-lync-server-2013"></a><span data-ttu-id="71a35-103">Installation de l’outil de planification dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71a35-103">Installing the Planning Tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71a35-104">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="71a35-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="71a35-105">Avant de commencer à concevoir et à planifier votre infrastructure Lync Server 2013 à l’aide de l’outil de planification Microsoft Lync Server 2013, vous devez d’abord installer l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="71a35-105">Before you begin designing and planning your Lync Server 2013 infrastructure by using the Microsoft Lync Server 2013, Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="71a35-106">L’outil de planification n’a pas besoin d’être déployé sur une station de travail ou un serveur qui fait partie du domaine ou de l’infrastructure dans lequel vous prévoyez d’installer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71a35-106">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Lync Server 2013.</span></span> <span data-ttu-id="71a35-107">Le fichier Lisez-moi qui accompagne l’outil de planification détaille les informations importantes sur l’installation et l’utilisation de l’outil.</span><span class="sxs-lookup"><span data-stu-id="71a35-107">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="71a35-108">Certaines des informations contenues dans le fichier Lisez-moi sont dupliquées ici pour plus de clarté.</span><span class="sxs-lookup"><span data-stu-id="71a35-108">Some of the information in the Readme file is duplicated here for clarity.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="71a35-109">L’outil de planification nécessite une installation par un utilisateur disposant de droits et d’autorisations d’administrateur sur l’ordinateur sur lequel l’outil doit être installé.</span><span class="sxs-lookup"><span data-stu-id="71a35-109">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>



</div>

<span data-ttu-id="71a35-110">Les systèmes d’exploitation pris en charge pour l’installation et le fonctionnement de l’outil de planification sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="71a35-110">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

  - <span data-ttu-id="71a35-111">Windows 8</span><span class="sxs-lookup"><span data-stu-id="71a35-111">Windows 8</span></span>

  - <span data-ttu-id="71a35-112">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="71a35-112">Windows 8.1</span></span>

  - <span data-ttu-id="71a35-113">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="71a35-113">Windows Server 2012</span></span>

  - <span data-ttu-id="71a35-114">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="71a35-114">Windows Server 2012 R2</span></span>

  - <span data-ttu-id="71a35-115">Windows 7, édition 32 bits</span><span class="sxs-lookup"><span data-stu-id="71a35-115">Windows 7, 32-bit edition</span></span>

  - <span data-ttu-id="71a35-116">Windows 7, 64-bit Edition à l’aide de Windows sur Win32 (WOW)</span><span class="sxs-lookup"><span data-stu-id="71a35-116">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

  - <span data-ttu-id="71a35-117">Windows Server 2008 R2, à l’aide de WOW</span><span class="sxs-lookup"><span data-stu-id="71a35-117">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="71a35-118">En outre, l’outil de planification nécessite Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="71a35-118">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="71a35-119">Une fois que la configuration requise pour la préinstallation est satisfaite, vous pouvez installer l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="71a35-119">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>

<div>

## <a name="to-install-the-planning-tool"></a><span data-ttu-id="71a35-120">Pour installer l’outil de planification</span><span class="sxs-lookup"><span data-stu-id="71a35-120">To install the Planning Tool</span></span>

1.  <span data-ttu-id="71a35-121">Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="71a35-121">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="71a35-122">À l’aide de l’Explorateur Windows ou d’une fenêtre de commande, recherchez le répertoire dans lequel vous avez téléchargé les fichiers d’installation de l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="71a35-122">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3.  <span data-ttu-id="71a35-123">Recherchez le LyncPlanningTool.msi.</span><span class="sxs-lookup"><span data-stu-id="71a35-123">Locate the LyncPlanningTool.msi.</span></span> <span data-ttu-id="71a35-124">Dans l’Explorateur Windows, double-cliquez sur le fichier.</span><span class="sxs-lookup"><span data-stu-id="71a35-124">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="71a35-125">Dans la fenêtre de commande, tapez le nom du fichier, puis appuyez sur **entrée** pour exécuter le fichier.</span><span class="sxs-lookup"><span data-stu-id="71a35-125">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4.  <span data-ttu-id="71a35-126">Sur la page d’accueil de l’Assistant de configuration de l' **outil de planification Microsoft Lync Server 2013**, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="71a35-126">On the Welcome page of the **Microsoft Lync Server 2013, Planning Tool Setup Wizard**, click **Next**.</span></span>

5.  <span data-ttu-id="71a35-127">Passez en revue le **contrat de licence utilisateur final**, sélectionnez **J’accepte les termes du contrat de licence** si vous choisissez d’accepter les conditions d’utilisation dans le contrat de licence, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="71a35-127">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6.  <span data-ttu-id="71a35-128">Choisissez l’emplacement d’installation des fichiers de l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="71a35-128">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="71a35-129">L’emplacement par défaut est C : \\ Program Files (x86) \\ Microsoft Lync Server 2013 \\ Planning Tool.</span><span class="sxs-lookup"><span data-stu-id="71a35-129">The default location is C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool.</span></span> <span data-ttu-id="71a35-130">Si vous souhaitez modifier l’emplacement d’installation, cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="71a35-130">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="71a35-131">Sur **modifier le dossier de destination**, parcourez ou tapez l’emplacement d’installation des fichiers, cliquez sur **OK**, puis sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="71a35-131">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="71a35-132">Le programme d’installation est maintenant prêt à installer l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="71a35-132">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="71a35-133">Cliquez sur **installer** pour commencer le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="71a35-133">Click **Install** to begin the installation process.</span></span>

8.  <span data-ttu-id="71a35-134">L’installation démarre et la progression s’affiche.</span><span class="sxs-lookup"><span data-stu-id="71a35-134">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="71a35-135">Une fois l’installation terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="71a35-135">After the installation is successfully completed, click **Finish**.</span></span>

9.  <span data-ttu-id="71a35-136">L’outil de planification est prêt à l’emploi.</span><span class="sxs-lookup"><span data-stu-id="71a35-136">The Planning Tool is ready for use.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="71a35-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="71a35-137">See Also</span></span>


[<span data-ttu-id="71a35-138">Installation de logiciels facultatifs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71a35-138">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

