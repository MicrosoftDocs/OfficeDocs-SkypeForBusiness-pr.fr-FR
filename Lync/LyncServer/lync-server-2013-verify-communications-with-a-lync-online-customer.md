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
ms.openlocfilehash: f9b20be32ecbc7c3c684009c9c2f928c9dc897cd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="ae663-102">Vérifier les communications avec un client Lync Online dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae663-102">Verify communications with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae663-103">_**Dernière modification de la rubrique :** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="ae663-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="ae663-104">Pour permettre aux utilisateurs de Lync de votre organisation de communiquer avec des utilisateurs d’un client Microsoft Lync Online 2010, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ae663-104">To enable Lync users in your organization to communicate with users of a Microsoft Lync Online 2010 customer, you must have completed the following steps:</span></span>

  - <span data-ttu-id="ae663-105">Rempli toutes les conditions préalables.</span><span class="sxs-lookup"><span data-stu-id="ae663-105">Met all prerequisites.</span></span> <span data-ttu-id="ae663-106">Cela inclut le déploiement de vos serveurs internes et de périphérie, l’activation de la prise en charge de la Fédération pour votre organisation et la configuration des comptes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ae663-106">This includes deploying your internal and edge servers, enabling federation support for your organization, and setting up user accounts.</span></span> <span data-ttu-id="ae663-107">Pour plus d’informations, reportez-vous [à la configuration requise pour fédérer avec un client Lync Online dans Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span><span class="sxs-lookup"><span data-stu-id="ae663-107">For details, see [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span></span>

  - <span data-ttu-id="ae663-108">Configuration de la prise en charge de l’accès au domaine dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ae663-108">Configured domain access support in your internal deployment.</span></span> <span data-ttu-id="ae663-109">Cela inclut la création d’une entrée de fournisseur d’hébergement et la configuration de votre déploiement pour autoriser l’accès à partir du domaine du client Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ae663-109">This includes creating a host provider entry and configuring your deployment to allow access from the Lync Online customer’s domain.</span></span> <span data-ttu-id="ae663-110">Pour plus d’informations, voir [configurer la prise en charge de la Fédération pour un domaine Lync Online dans Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span><span class="sxs-lookup"><span data-stu-id="ae663-110">For details, see [Configure federation support for a Lync Online domain in Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span></span>

  - <span data-ttu-id="ae663-111">Configuré vos comptes d’utilisateurs pour la prise en charge de la Fédération ;</span><span class="sxs-lookup"><span data-stu-id="ae663-111">Configured your user accounts to support federation.</span></span> <span data-ttu-id="ae663-112">Pour plus d’informations, voir [configurer l’accès utilisateur pour la Fédération avec un client Lync Online dans Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span><span class="sxs-lookup"><span data-stu-id="ae663-112">For details, see [Configure user access for federation with a Lync Online customer in Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span></span>

<span data-ttu-id="ae663-113">Après avoir effectué toutes les étapes décrites dans le tableau ci-dessous, vous devez effectuer toutes les étapes de configuration de ses services en ligne pour 2010 la prise en charge de la Fédération avec votre organisation. utilisateur de votre organisation et utilisateur du client Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ae663-113">After you complete all of these steps and the administrator of the Lync Online 2010 customer completes all configuration of their online services to support federation with your organization, verify communications by testing communications between an internal user in your organization and a user of the Lync Online customer.</span></span> <span data-ttu-id="ae663-114">Si la communication échoue, utilisez l’outil de journalisation de votre serveur de périphérie pour capturer les fichiers de journaux et de suivi afin de résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="ae663-114">If communication is not successful, use the Logging Tool from your Edge Server to capture log and trace files in order to troubleshoot the problem.</span></span> <span data-ttu-id="ae663-115">Pour plus d’informations sur l’utilisation de l’outil journalisation, voir [ouvrir les outils d’administration de Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md) dans la documentation sur les opérations.</span><span class="sxs-lookup"><span data-stu-id="ae663-115">For details about using the Logging Tool, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span> <span data-ttu-id="ae663-116">Pour plus d’informations sur l’outil de journalisation, voir la documentation de l’outil de journalisation [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)Lync Server 2010 dans la bibliothèque TechNet à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="ae663-116">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

