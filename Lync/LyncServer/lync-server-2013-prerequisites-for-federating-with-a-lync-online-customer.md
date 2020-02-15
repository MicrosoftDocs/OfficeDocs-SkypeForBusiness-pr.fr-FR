---
title: 'Lync Server 2013 : conditions préalables pour la Fédération avec un client Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for federating with a Lync Online customer
ms:assetid: f57d8f8a-2b1e-4186-a74f-1d7c6872bfdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202196(v=OCS.15)
ms:contentKeyID: 48185838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71ad28107f31bf2593952ae8356ac2c9af2b4bc6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-federating-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="fc99f-102">Conditions préalables à la Fédération avec un client Lync Online dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc99f-102">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc99f-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="fc99f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="fc99f-104">Pour fédérer avec un client Lync Online 2010, vous devez avoir déjà effectué le déploiement et la configuration initiaux de Lync Server 2013 au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fc99f-104">To federate with a Lync Online 2010 customer, you should have already completed initial deployment and configuration of Lync Server 2013 in your organization.</span></span> <span data-ttu-id="fc99f-105">Les voici :</span><span class="sxs-lookup"><span data-stu-id="fc99f-105">This includes the following:</span></span>

  - <span data-ttu-id="fc99f-106">Le déploiement d’au moins un serveur Standard Edition Server ou d’un pool frontal Enterprise Edition dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fc99f-106">Deploying at least one Standard Edition server or one Enterprise Edition Front End pool in your organization.</span></span> <span data-ttu-id="fc99f-107">Pour plus d’informations sur le déploiement des serveurs internes, voir [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="fc99f-107">For details about deploying internal servers, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="fc99f-108">Activation des comptes d’utilisateur internes pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fc99f-108">Enabling internal user accounts for Lync Server 2013.</span></span> <span data-ttu-id="fc99f-109">Pour plus d’informations, reportez-vous à la rubrique désactiver ou réactiver le [compte d’utilisateur pour Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) dans la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="fc99f-109">For details, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in the Deployment documentation or the Operations documentation.</span></span>

  - <span data-ttu-id="fc99f-110">Le déploiement d’au moins un serveur Edge et des autres composants requis pour prendre en charge l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="fc99f-110">Deploying at least one Edge Server and the other components required to support external user access.</span></span> <span data-ttu-id="fc99f-111">Pour plus d’informations, consultez la rubrique gestion de la [Fédération et de l’accès externe à Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="fc99f-111">For details, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="fc99f-112">Activation de la prise en charge de la Fédération au sein de votre organisation et configuration de la méthode appropriée pour contrôler l’accès par les domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="fc99f-112">Enabling federation support within your organization and configuring the appropriate method for controlling access by federated domains.</span></span> <span data-ttu-id="fc99f-113">Pour plus d’informations, reportez-vous à la rubrique [activation ou désactivation de l’accès des utilisateurs distants dans Lync server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) et [gestion des fournisseurs fédérés SIP pour votre organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="fc99f-113">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) and [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="fc99f-114">Activation de l’accès des utilisateurs externes pour les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fc99f-114">Enabling external user access for users in your organization.</span></span> <span data-ttu-id="fc99f-115">Pour plus d’informations, reportez-vous à la rubrique [attribuer une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) et dans la documentation sur le déploiement ou les opérations.</span><span class="sxs-lookup"><span data-stu-id="fc99f-115">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) and in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

