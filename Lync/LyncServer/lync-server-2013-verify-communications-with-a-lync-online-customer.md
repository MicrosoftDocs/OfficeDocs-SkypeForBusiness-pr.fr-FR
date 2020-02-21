---
title: 'Lync Server 2013 : vérifier les communications avec un client Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03aae75cfdb3e179347d14c6f42a90ffe060fad7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="0ca48-102">Vérifier les communications avec un client Lync Online dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ca48-102">Verify communications with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ca48-103">_**Dernière modification de la rubrique :** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="0ca48-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="0ca48-104">Pour permettre aux utilisateurs Lync de votre organisation de communiquer avec les utilisateurs d’un client Microsoft Lync Online 2010, vous devez avoir effectué les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="0ca48-104">To enable Lync users in your organization to communicate with users of a Microsoft Lync Online 2010 customer, you must have completed the following steps:</span></span>

  - <span data-ttu-id="0ca48-105">Respectez tous les éléments prérequis.</span><span class="sxs-lookup"><span data-stu-id="0ca48-105">Met all prerequisites.</span></span> <span data-ttu-id="0ca48-106">Cela inclut le déploiement de vos serveurs internes et de périphérie, l’activation de la prise en charge de la Fédération pour votre organisation et la configuration des comptes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0ca48-106">This includes deploying your internal and edge servers, enabling federation support for your organization, and setting up user accounts.</span></span> <span data-ttu-id="0ca48-107">Pour plus d’informations, reportez-vous à [la rubrique conditions préalables à la Fédération avec un client Lync Online dans Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span><span class="sxs-lookup"><span data-stu-id="0ca48-107">For details, see [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span></span>

  - <span data-ttu-id="0ca48-108">Vous avez configuré la prise en charge de l’accès au domaine dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="0ca48-108">Configured domain access support in your internal deployment.</span></span> <span data-ttu-id="0ca48-109">Cela inclut la création d’une entrée de fournisseur d’hôte et la configuration de votre déploiement pour autoriser l’accès à partir du domaine du client Lync Online.</span><span class="sxs-lookup"><span data-stu-id="0ca48-109">This includes creating a host provider entry and configuring your deployment to allow access from the Lync Online customer’s domain.</span></span> <span data-ttu-id="0ca48-110">Pour plus d’informations, consultez [la rubrique Configurer la prise en charge de la Fédération pour un domaine Lync Online dans Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span><span class="sxs-lookup"><span data-stu-id="0ca48-110">For details, see [Configure federation support for a Lync Online domain in Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span></span>

  - <span data-ttu-id="0ca48-111">Vous avez configuré les comptes de vos utilisateurs de sorte qu’ils prennent en charge la fédération.</span><span class="sxs-lookup"><span data-stu-id="0ca48-111">Configured your user accounts to support federation.</span></span> <span data-ttu-id="0ca48-112">Pour plus d’informations, voir [configurer l’accès utilisateur pour la Fédération avec un client Lync Online dans Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span><span class="sxs-lookup"><span data-stu-id="0ca48-112">For details, see [Configure user access for federation with a Lync Online customer in Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span></span>

<span data-ttu-id="0ca48-113">Une fois que vous avez effectué toutes ces étapes et que l’administrateur du client Lync Online 2010 complète toutes les configurations de leurs services en ligne afin de prendre en charge la Fédération avec votre organisation, vérifiez les communications en testant les communications entre un service interne utilisateur au sein de votre organisation et un utilisateur du client Lync Online.</span><span class="sxs-lookup"><span data-stu-id="0ca48-113">After you complete all of these steps and the administrator of the Lync Online 2010 customer completes all configuration of their online services to support federation with your organization, verify communications by testing communications between an internal user in your organization and a user of the Lync Online customer.</span></span> <span data-ttu-id="0ca48-114">Si la communication échoue, utilisez l’outil de journalisation à partir de votre serveur Edge pour capturer les fichiers journaux et de suivi afin de résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="0ca48-114">If communication is not successful, use the Logging Tool from your Edge Server to capture log and trace files in order to troubleshoot the problem.</span></span> <span data-ttu-id="0ca48-115">Pour plus d’informations sur l’utilisation de l’outil de journalisation, voir [Open Lync Server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="0ca48-115">For details about using the Logging Tool, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span> <span data-ttu-id="0ca48-116">Pour plus d’informations sur l’outil de journalisation, voir la documentation de l’outil de journalisation [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265)Lync Server 2010 dans la bibliothèque TechNet à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="0ca48-116">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

