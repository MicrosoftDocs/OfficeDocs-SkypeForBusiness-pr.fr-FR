---
title: Conditions préalables
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5ffc74e80547df1dd451cd86d681e85befe334
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a><span data-ttu-id="751c3-102">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="751c3-102">Prerequisites</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="751c3-103">_**Dernière modification de la rubrique :** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="751c3-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="751c3-104">Il existe différentes exigences en matière de configuration du matériel, des logiciels et des systèmes, dont vous aurez besoin pour exécuter l’outil de contrainte et de performances de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="751c3-104">There are various hardware, software, and system configuration requirements that you’ll need to run the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="client-hardware-requirements"></a><span data-ttu-id="751c3-105">Configuration matérielle requise pour le client</span><span class="sxs-lookup"><span data-stu-id="751c3-105">Client Hardware Requirements</span></span>

<span data-ttu-id="751c3-106">Pour exécuter l’outil de contrainte et de performances de Lync Server 2013 sur votre déploiement Lync Server 2013, tous les 4 500 utilisateurs dont la charge doit être simulée, vous devez disposer d’au moins un ordinateur dédié répondant à la configuration matérielle minimale requise suivante :</span><span class="sxs-lookup"><span data-stu-id="751c3-106">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, for every 4,500 users whose load you want to simulate, you’ll need at least one dedicated computer that meets the following minimum hardware requirements:</span></span>

  - <span data-ttu-id="751c3-107">carte réseau 1 Gigabit</span><span class="sxs-lookup"><span data-stu-id="751c3-107">1 gigabit network adapter</span></span>

  - <span data-ttu-id="751c3-108">8 Go de RAM</span><span class="sxs-lookup"><span data-stu-id="751c3-108">8-GB ram</span></span>

  - <span data-ttu-id="751c3-109">2 unités centrales (UC) double cœur</span><span class="sxs-lookup"><span data-stu-id="751c3-109">2 dual-core central processing units (CPUs)</span></span>

</div>

<div>

## <a name="client-software-requirements"></a><span data-ttu-id="751c3-110">Configuration logicielle requise pour le client</span><span class="sxs-lookup"><span data-stu-id="751c3-110">Client Software Requirements</span></span>

<span data-ttu-id="751c3-111">Pour exécuter l’outil de contrainte et de performances de Lync Server 2013 sur votre déploiement Lync Server 2013, les systèmes d’exploitation pris en charge sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="751c3-111">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, the supported operating systems are:</span></span>

  - <span data-ttu-id="751c3-112">Système d’exploitation Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="751c3-112">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="751c3-113">Système d’exploitation Windows Server 2008 (version 64 bits)</span><span class="sxs-lookup"><span data-stu-id="751c3-113">Windows Server 2008 operating system (64-bit edition)</span></span>

<span data-ttu-id="751c3-114">Votre ordinateur client doit répondre à la configuration logicielle requise suivante :</span><span class="sxs-lookup"><span data-stu-id="751c3-114">Your client computer must meet the following software requirements:</span></span>

  - <span data-ttu-id="751c3-115">[Microsoft .NET Framework 4,5](https://go.microsoft.com/fwlink/?linkid=143212) Runtime doit être installé.</span><span class="sxs-lookup"><span data-stu-id="751c3-115">You must have the [Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212) runtime installed.</span></span>

  - <span data-ttu-id="751c3-116">Sur Windows Server 2008/Windows Server 2012, la fonctionnalité expérience utilisateur doit être activée.</span><span class="sxs-lookup"><span data-stu-id="751c3-116">On Windows Server 2008/Windows Server 2012, the Desktop Experience feature must be enabled.</span></span>

  - <span data-ttu-id="751c3-117">Le [package redistribuable de Microsoft Visual C++ 2012](https://go.microsoft.com/fwlink/?linkid=143216) (x64) doit être installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="751c3-117">You must have the [Microsoft Visual C++ 2012 redistributable package](https://go.microsoft.com/fwlink/?linkid=143216) (x64) installed.</span></span>

  - <span data-ttu-id="751c3-118">Un déploiement de Lync Server 2013 entièrement configuré.</span><span class="sxs-lookup"><span data-stu-id="751c3-118">A fully configured Lync Server 2013 deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="751c3-119">Les bibliothèques Microsoft Unified Communications Managed API (UCMA) 4,0 sont incluses dans le package d’installation, de sorte que UCMA n’est pas obligatoire et ne doit pas être installé sur les ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="751c3-119">Microsoft Unified Communications Managed API (UCMA) 4.0 libraries are included in the installation package, so UCMA is not required and should not be installed on client computers.</span></span>



</div>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="751c3-120">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="751c3-120">Configuration Requirements</span></span>

<span data-ttu-id="751c3-121">Les ordinateurs qui exécuteront l’outil de contrainte et de performances de Lync Server 2013 doivent être configurés conformément aux exigences suivantes :</span><span class="sxs-lookup"><span data-stu-id="751c3-121">The computers that will run the Lync Server 2013 Stress and Performance Tool must be configured according to the following requirements:</span></span>

1.  <span data-ttu-id="751c3-122">Vous devez être connecté en tant que membre du groupe de domaine ou du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="751c3-122">You must be logged on as a member of the Domain or Local Admins group.</span></span>

2.  <span data-ttu-id="751c3-123">L’outil stress and performance de Lync Server 2013 (LyncPerfTool. exe) ne peut pas être exécuté sur un ordinateur qui exécute également les composants Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="751c3-123">Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) cannot be run on a computer that is also running Lync Server 2013 components.</span></span>

3.  <span data-ttu-id="751c3-124">Vous devez exécuter l’outil de création d’utilisateurs Lync Server 2013 (UserProvisioningTool. exe) sur le serveur frontal ou sur le serveur Standard Edition où les comptes d’utilisateur doivent résider.</span><span class="sxs-lookup"><span data-stu-id="751c3-124">You must run the Lync Server 2013 User Creation tool (UserProvisioningTool.exe) on the Front End Server or on the Standard Edition server where the user accounts will reside.</span></span> <span data-ttu-id="751c3-125">Lorsque l’outil est exécuté plusieurs fois, chaque utilisateur activé pour les communications unifiées de Microsoft doit disposer d’un numéro de téléphone unique.</span><span class="sxs-lookup"><span data-stu-id="751c3-125">When the tool is run multiple times, each user who is enabled for Microsoft Unified Communications must have a unique phone number.</span></span>

4.  <span data-ttu-id="751c3-126">La taille du fichier d’échange doit être gérée par le système ou au moins 1,5 fois la quantité de RAM sur le système.</span><span class="sxs-lookup"><span data-stu-id="751c3-126">The page file size should be system-managed, or should be at least 1.5 times the amount of RAM on the system.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

