---
title: 'Lync Server 2013 : configuration des versions du client prises en charge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34d74de1ae5e25c372e51783d8321ebc8699eaef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a><span data-ttu-id="e4fa8-102">Configuration des versions de client prises en charge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4fa8-102">Configuring supported client versions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4fa8-103">_**Dernière modification de la rubrique :** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="e4fa8-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="e4fa8-104">Dans Lync Server 2013, vous pouvez configurer des stratégies de version du client pour spécifier les versions des clients prises en charge dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="e4fa8-104">In Lync Server 2013, you can set up client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="e4fa8-105">En outre, vous pouvez utiliser la configuration de version du client globale pour spécifier une action par défaut pour les clients qui n’ont pas encore de stratégie de version définie et, par conséquent, ne sont pas explicitement prises en charge ou restreintes.</span><span class="sxs-lookup"><span data-stu-id="e4fa8-105">Additionally, you can use the global client version configuration to specify a default action for clients that do not already have a version policy defined and, therefore, are not explicitly supported or restricted.</span></span>

<span data-ttu-id="e4fa8-106">Vous pouvez également utiliser des stratégies de version du client pour gérer les mises à jour du client.</span><span class="sxs-lookup"><span data-stu-id="e4fa8-106">You can also use client version policies to manage client updates.</span></span> <span data-ttu-id="e4fa8-107">Lorsque vous définissez une stratégie de version de client et utilisez les options **autoriser et mettre à niveau** et **bloquer et mettre à niveau**, les clients recevront des logiciels mis à jour à partir du service de mise à jour de Windows Server (si vous utilisez ce service) ou à partir de Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="e4fa8-107">When you set a client version policy and use the options **Allow and upgrade** and **Block and upgrade**, clients will receive updated software from the Windows Server Update Service (if you are using this service) or from Microsoft Update.</span></span>

<div>

## <a name="client-version-policy-settings"></a><span data-ttu-id="e4fa8-108">Paramètres de la stratégie de version de client</span><span class="sxs-lookup"><span data-stu-id="e4fa8-108">Client Version Policy Settings</span></span>

<span data-ttu-id="e4fa8-109">La stratégie de version de client par défaut exige que tous les clients exécutent Lync.</span><span class="sxs-lookup"><span data-stu-id="e4fa8-109">The default client version policy requires that all clients run Lync.</span></span> <span data-ttu-id="e4fa8-110">Si les clients de votre environnement exécutent des versions antérieures de Communicator, il se peut que vous deviez reconfigurer les règles de version du client pour empêcher les clients et les appareils d’être bloqués ou mis à jour de manière inattendue lors de la connexion à Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4fa8-110">If clients in your environment are running earlier versions of Communicator, you may need to reconfigure the Client Version rules to prevent clients and devices from being unexpectedly blocked or updated when connecting to Lync Server 2013.</span></span> <span data-ttu-id="e4fa8-111">Vous pouvez modifier la règle par défaut ou la remplacer en ajoutant une règle supérieure dans la liste des stratégies de version de client.</span><span class="sxs-lookup"><span data-stu-id="e4fa8-111">You can modify the default rule, or you can add a rule higher in the Client Version Policy list to override the default rule.</span></span> <span data-ttu-id="e4fa8-112">De plus, à mesure que des mises à jour cumulatives sont publiées, vous devez configurer la stratégie de version de client pour demander les dernières mises à jour.</span><span class="sxs-lookup"><span data-stu-id="e4fa8-112">Additionally, as Cumulative Updates (CUs) are released, you should configure the Client Version Policy to require the latest updates.</span></span> <span data-ttu-id="e4fa8-113">Pour plus d’informations, reportez-vous à la rubrique [spécification des applications clientes pouvant être utilisées pour se connecter à Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="e4fa8-113">For details, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

