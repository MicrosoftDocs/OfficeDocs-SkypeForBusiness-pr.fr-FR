---
title: 'Lync Server 2013 : configuration technique requise pour le parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6467f4047754697322780373521cdd47fe1e1ba3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a><span data-ttu-id="d411c-102">Configuration technique requise pour le parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d411c-102">Technical requirements for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d411c-103">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="d411c-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="d411c-104">Cette section décrit les exigences techniques suivantes pour le parcage d’appel :</span><span class="sxs-lookup"><span data-stu-id="d411c-104">This section describes the following technical requirements for Call Park:</span></span>

  - <span data-ttu-id="d411c-105">Configuration matérielle requise</span><span class="sxs-lookup"><span data-stu-id="d411c-105">Hardware requirements</span></span>

  - <span data-ttu-id="d411c-106">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="d411c-106">Software requirements</span></span>

  - <span data-ttu-id="d411c-107">Conditions requises en matière de ports</span><span class="sxs-lookup"><span data-stu-id="d411c-107">Port requirements</span></span>

  - <span data-ttu-id="d411c-108">Conditions requises pour les fichiers audio</span><span class="sxs-lookup"><span data-stu-id="d411c-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="d411c-109">Configuration matérielle requise</span><span class="sxs-lookup"><span data-stu-id="d411c-109">Hardware Requirements</span></span>

<span data-ttu-id="d411c-110">L’application de parcage d’appel présente les mêmes besoins en matière de matériel que les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="d411c-110">The Call Park application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="d411c-111">Pour plus d’informations sur la configuration matérielle requise, voir [Server Hardware Platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="d411c-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="d411c-112">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="d411c-112">Software Requirements</span></span>

<span data-ttu-id="d411c-113">L’application de parcage d’appel présente les mêmes exigences en matière de système d’exploitation et de logiciels que les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="d411c-113">The Call Park application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="d411c-114">Pour plus d’informations sur la configuration logicielle requise, voir [serveur et outils pris en charge par le système d’exploitation dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="d411c-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="d411c-115">Tous les serveurs frontaux et les serveurs Standard Edition Server sur lesquels l’application de parcage d’appel est déployée doivent avoir installé le module d’exécution du format Windows Media pour les serveurs exécutant Windows Server 2008 R2 ou Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 ou Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="d411c-115">All Front End Servers and Standard Edition servers where the Call Park application is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="d411c-116">Pour Windows Server 2008 R2, le runtime du format Windows Media est installé dans le cadre de l’expérience Bureau Windows.</span><span class="sxs-lookup"><span data-stu-id="d411c-116">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="d411c-117">Le runtime du format Windows Media ou Microsoft Media Foundation est requis pour les fichiers audio Windows Media (. WMA) que le parcage d’appel joue pour la musique en attente.</span><span class="sxs-lookup"><span data-stu-id="d411c-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="d411c-118">Configuration requise pour les ports</span><span class="sxs-lookup"><span data-stu-id="d411c-118">Port Requirements</span></span>

<span data-ttu-id="d411c-119">L’application de parcage d’appel utilise le port suivant :</span><span class="sxs-lookup"><span data-stu-id="d411c-119">The Call Park application uses the following port:</span></span>

  - <span data-ttu-id="d411c-120">**Port 5075**   utilisé pour les demandes d’écoute SIP.</span><span class="sxs-lookup"><span data-stu-id="d411c-120">**Port 5075**   Used for SIP listening requests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d411c-121">Ce port est un paramètre par défaut que vous pouvez modifier à l’aide de l’applet de commande <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d411c-121">This port is a default setting that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="d411c-122">Pour plus d’informations sur cette applet de commande, voir la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d411c-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="d411c-123">Conditions requises pour les fichiers audio</span><span class="sxs-lookup"><span data-stu-id="d411c-123">Audio File Requirements</span></span>

<span data-ttu-id="d411c-124">L’application de parcage d’appel ne prend en charge que les fichiers audio Windows Media (. WMA) pour l’attente musicale.</span><span class="sxs-lookup"><span data-stu-id="d411c-124">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="d411c-125">Pour personnaliser les fichiers d’attente musicale, vous pouvez utiliser Microsoft Expression Encoder 4.</span><span class="sxs-lookup"><span data-stu-id="d411c-125">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="d411c-126">Pour télécharger Expression Encoder 4, voir « Expression Encoder 4 » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span><span class="sxs-lookup"><span data-stu-id="d411c-126">To download Expression Encoder 4, see "Expression Encoder 4" at [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span> <span data-ttu-id="d411c-127">Utilisez l’outil pour convertir le fichier au format .wma.</span><span class="sxs-lookup"><span data-stu-id="d411c-127">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="d411c-128">Le format recommandé des fichiers d’attente musicale pour le parcage d’appel est Windows Media Audio 9,44 kHz, 16 bits, Mono, CBR, 32 Kbits/s.</span><span class="sxs-lookup"><span data-stu-id="d411c-128">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d411c-129">Le fichier converti est lu à 16 kHz sur le téléphone, même s’il a été enregistré à 44 kHz.</span><span class="sxs-lookup"><span data-stu-id="d411c-129">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

