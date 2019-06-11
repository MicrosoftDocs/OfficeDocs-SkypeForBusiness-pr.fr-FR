---
title: 'Lync Server 2013: spécification des applications clientes qui peuvent être utilisées pour la connexion à Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Specifying the client applications that can be used to log on to Lync Server 2013
ms:assetid: d256a581-9a48-4d1a-82cc-2e1f520d7d2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182591(v=OCS.15)
ms:contentKeyID: 48185450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42f1135349c7caab0f8e3fe2e428a1bad59466ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013"></a><span data-ttu-id="b8cbb-102">Spécification des applications clientes qui peuvent être utilisées pour la connexion à Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8cbb-102">Specifying the client applications that can be used to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8cbb-103">_**Dernière modification de la rubrique:** 2012-12-11_</span><span class="sxs-lookup"><span data-stu-id="b8cbb-103">_**Topic Last Modified:** 2012-12-11_</span></span>

<span data-ttu-id="b8cbb-104">Lync Server 2013 vous permet de spécifier la version des clients qui sont pris en charge dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="b8cbb-104">Lync Server 2013 enables you to specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="b8cbb-105">L’utilisation de stratégies de version de client peut vous aider à réduire les coûts associés à la prise en charge de plusieurs versions de client.</span><span class="sxs-lookup"><span data-stu-id="b8cbb-105">Using client version policies can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="b8cbb-106">Cela permet également d’améliorer l’utilisation globale de l’utilisateur, car lorsque les versions précédentes et ultérieures de clients interagissent, les fonctionnalités disponibles peuvent être limitées par la version antérieure du client.</span><span class="sxs-lookup"><span data-stu-id="b8cbb-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span>

<span data-ttu-id="b8cbb-107">Il existe trois composants du contrôle de version du client:</span><span class="sxs-lookup"><span data-stu-id="b8cbb-107">There are three components of client version control:</span></span>

  - <span data-ttu-id="b8cbb-108">Les paramètres de configuration de la version du client permettent d’activer ou de désactiver le contrôle de version du client, globalement ou pour des sites spécifiques.</span><span class="sxs-lookup"><span data-stu-id="b8cbb-108">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span>

  - <span data-ttu-id="b8cbb-109">Les stratégies de version de client permettent d’affecter globalement un ensemble de règles ou à un site, un pool ou un groupe d’utilisateurs particulier.</span><span class="sxs-lookup"><span data-stu-id="b8cbb-109">Client version policies are used to assign a set of rules globally, or to a particular site, pool, or group of users.</span></span>

  - <span data-ttu-id="b8cbb-110">Les règles de stratégie de version de client constituent une stratégie de version de client et sont utilisées pour définir les actions qui doivent être effectuées lorsque les utilisateurs essaient de se connecter avec des clients et des versions client spécifiques.</span><span class="sxs-lookup"><span data-stu-id="b8cbb-110">Client version policy rules make up a client version policy, and are used to define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8cbb-111">Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifiques, les utilisateurs anonymes ne sont affectés que par les stratégies globales.</span><span class="sxs-lookup"><span data-stu-id="b8cbb-111">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b8cbb-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="b8cbb-112">In This Section</span></span>

  - [<span data-ttu-id="b8cbb-113">Paramètres de configuration de la version du client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8cbb-113">Client version configuration settings in Lync Server 2013</span></span>](lync-server-2013-client-version-configuration-settings.md)

  - [<span data-ttu-id="b8cbb-114">Stratégies de version de client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8cbb-114">Client version policies in Lync Server 2013</span></span>](lync-server-2013-client-version-policies.md)

  - [<span data-ttu-id="b8cbb-115">Règles de version de client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8cbb-115">Client version rules in Lync Server 2013</span></span>](lync-server-2013-client-version-rules.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b8cbb-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b8cbb-116">See Also</span></span>


[<span data-ttu-id="b8cbb-117">Gestion des appareils, des téléphones et des applications client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8cbb-117">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

