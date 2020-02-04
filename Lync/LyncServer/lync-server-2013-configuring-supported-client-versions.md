---
title: 'Lync Server 2013 : configuration des versions clientes prises en charge'
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
ms.openlocfilehash: 9a262cab2145013d83cdae573d98b5db17e0e890
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a><span data-ttu-id="37ebf-102">Configuration des versions clientes prises en charge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37ebf-102">Configuring supported client versions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37ebf-103">_**Dernière modification de la rubrique :** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="37ebf-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="37ebf-104">Dans Lync Server 2013, vous pouvez configurer des stratégies de version de client pour spécifier les versions des clients qui sont prises en charge dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="37ebf-104">In Lync Server 2013, you can set up client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="37ebf-105">De plus, vous pouvez utiliser la configuration de la version du client global pour spécifier une action par défaut pour les clients qui ne disposent pas encore d’une stratégie de version définie et ne sont donc pas explicitement pris en charge ou limités.</span><span class="sxs-lookup"><span data-stu-id="37ebf-105">Additionally, you can use the global client version configuration to specify a default action for clients that do not already have a version policy defined and, therefore, are not explicitly supported or restricted.</span></span>

<span data-ttu-id="37ebf-106">Vous pouvez également utiliser des stratégies de version de client pour gérer les mises à jour du client.</span><span class="sxs-lookup"><span data-stu-id="37ebf-106">You can also use client version policies to manage client updates.</span></span> <span data-ttu-id="37ebf-107">Lorsque vous définissez une stratégie de version de client et que vous utilisez les options **autoriser et** mettre à niveau et **bloquer et mettre à niveau**, les clients reçoivent le logiciel mis à jour du service Windows Server Update (si vous utilisez ce service) ou de Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="37ebf-107">When you set a client version policy and use the options **Allow and upgrade** and **Block and upgrade**, clients will receive updated software from the Windows Server Update Service (if you are using this service) or from Microsoft Update.</span></span>

<div>

## <a name="client-version-policy-settings"></a><span data-ttu-id="37ebf-108">Paramètres de la stratégie de version du client</span><span class="sxs-lookup"><span data-stu-id="37ebf-108">Client Version Policy Settings</span></span>

<span data-ttu-id="37ebf-109">La stratégie de version de client par défaut exige que tous les clients exécutent Lync.</span><span class="sxs-lookup"><span data-stu-id="37ebf-109">The default client version policy requires that all clients run Lync.</span></span> <span data-ttu-id="37ebf-110">Si les clients de votre environnement exécutent des versions antérieures de Communicator, il est possible que vous deviez reconfigurer les règles de version de client pour empêcher le blocage ou la mise à jour inattendue des clients et des appareils lors de la connexion à Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37ebf-110">If clients in your environment are running earlier versions of Communicator, you may need to reconfigure the Client Version rules to prevent clients and devices from being unexpectedly blocked or updated when connecting to Lync Server 2013.</span></span> <span data-ttu-id="37ebf-111">Vous pouvez modifier la règle par défaut ou ajouter une règle plus haut dans la liste des stratégies de version du client pour remplacer la règle par défaut.</span><span class="sxs-lookup"><span data-stu-id="37ebf-111">You can modify the default rule, or you can add a rule higher in the Client Version Policy list to override the default rule.</span></span> <span data-ttu-id="37ebf-112">Par ailleurs, dans la mesure où les mises à jour cumulatives (CUs) sont disponibles, vous devez configurer la stratégie de version du client pour exiger les mises à jour les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="37ebf-112">Additionally, as Cumulative Updates (CUs) are released, you should configure the Client Version Policy to require the latest updates.</span></span> <span data-ttu-id="37ebf-113">Pour plus d’informations, reportez-vous [à la rubrique Spécification des applications clientes qui peuvent être utilisées pour vous connecter à Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) dans la documentation sur les opérations.</span><span class="sxs-lookup"><span data-stu-id="37ebf-113">For details, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

