---
title: 'Lync Server 2013: prérequis pour fédérer avec un client Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for federating with a Lync Online customer
ms:assetid: f57d8f8a-2b1e-4186-a74f-1d7c6872bfdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202196(v=OCS.15)
ms:contentKeyID: 48185838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af3db1918e2d347084f1bbdcdf5ea4eb92ae8d91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-federating-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="1bafa-102">Conditions préalables à la Fédération avec un client Lync Online dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1bafa-102">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bafa-103">_**Dernière modification de la rubrique:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="1bafa-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="1bafa-104">Pour fédérer avec un client Lync Online 2010, vous devez déjà avoir effectué le déploiement initial et la configuration de Lync Server 2013 au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1bafa-104">To federate with a Lync Online 2010 customer, you should have already completed initial deployment and configuration of Lync Server 2013 in your organization.</span></span> <span data-ttu-id="1bafa-105">Il s’agit notamment de ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="1bafa-105">This includes the following:</span></span>

  - <span data-ttu-id="1bafa-106">Déploiement d’au moins un serveur Standard Edition Server ou un pool frontal Enterprise Edition au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1bafa-106">Deploying at least one Standard Edition server or one Enterprise Edition Front End pool in your organization.</span></span> <span data-ttu-id="1bafa-107">Pour plus d’informations sur le déploiement de serveurs internes, voir [déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="1bafa-107">For details about deploying internal servers, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="1bafa-108">Activation de comptes d’utilisateurs internes pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1bafa-108">Enabling internal user accounts for Lync Server 2013.</span></span> <span data-ttu-id="1bafa-109">Pour plus d’informations, reportez-vous à désactiver ou réactiver le [compte d’utilisateur Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) dans la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="1bafa-109">For details, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in the Deployment documentation or the Operations documentation.</span></span>

  - <span data-ttu-id="1bafa-110">Déploiement d’au moins un serveur Edge et des autres composants nécessaires à la prise en charge de l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="1bafa-110">Deploying at least one Edge Server and the other components required to support external user access.</span></span> <span data-ttu-id="1bafa-111">Pour plus d’informations, reportez-vous [à gestion de la Fédération et accès externe à Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="1bafa-111">For details, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="1bafa-112">Activation de la prise en charge de la Fédération au sein de votre organisation et configuration de la méthode appropriée pour contrôler l’accès par des domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="1bafa-112">Enabling federation support within your organization and configuring the appropriate method for controlling access by federated domains.</span></span> <span data-ttu-id="1bafa-113">Pour plus d’informations, reportez-vous à [activation ou désactivation de l’accès des utilisateurs distants dans Lync server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) et à la [gestion des fournisseurs fédérés SIP pour votre organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) dans la documentation sur les opérations.</span><span class="sxs-lookup"><span data-stu-id="1bafa-113">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) and [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="1bafa-114">Activation de l’accès des utilisateurs externes pour les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1bafa-114">Enabling external user access for users in your organization.</span></span> <span data-ttu-id="1bafa-115">Pour plus d’informations, voir [affecter une stratégie d’accès d’utilisateur externe à un utilisateur compatible Lync dans Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) et dans la documentation relative au déploiement et aux opérations.</span><span class="sxs-lookup"><span data-stu-id="1bafa-115">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) and in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

