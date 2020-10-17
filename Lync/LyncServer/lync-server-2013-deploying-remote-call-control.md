---
title: 'Lync Server 2013 : déploiement du contrôle d’appel distant'
description: 'Lync Server 2013 : déploiement du contrôle d’appel distant.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying remote call control
ms:assetid: 763037f7-7a2a-49ae-acc3-9781b0bff7e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558664(v=OCS.15)
ms:contentKeyID: 48184536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cc5e79f3ee44c354baf435585d304574d6a980c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566080"
---
# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="a61ac-103">Déploiement du contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a61ac-103">Deploying remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a61ac-104">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="a61ac-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="a61ac-105">Cette section vous guide tout au long du processus de déploiement de la fonctionnalité de contrôle d’appel distant sur les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a61ac-105">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a61ac-106">Même si les fonctionnalités de contrôle d’appel distant sont accessibles aux utilisateurs distants lorsqu’ils se trouvent à l’extérieur du pare-feu de votre organisation, les détails relatifs au déploiement de scénarios d’accès externe ne rentrent pas dans le cadre de cette documentation.</span><span class="sxs-lookup"><span data-stu-id="a61ac-106">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="a61ac-107">Pour plus d’informations sur le déploiement de l’accès des utilisateurs externes, voir <A href="lync-server-2013-deploying-external-user-access.md">Deploying External User Access in Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="a61ac-107">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a61ac-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="a61ac-108">In This Section</span></span>

  - [<span data-ttu-id="a61ac-109">Configuration de Lync Server 2013 pour un routage vers une passerelle SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="a61ac-109">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="a61ac-110">Configurer un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a61ac-110">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="a61ac-111">Configurer une entrée d’application approuvée pour le contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a61ac-111">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="a61ac-112">[Définition d’une adresse IP de passerelle SIP/CSTA dans Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (uniquement si la passerelle est configurée pour utiliser le protocole TCP)</span><span class="sxs-lookup"><span data-stu-id="a61ac-112">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="a61ac-113">Activation des utilisateurs Lync pour le contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a61ac-113">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="a61ac-114">Contrôle d’appel distant et normalisation des numéros de téléphone dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a61ac-114">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="a61ac-115">[Suppression d’un hôte autorisé hérité dans Lync Server 2013 (facultatif)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (uniquement si vous migrez les utilisateurs précédemment activés pour le contrôle d’appel distant)</span><span class="sxs-lookup"><span data-stu-id="a61ac-115">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="a61ac-116">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="a61ac-116">Related Sections</span></span>

[<span data-ttu-id="a61ac-117">Planification du contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a61ac-117">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

