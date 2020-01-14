---
title: 'Lync Server 2013 : Configuration système requise pour les serveurs exécutant Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 301cd234e2218fc806423a9ffe9beb49994402f2
ms.sourcegitcommit: 208179a3dd166f53b5a3058242cb84207909f4ee
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2020
ms.locfileid: "41104493"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a><span data-ttu-id="8e716-102">Configuration système requise pour les serveurs exécutant Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e716-102">System requirements for servers running Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e716-103">_**Dernière modification de la rubrique :** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="8e716-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8e716-104">Pour plus d’informations sur la configuration matérielle requise, voir <A href="lync-server-2013-server-hardware-platforms.md">plates-formes matérielles pour Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8e716-104">For details about hardware requirements, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="8e716-105">Les serveurs Standard Edition et Enterprise Edition partagent les mêmes exigences logicielles.</span><span class="sxs-lookup"><span data-stu-id="8e716-105">Standard Edition and Enterprise Edition servers share the same software requirements.</span></span>

<span data-ttu-id="8e716-106">Les serveurs exécutant Lync Server 2013 Enterprise Edition sont destinés aux grandes organisations comme déploiement principal de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="8e716-106">Servers running Lync Server 2013, Enterprise Edition are intended for large organizations as the main organizational deployment.</span></span> <span data-ttu-id="8e716-107">Le serveur Enterprise Edition est conçu pour être mis à niveau vers approximativement 80 000 utilisateurs familiaux par pool.</span><span class="sxs-lookup"><span data-stu-id="8e716-107">Enterprise Edition server is designed to scale to approximately 80,000 homed users per pool.</span></span> <span data-ttu-id="8e716-108">Les serveurs exécutant Lync Server 2013 Standard Edition sont destinés aux organisations plus petites et aux endroits distants du déploiement principal de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="8e716-108">Servers running Lync Server 2013, Standard Edition are intended for smaller organizations and remote locations from the main organization deployment.</span></span> <span data-ttu-id="8e716-109">Une paire de serveurs Standard Edition peut prendre en charge jusqu’à 5 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8e716-109">One pair of Standard Edition servers can support up to 5,000 users..</span></span> <span data-ttu-id="8e716-110">Pour plus d’informations sur les différences entre les serveurs Standard Edition et les serveurs Enterprise Edition, voir [vue d’ensemble du déploiement pour Lync Server 2013](lync-server-2013-deployment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8e716-110">For details on the differences between Standard Edition servers and Enterprise Edition servers, see [Deployment overview for Lync Server 2013](lync-server-2013-deployment-overview.md).</span></span>

<div>

## <a name="operating-system-installation"></a><span data-ttu-id="8e716-111">Installation du système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="8e716-111">Operating System Installation</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8e716-112">Lync Server 2013 est disponible uniquement dans une édition 64 bits, qui nécessite une version matérielle 64 bits et une édition en 64 bits du système d’exploitation Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8e716-112">Lync Server 2013 is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of the Windows Server operating system.</span></span> <span data-ttu-id="8e716-113">Une édition 32 bits de Lync Server 2013 n’est pas disponible dans cette version.</span><span class="sxs-lookup"><span data-stu-id="8e716-113">A 32-bit edition of Lync Server 2013 is not available with this release.</span></span>



</div>

<span data-ttu-id="8e716-114">Les éditions standard du serveur et Enterprise Edition peuvent utiliser l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="8e716-114">Standard Edition and Enterprise Edition server can use any of the following:</span></span>

  - <span data-ttu-id="8e716-115">Windows Server 2008 R2 SP1 ou le dernier Service Pack</span><span class="sxs-lookup"><span data-stu-id="8e716-115">Windows Server 2008 R2 SP1 or latest service pack</span></span>

  - <span data-ttu-id="8e716-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="8e716-116">Windows Server 2012</span></span>

  - <span data-ttu-id="8e716-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="8e716-117">Windows Server 2012 R2</span></span>

<span data-ttu-id="8e716-118">Installez le logiciel du système d’exploitation sur le serveur frontal Standard Edition Server ou Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="8e716-118">Install the operating system software on the Standard Edition Server or Enterprise Edition Front End Server.</span></span> <span data-ttu-id="8e716-119">Appliquez toutes les mises à jour afin de faire en sorte que le système d’exploitation dispose de la dernière mise à jour et du niveau de mise à jour requis conformément aux normes de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8e716-119">Apply all updates in order to bring the operating system up to the latest update and required update level consistent with your organization’s standards.</span></span> <span data-ttu-id="8e716-120">Pour plus d’informations sur la configuration requise, reportez-vous à la [prise en charge des systèmes d’exploitation serveur et outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation relative à la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="8e716-120">For more details about the operating requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

