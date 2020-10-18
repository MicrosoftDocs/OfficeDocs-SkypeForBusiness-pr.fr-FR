---
title: 'Lync Server 2013 : installation des outils d’administration Lync Server'
description: 'Lync Server 2013 : Installez les outils d’administration Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca1ad96299197c3339d06c4f094784edc632e6b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574170"
---
# <a name="install-lync-server-2013-administrative-tools"></a><span data-ttu-id="fd232-103">Installer les outils d’administration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd232-103">Install Lync Server 2013 administrative tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd232-104">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="fd232-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="fd232-105">Cette rubrique décrit la procédure d’installation des outils d’administration nécessaires au déploiement et à la gestion de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fd232-105">This topic describes how to install the administrative tools you need to use to deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="fd232-106">Les outils d’administration sont installés par défaut sur chaque serveur exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fd232-106">The administrative tools are installed by default on each server running Lync Server 2013.</span></span> <span data-ttu-id="fd232-107">Vous pouvez également les installer sur d’autres ordinateurs, notamment des consoles d’administration dédiées.</span><span class="sxs-lookup"><span data-stu-id="fd232-107">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="fd232-108">Nous vous recommandons vivement d’installer les outils d’administration sur un ordinateur qui se trouve dans le même domaine ou la même forêt que le déploiement Lync Server 2013 que vous créez, car en procédant ainsi, vous êtes assuré que les étapes de préparation des services de domaine Active Directory sont déjà terminées, ce qui vous permet d’utiliser les outils d’administration sur cet ordinateur ultérieurement pour publier votre topologie.</span><span class="sxs-lookup"><span data-stu-id="fd232-108">We strongly recommend that you install the administrative tools on a computer that is in the same domain or forest as the Lync Server 2013 deployment you are creating because by doing so you make sure that Active Directory Domain Services preparation steps are already complete, which enables you to use the administrative tools on that computer later to publish your topology.</span></span>

<span data-ttu-id="fd232-109">Avant d’installer ou d’utiliser les outils d’administration Lync Server 2013, veillez à consulter les conditions requises en matière d’infrastructure, de système d’exploitation, de logiciel et d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="fd232-109">Make sure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="fd232-110">Pour plus d’informations sur les exigences d’infrastructure, voir [administrative Tools infrastructure Requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd232-110">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="fd232-111">Pour plus d’informations sur le système d’exploitation et la configuration logicielle requise pour l’installation des outils d’administration Lync Server 2013, voir [serveur et outils pris en charge par le système d’exploitation dans Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), la [configuration logicielle requise pour Lync Server 2013](lync-server-2013-additional-software-requirements.md), ainsi que la [prise en charge et les exigences des serveurs supplémentaires dans Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd232-111">For details about operating system and software requirements to install the Lync Server 2013 administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="fd232-112">Pour plus d’informations sur les droits utilisateur et les autorisations nécessaires à l’installation et à l’utilisation des outils, reportez-vous à la rubrique [droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span><span class="sxs-lookup"><span data-stu-id="fd232-112">For details about the user rights and permissions required to install and use the tools, see [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fd232-113">Si votre organisation exige que les services IIS (Internet Information Services) et l’ensemble des services web soient placés sur un lecteur autre que le lecteur système, vous pouvez modifier l’emplacement d’installation des fichiers Lync Server dans la boîte de dialogue Installation.</span><span class="sxs-lookup"><span data-stu-id="fd232-113">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="fd232-114">Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore.msi, les autres fichiers Lync Server 2013 seront également déployés sur ce lecteur.</span><span class="sxs-lookup"><span data-stu-id="fd232-114">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span>



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a><span data-ttu-id="fd232-115">Pour installer les outils d’administration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd232-115">To install the Lync Server 2013 administrative tools</span></span>

1.  <span data-ttu-id="fd232-p104">Connectez-vous en tant qu’administrateur local (minimum requis) à l’ordinateur sur lequel vous souhaitez installer les outils d’administration. Si vous êtes connecté en tant qu’utilisateur standard sur les systèmes d’exploitation Windows Vista ou Windows 7 et que le contrôle de compte d’utilisateur (UAC) est activé, vous devez entrer votre nom d’utilisateur et votre mot de passe en qualité d’administrateur local ou ceux d’un domaine équivalent.</span><span class="sxs-lookup"><span data-stu-id="fd232-p104">Log on as a local administrator (minimum requirement) to the computer where you want to install the administrative tools. If you are logged on as an a standard user on the Windows Vista or Windows 7 operating systems, and User Account Control (UAC) is enabled, you will be prompted for the local administrator or a domain equivalent user name and password.</span></span>

2.  <span data-ttu-id="fd232-118">Localisez le support d’installation sur votre ordinateur, puis double-cliquez sur \\ configurer \\ amd64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="fd232-118">Locate the installation media on your computer, and then double-click \\Setup\\amd64\\Setup.exe.</span></span>

3.  <span data-ttu-id="fd232-119">Si le système vous invite à installer le package distribuable Microsoft Visual C++ 2008, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="fd232-119">If you are prompted to install the Microsoft Visual C++ 2008 distributable, click **Yes**.</span></span>

4.  <span data-ttu-id="fd232-120">Sur la page **emplacement d’installation de Microsoft Lync Server 2013** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd232-120">On the **Microsoft Lync Server 2013 Installation Location** page, click **OK**.</span></span> <span data-ttu-id="fd232-121">Remplacez ce chemin par le chemin d’accès à un autre emplacement ou lecteur si vous souhaitez que les fichiers soient installés à un autre endroit.</span><span class="sxs-lookup"><span data-stu-id="fd232-121">Change this path to another location or drive if you need to have the files installed to another location.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fd232-122">Si votre organisation exige que vous localisiez Internet Information Services (IIS) et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès de l’emplacement d’installation des fichiers Lync Server 2013 dans la boîte de dialogue Configuration.</span><span class="sxs-lookup"><span data-stu-id="fd232-122">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box.</span></span> <span data-ttu-id="fd232-123">Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore.msi, les autres fichiers Lync Server 2013 seront également déployés sur ce lecteur.</span><span class="sxs-lookup"><span data-stu-id="fd232-123">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive too.</span></span>

    
    </div>

5.  <span data-ttu-id="fd232-p107">Dans la page **Contrat de Licence Utilisateur Final**, vérifiez les termes du contrat de licence, cliquez sur **J’accepte**, puis cliquez sur **OK**. Cette étape est obligatoire pour continuer.</span><span class="sxs-lookup"><span data-stu-id="fd232-p107">On the **End User License Agreement** page, review the license terms, click **I accept**, and then click **OK**. This step is required before you can continue.</span></span>

6.  <span data-ttu-id="fd232-126">Sur la page **Microsoft Lync Server 2013 – Assistant Déploiement** , cliquez sur **installer les outils d’administration**.</span><span class="sxs-lookup"><span data-stu-id="fd232-126">On the **Microsoft Lync Server 2013 – Deployment Wizard** page, click **Install Administrator Tools**.</span></span>

7.  <span data-ttu-id="fd232-127">Lorsque l’installation est terminée cliquez sur **Quitter**.</span><span class="sxs-lookup"><span data-stu-id="fd232-127">When the installation successfully completes, click **Exit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fd232-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fd232-128">See Also</span></span>


[<span data-ttu-id="fd232-129">Ouvrir les outils d’administration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd232-129">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="fd232-130">Outils d’administration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd232-130">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

