---
title: 'Lync Server 2013 : déploiement du plug-in Lync VDI'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync VDI plug-in
ms:assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204683(v=OCS.15)
ms:contentKeyID: 48183449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 889bcb5579d3c65578f5634ac73e75cf1640e0f1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="11c37-102">Déploiement du plug-in Lync VDI dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11c37-102">Deploying the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11c37-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="11c37-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="11c37-104">Le client Lync 2013 prend en charge les fonctionnalités audio et vidéo dans un environnement VDI (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="11c37-104">The Lync 2013 client supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="11c37-105">Un utilisateur peut connecter un périphérique audio ou vidéo (par exemple, un casque ou une caméra) à l’ordinateur local (par exemple, un client léger ou un ordinateur réaffecté).</span><span class="sxs-lookup"><span data-stu-id="11c37-105">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="11c37-106">L’utilisateur peut se connecter à la machine virtuelle, se connecter au client Lync 2013 qui est en cours d’exécution sur l’ordinateur virtuel et participer à des communications audio et vidéo en temps réel, comme si le client était en cours d’exécution localement.</span><span class="sxs-lookup"><span data-stu-id="11c37-106">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communications as though the client is running locally.</span></span>

<span data-ttu-id="11c37-107">Le plug-in Lync VDI est une application autonome qui s’installe sur l’ordinateur local et permet d’utiliser des périphériques audio et vidéo locaux avec le client Lync 2013 qui s’exécute sur l’ordinateur virtuel.</span><span class="sxs-lookup"><span data-stu-id="11c37-107">The Lync VDI Plug-in is a stand-alone application that installs on the local computer and allows the use of local audio and video devices with the Lync 2013 client running on the virtual machine.</span></span> <span data-ttu-id="11c37-108">Le plug-in ne nécessite pas l’installation de Lync sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="11c37-108">The plug-in does not require Lync to be installed on the local computer.</span></span> <span data-ttu-id="11c37-109">Une fois que l’utilisateur se connecte au client Lync 2013 qui s’exécute sur l’ordinateur virtuel, Lync invite l’utilisateur à entrer de nouveau ses informations d’identification pour établir une connexion avec le plug-in Lync VDI en cours d’exécution sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="11c37-109">After the user signs in to the Lync 2013 client that is running on the virtual machine, Lync prompts the user to re-enter his or her credentials to establish a connection with the Lync VDI Plug-in that is running on the local computer.</span></span> <span data-ttu-id="11c37-110">Une fois cette connexion établie, l’utilisateur est prêt à passer et à recevoir des appels audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="11c37-110">After this connection is established, the user is ready to make and receive audio and video calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="11c37-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="11c37-111">In This Section</span></span>

  - [<span data-ttu-id="11c37-112">Conditions préalables du plug-in Lync VDI dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11c37-112">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>](lync-server-2013-lync-vdi-plug-in-prerequisites.md)

  - [<span data-ttu-id="11c37-113">Préparation de votre environnement Lync Server 2013 pour VDI</span><span class="sxs-lookup"><span data-stu-id="11c37-113">Preparing your Lync Server 2013 environment for VDI</span></span>](lync-server-2013-preparing-your-environment-for-vdi.md)

  - [<span data-ttu-id="11c37-114">Connexion et utilisation de Lync 2013 sur l’ordinateur virtuel</span><span class="sxs-lookup"><span data-stu-id="11c37-114">Signing in and using Lync 2013 on the virtual machine</span></span>](lync-server-2013-signing-in-and-using-lync-2013-on-the-virtual-machine.md)

  - [<span data-ttu-id="11c37-115">Résolution des problèmes liés au plug-in Lync VDI dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11c37-115">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-the-lync-vdi-plug-in.md)

  - [<span data-ttu-id="11c37-116">Technologies de virtualisation prises en charge et limitations connues dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11c37-116">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>](lync-server-2013-supported-virtualization-technologies-and-known-limitations.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

