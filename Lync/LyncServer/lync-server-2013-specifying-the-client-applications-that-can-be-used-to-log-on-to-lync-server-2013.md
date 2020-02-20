---
title: 'Lync Server 2013 : spécification des applications clientes qui peuvent être utilisées pour se connecter à Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying the client applications that can be used to log on to Lync Server 2013
ms:assetid: d256a581-9a48-4d1a-82cc-2e1f520d7d2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182591(v=OCS.15)
ms:contentKeyID: 48185450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5167a2f8b4c9d82be979d7699c621cd3cb7a5ab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013"></a><span data-ttu-id="52f32-102">Spécification des applications clientes qui peuvent être utilisées pour se connecter à Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52f32-102">Specifying the client applications that can be used to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52f32-103">_**Dernière modification de la rubrique :** 2012-12-11_</span><span class="sxs-lookup"><span data-stu-id="52f32-103">_**Topic Last Modified:** 2012-12-11_</span></span>

<span data-ttu-id="52f32-104">Lync Server 2013 vous permet de spécifier la version des clients pris en charge dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="52f32-104">Lync Server 2013 enables you to specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="52f32-105">L’utilisation des stratégies de version du client permet de réduire les coûts associés à la prise en charge de plusieurs versions du client.</span><span class="sxs-lookup"><span data-stu-id="52f32-105">Using client version policies can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="52f32-106">Elle peut également améliorer l’expérience globale de l’utilisateur, car lorsque des versions antérieures et ultérieures de clients interagissent, les fonctionnalités disponibles peuvent être limitées par la version antérieure du client.</span><span class="sxs-lookup"><span data-stu-id="52f32-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span>

<span data-ttu-id="52f32-107">Il existe trois composants de contrôle de version des clients :</span><span class="sxs-lookup"><span data-stu-id="52f32-107">There are three components of client version control:</span></span>

  - <span data-ttu-id="52f32-108">Les paramètres de configuration de la version du client permettent d’activer ou de désactiver le contrôle de version du client, soit globalement, soit pour des sites particuliers.</span><span class="sxs-lookup"><span data-stu-id="52f32-108">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span>

  - <span data-ttu-id="52f32-109">Les stratégies de version du client sont utilisées pour affecter un ensemble de règles globalement, ou pour un site, un pool ou un groupe d’utilisateurs particulier.</span><span class="sxs-lookup"><span data-stu-id="52f32-109">Client version policies are used to assign a set of rules globally, or to a particular site, pool, or group of users.</span></span>

  - <span data-ttu-id="52f32-110">Les règles de stratégie de version des clients constituent une stratégie de version de client et sont utilisées pour définir les actions à effectuer lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques.</span><span class="sxs-lookup"><span data-stu-id="52f32-110">Client version policy rules make up a client version policy, and are used to define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="52f32-111">Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifiques, les utilisateurs anonymes sont uniquement affectés par les stratégies globales.</span><span class="sxs-lookup"><span data-stu-id="52f32-111">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="52f32-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="52f32-112">In This Section</span></span>

  - [<span data-ttu-id="52f32-113">Paramètres de configuration de la version du client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52f32-113">Client version configuration settings in Lync Server 2013</span></span>](lync-server-2013-client-version-configuration-settings.md)

  - [<span data-ttu-id="52f32-114">Stratégies de version du client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52f32-114">Client version policies in Lync Server 2013</span></span>](lync-server-2013-client-version-policies.md)

  - [<span data-ttu-id="52f32-115">Règles de version du client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52f32-115">Client version rules in Lync Server 2013</span></span>](lync-server-2013-client-version-rules.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="52f32-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="52f32-116">See Also</span></span>


[<span data-ttu-id="52f32-117">Gestion des appareils, des téléphones et des applications clientes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52f32-117">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