> [!NOTE] <span data-ttu-id="8e716-121">La mise à niveau sur place du système d’exploitation n’est pas prise en charge avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8e716-121">In-place upgrade of the operating system is not supported with Lync Server 2013.</span></span>  <span data-ttu-id="8e716-122">Vous devez déployer un pool distinct et migrer les utilisateurs vers le nouveau pool avec un autre système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="8e716-122">You must deploy a separate pool and migrate users to the new pool with a different operating system.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8e716-123">Pour que Lync Server 2013 fonctionne sur Windows Server 2012 R2, il est possible que vous deviez modifier la valeur d’une clé de Registre dans Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8e716-123">For Lync Server 2013 to work on Windows Server 2012 R2, you may need to change the value of a registry key in Windows Server.</span></span> <span data-ttu-id="8e716-124">Ce changement est susceptible d’être nécessaire pour le bon fonctionnement des certificats et permettre aux clients de s’inscrire à des appareils distants.</span><span class="sxs-lookup"><span data-stu-id="8e716-124">This change may be necessary for certificates to work correctly, and for clients to register with Survivable Branch Appliances.</span></span> <span data-ttu-id="8e716-125">Pour plus d’informations, <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>reportez-vous à.</span><span class="sxs-lookup"><span data-stu-id="8e716-125">For more information, see <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>.</span></span>



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a><span data-ttu-id="8e716-126">Logiciels supplémentaires pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e716-126">Additional Software for Lync Server 2013</span></span>

<span data-ttu-id="8e716-127">Outre les mises à jour requises pour le système d’exploitation, Lync Server 2013 nécessite le fonctionnement des rôles, fonctionnalités et logiciels du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="8e716-127">In addition to the updates required for the operating system, Lync Server 2013 requires operating system roles, features, and software to operate.</span></span> <span data-ttu-id="8e716-128">Pour plus d’informations sur les logiciels supplémentaires qui doivent être installés avant de publier votre topologie et d’installer Lync Server 2013, voir [configuration logicielle requise pour Lync server 2013](lync-server-2013-additional-software-requirements.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="8e716-128">For details about the additional software that must be installed prior to publishing your topology and installing Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a><span data-ttu-id="8e716-129">Logiciel supplémentaire nécessaire pour tous les rôles de serveur</span><span class="sxs-lookup"><span data-stu-id="8e716-129">Additional Software Necessary for All Server Roles</span></span>

<span data-ttu-id="8e716-130">Sur tous les rôles de serveur, vous devez également vous assurer que l’interface de ligne de commande Windows PowerShell 3,0 et Microsoft .NET Framework 4,5 sont installés.</span><span class="sxs-lookup"><span data-stu-id="8e716-130">On all server roles, you must also make sure that Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are installed.</span></span>

<span data-ttu-id="8e716-131">Par ailleurs, l’interface de ligne de commande Windows PowerShell 3,0 et Microsoft .NET Framework 4,5 sont nécessaires sur tout ordinateur sur lequel vous allez exécuter les outils d’administration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8e716-131">Additionally, Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are required on any computer where you will run the Lync Server administrative tools.</span></span>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="8e716-132">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="8e716-132">Windows PowerShell 3.0</span></span>

<span data-ttu-id="8e716-133">Lync Server 2013 nécessite l’installation de Windows PowerShell 3,0 sur les ordinateurs qui participeront à la topologie de votre serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="8e716-133">Lync Server 2013 requires you to install Windows PowerShell 3.0 on each computer that will take part in your Lync Server topology.</span></span> <span data-ttu-id="8e716-134">Pour plus d’informations sur l’installation de Windows PowerShell 3,0, voir [installation de Windows powershell 3,0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="8e716-134">For details about installing Windows PowerShell 3.0, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8e716-135">Sur Windows Server&nbsp;2008&nbsp;R2 avec SP1, l’interface de ligne de commande Windows PowerShell 3,0 ne peut pas être installée avant l’installation de Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="8e716-135">On Windows Server&nbsp;2008&nbsp;R2 with SP1, Windows PowerShell command-line interface 3.0 cannot be installed before installing Microsoft .NET Framework 4.5.</span></span>



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="8e716-136">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="8e716-136">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="8e716-137">Lorsque vous installez Microsoft .NET Framework 4,5 sur des serveurs exécutant Lync Server 2013 sur Windows Server 2012 ou Windows Server 2012 R2, vous devez effectuer une étape supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="8e716-137">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 on Windows Server 2012 or Windows Server 2012 R2, you must perform one additional step.</span></span> <span data-ttu-id="8e716-138">Après avoir installé .NET Framework 4,5, utilisez le gestionnaire de serveur pour installer l’activation HTTP.</span><span class="sxs-lookup"><span data-stu-id="8e716-138">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="8e716-139">**Pour installer l’activation HTTP de .NET 4,5 sur Windows Server 2012 ou Windows Server 2012 R2**</span><span class="sxs-lookup"><span data-stu-id="8e716-139">**To Install .NET 4.5 HTTP Activation on Windows Server 2012 or Windows Server 2012 R2**</span></span>

1.  <span data-ttu-id="8e716-140">Dans le menu **Démarrer** , cliquez sur **programmes**, sur **Outils d’administration**, puis sur gestionnaire de **serveur**.</span><span class="sxs-lookup"><span data-stu-id="8e716-140">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="8e716-141">Dans le gestionnaire de serveur, sous **fonctionnalités récapitulatives**, sélectionnez **Ajouter des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="8e716-141">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="8e716-142">Développez **.NET Framework 4,5**.</span><span class="sxs-lookup"><span data-stu-id="8e716-142">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="8e716-143">Sélectionnez **activation WCF** si ce n’est pas déjà fait.</span><span class="sxs-lookup"><span data-stu-id="8e716-143">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="8e716-144">Ensuite, sélectionnez **activation http**.</span><span class="sxs-lookup"><span data-stu-id="8e716-144">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="8e716-145">Cliquez sur **suivant** et suivez les invites pour terminer l’installation.</span><span class="sxs-lookup"><span data-stu-id="8e716-145">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

