---
title: 'Lync Server 2013 : Installation des outils d’administration Lync Server'
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
ms.openlocfilehash: 5ebdcf355618c4257ceaeced5f5e4032ede40cec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a><span data-ttu-id="5fdbe-102">Installation des outils d’administration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fdbe-102">Install Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fdbe-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5fdbe-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5fdbe-104">Cette rubrique explique comment installer les outils d’administration que vous devez utiliser pour déployer et gérer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-104">This topic describes how to install the administrative tools you need to use to deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="5fdbe-105">Les outils d’administration sont installés par défaut sur chaque serveur exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-105">The administrative tools are installed by default on each server running Lync Server 2013.</span></span> <span data-ttu-id="5fdbe-106">Par ailleurs, vous pouvez installer les outils d’administration sur d’autres ordinateurs, par exemple des consoles d’administration dédiées.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="5fdbe-107">Nous vous recommandons vivement d’installer les outils d’administration sur un ordinateur qui se trouve dans le même domaine ou la même forêt que le déploiement de Lync Server 2013 que vous créez, car cela vous permet de vous assurer que les étapes de préparation des services de domaine Active Directory est déjà activée. terminé, qui vous permet d’utiliser les outils d’administration de cet ordinateur plus tard pour publier votre topologie.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-107">We strongly recommend that you install the administrative tools on a computer that is in the same domain or forest as the Lync Server 2013 deployment you are creating because by doing so you make sure that Active Directory Domain Services preparation steps are already complete, which enables you to use the administrative tools on that computer later to publish your topology.</span></span>

<span data-ttu-id="5fdbe-108">Assurez-vous d’avoir examiné les exigences relatives aux privilèges d’infrastructure, de système d’exploitation, de logiciels et d’administrateur avant d’installer ou d’utiliser les outils d’administration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-108">Make sure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="5fdbe-109">Pour plus d’informations sur la configuration requise en matière d’infrastructure, voir la [Configuration requise infrastructure des outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fdbe-109">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="5fdbe-110">Pour plus d’informations sur le système d’exploitation et la configuration logicielle requise pour l’installation des outils d’administration de Lync Server 2013, voir [prise en charge des systèmes d’exploitation serveur et outils dans Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [configuration logicielle requise pour Lync Server 2013](lync-server-2013-additional-software-requirements.md), et [prise en charge et configuration supplémentaires du](lync-server-2013-additional-server-support-and-requirements.md)serveur sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-110">For details about operating system and software requirements to install the Lync Server 2013 administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="5fdbe-111">Pour plus d’informations sur les droits d’utilisateur et les autorisations nécessaires pour installer et utiliser les outils, voir [droits d’administrateur et autorisations nécessaires pour l’installation et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span><span class="sxs-lookup"><span data-stu-id="5fdbe-111">For details about the user rights and permissions required to install and use the tools, see [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5fdbe-112">Si votre organisation nécessite que vous localisiez Internet Information Services (IIS) et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès de l’emplacement d’installation des fichiers du serveur Lync dans la boîte de dialogue d’installation.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-112">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="5fdbe-113">Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, les autres fichiers Lync Server 2013 sont déployés également sur ce lecteur.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-113">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span>



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a><span data-ttu-id="5fdbe-114">Pour installer les outils d’administration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fdbe-114">To install the Lync Server 2013 administrative tools</span></span>

1.  <span data-ttu-id="5fdbe-115">Ouvrez une session en tant qu’administrateur local (configuration minimale) pour l’ordinateur sur lequel vous voulez installer les outils d’administration.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-115">Log on as a local administrator (minimum requirement) to the computer where you want to install the administrative tools.</span></span> <span data-ttu-id="5fdbe-116">Si vous êtes connecté en tant qu’utilisateur standard sur les systèmes d’exploitation Windows Vista ou Windows 7, et que le contrôle de compte d’utilisateur (UAC) est activé, vous serez invité à entrer le nom d’utilisateur et le mot de passe d’administrateur local.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-116">If you are logged on as an a standard user on the Windows Vista or Windows 7 operating systems, and User Account Control (UAC) is enabled, you will be prompted for the local administrator or a domain equivalent user name and password.</span></span>

2.  <span data-ttu-id="5fdbe-117">Recherchez le support d’installation sur votre ordinateur, puis double-cliquez \\sur\\Setup\\. exe. exe.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-117">Locate the installation media on your computer, and then double-click \\Setup\\amd64\\Setup.exe.</span></span>

3.  <span data-ttu-id="5fdbe-118">Si vous êtes invité à installer Microsoft Visual C++ 2008 distribuable, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-118">If you are prompted to install the Microsoft Visual C++ 2008 distributable, click **Yes**.</span></span>

4.  <span data-ttu-id="5fdbe-119">Dans la page de l’emplacement de l' **installation de Microsoft Lync Server 2013** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-119">On the **Microsoft Lync Server 2013 Installation Location** page, click **OK**.</span></span> <span data-ttu-id="5fdbe-120">Changez de chemin d’accès à un autre emplacement ou lecteur si vous avez besoin d’installer les fichiers à un autre emplacement.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-120">Change this path to another location or drive if you need to have the files installed to another location.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5fdbe-121">Si votre organisation nécessite que vous localisiez Internet Information Services (IIS) et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès d’installation pour les fichiers Lync Server 2013 dans la boîte de dialogue d’installation.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-121">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box.</span></span> <span data-ttu-id="5fdbe-122">Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, les autres fichiers Lync Server 2013 seront également déployés sur ce lecteur.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-122">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive too.</span></span>

    
    </div>

5.  <span data-ttu-id="5fdbe-123">Sur la page **contrat de licence utilisateur final** , passez en revue les termes du contrat de licence, cliquez sur **J’accepte**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-123">On the **End User License Agreement** page, review the license terms, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="5fdbe-124">Cette étape est nécessaire pour pouvoir continuer.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-124">This step is required before you can continue.</span></span>

6.  <span data-ttu-id="5fdbe-125">Dans la page **Microsoft Lync Server 2013-Assistant Déploiement** , cliquez sur **installer les outils d’administration**.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-125">On the **Microsoft Lync Server 2013 – Deployment Wizard** page, click **Install Administrator Tools**.</span></span>

7.  <span data-ttu-id="5fdbe-126">Lorsque l’installation est terminée, cliquez sur **quitter**.</span><span class="sxs-lookup"><span data-stu-id="5fdbe-126">When the installation successfully completes, click **Exit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5fdbe-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5fdbe-127">See Also</span></span>


[<span data-ttu-id="5fdbe-128">Ouvrez les outils d’administration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fdbe-128">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="5fdbe-129">Outils d’administration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fdbe-129">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

