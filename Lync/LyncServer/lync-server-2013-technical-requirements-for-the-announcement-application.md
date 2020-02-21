---
title: 'Lync Server 2013 : configuration technique requise pour l’application d’annonce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8687c5b9c5f422994817910eec640cc795798d18
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="f89d7-102">Configuration technique requise pour l’application d’annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f89d7-102">Technical requirements for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f89d7-103">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="f89d7-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="f89d7-104">Cette section décrit les exigences techniques suivantes pour l’application d’annonce :</span><span class="sxs-lookup"><span data-stu-id="f89d7-104">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="f89d7-105">Configuration matérielle requise</span><span class="sxs-lookup"><span data-stu-id="f89d7-105">Hardware requirements</span></span>

  - <span data-ttu-id="f89d7-106">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="f89d7-106">Software requirements</span></span>

  - <span data-ttu-id="f89d7-107">Conditions requises en matière de ports</span><span class="sxs-lookup"><span data-stu-id="f89d7-107">Port requirements</span></span>

  - <span data-ttu-id="f89d7-108">Conditions requises pour les fichiers audio</span><span class="sxs-lookup"><span data-stu-id="f89d7-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="f89d7-109">Configuration matérielle requise</span><span class="sxs-lookup"><span data-stu-id="f89d7-109">Hardware Requirements</span></span>

<span data-ttu-id="f89d7-110">L’application d’annonce a les mêmes besoins en matière de matériel que les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="f89d7-110">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="f89d7-111">Pour plus d’informations sur la configuration matérielle requise, voir [Server Hardware Platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="f89d7-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="f89d7-112">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="f89d7-112">Software Requirements</span></span>

<span data-ttu-id="f89d7-113">L’application d’annonce présente les mêmes exigences en matière de système d’exploitation et de logiciels que les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="f89d7-113">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="f89d7-114">Pour plus d’informations sur la configuration logicielle requise, voir [serveur et outils pris en charge par le système d’exploitation dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="f89d7-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="f89d7-115">Windows Media Format Runtime doit être installé sur tous les serveurs frontaux ou les serveurs Standard Edition qui exécutent l’application d’annonce pour les serveurs exécutant Windows Server 2008 R2 ou Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 ou Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="f89d7-115">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="f89d7-116">Pour Windows Server 2008 R2, le runtime du format Windows Media est installé dans le cadre de l’expérience Bureau Windows.</span><span class="sxs-lookup"><span data-stu-id="f89d7-116">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="f89d7-117">Le module d’exécution du format Windows Media ou Microsoft Media Foundation est requis pour les fichiers audio Windows Media (. WMA) que l’application d’annonce joue pour les annonces et la musique.</span><span class="sxs-lookup"><span data-stu-id="f89d7-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="f89d7-118">Configuration requise pour les ports</span><span class="sxs-lookup"><span data-stu-id="f89d7-118">Port Requirements</span></span>

<span data-ttu-id="f89d7-119">L’application d’annonce utilise le port suivant :</span><span class="sxs-lookup"><span data-stu-id="f89d7-119">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="f89d7-120">**Port 5071**   utilisé pour les demandes d’écoute SIP</span><span class="sxs-lookup"><span data-stu-id="f89d7-120">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f89d7-121">Ce port est le paramètre par défaut, que vous pouvez modifier en utilisant la cmdlet <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f89d7-121">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="f89d7-122">Pour plus d’informations sur cette applet de commande, voir la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f89d7-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="f89d7-123">Conditions requises pour les fichiers audio</span><span class="sxs-lookup"><span data-stu-id="f89d7-123">Audio File Requirements</span></span>

<span data-ttu-id="f89d7-124">L’application annonce prend en charge le format de fichier Wave (. wav) et le format de fichier audio Windows Media (. WMA) pour la musique et les annonces.</span><span class="sxs-lookup"><span data-stu-id="f89d7-124">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="f89d7-125">Les exigences en matière de fichiers audio pour l’application d’annonce sont les mêmes que pour l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="f89d7-125">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="f89d7-126">Pour plus d’informations, voir [Technical Requirements for Response Group dans Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="f89d7-126">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

