---
title: 'Lync Server 2013 : problèmes liés au test de topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0492f53692230bf02b3b66d91ba7fdf14b01c23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a><span data-ttu-id="10bd1-102">Problèmes liés au test topologique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10bd1-102">Issues with the topology test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10bd1-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="10bd1-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="10bd1-104">À l’instar de l’applet **de contrôle test-CsTopology** , le meilleur analyseur de pratique vous offre la possibilité de vérifier que Lync Server 2013 fonctionne correctement à un niveau global.</span><span class="sxs-lookup"><span data-stu-id="10bd1-104">Like the **Test-CsTopology** cmdlet, Best Practice Analyzer provides a way for you to verify that Lync Server 2013 is functioning correctly at a global level.</span></span> <span data-ttu-id="10bd1-105">Par défaut, l’analyseur de meilleures pratiques, à l’instar de l’applet de contrôle, vérifie l’intégralité de votre infrastructure Lync Server 2013, en vérifiant que les services requis sont en cours d’exécution et que les droits d’utilisateur et les autorisations appropriés ont été définis pour ces services et pour le universel. groupes de sécurité créés lors de l’installation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="10bd1-105">By default, Best Practice Analyzer, like the cmdlet, checks your entire Lync Server 2013 infrastructure, verifying that the required services are running, and that the appropriate user rights and permissions have been set for these services and for the universal security groups created when you install Lync Server 2013.</span></span>

<span data-ttu-id="10bd1-106">En plus de vérifier la validité du serveur Lync, **test-CsTopology** vérifie également la validité d’un service spécifique.</span><span class="sxs-lookup"><span data-stu-id="10bd1-106">In addition to verifying the validity of Lync Server as a whole, **Test-CsTopology** also checks the validity of a specific service.</span></span> <span data-ttu-id="10bd1-107">Pour plus d’informations sur l’utilisation de l’applet de contrôle pour tester des services spécifiques, consultez la rubrique [test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) dans la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="10bd1-107">For details about using the cmdlet to test specific services, see [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="10bd1-108">Utilisez les informations suivantes pour vous aider à résoudre les problèmes liés à votre topologie.</span><span class="sxs-lookup"><span data-stu-id="10bd1-108">Use the following information to help resolve issues with your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="10bd1-109">En fonction de la configuration de votre serveur Edge et des paramètres de réseau de périmètre associés, y compris les paramètres de pare-feu et les autorisations, l’analyseur de meilleures pratiques peut ne pas être en mesure d’accéder aux serveurs Edge et de les analyser.</span><span class="sxs-lookup"><span data-stu-id="10bd1-109">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers.</span></span> <span data-ttu-id="10bd1-110">Si vous incluez des serveurs de périphérie dans votre numérisation et que les rapports indiquent qu’il y a un problème pour accéder aux serveurs Edge, désactivez la case à cocher <STRONG>serveurs de périphérie</STRONG> et relancez la numérisation pour éviter que le problème ne s’affiche dans les rapports.</span><span class="sxs-lookup"><span data-stu-id="10bd1-110">If you include Edge Servers in your scan and the reports indicate that there is an issue accessing Edge Servers, clear the <STRONG>Edge Servers</STRONG> check box and run the scan again to prevent the issue from showing up in reports.</span></span>



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a><span data-ttu-id="10bd1-111">Résoudre les problèmes liés à votre topologie</span><span class="sxs-lookup"><span data-stu-id="10bd1-111">Resolving Issues with Your Topology</span></span>

<span data-ttu-id="10bd1-112">Si le test de topologie a détecté des problèmes avec votre topologie, ces problèmes sont probablement causés par des problèmes qui se sont produits lorsque vous avez publié ou activé votre topologie.</span><span class="sxs-lookup"><span data-stu-id="10bd1-112">If the topology test found issues with your topology, these issues are probably caused by issues that occurred when you published or enabled your topology.</span></span>

<span data-ttu-id="10bd1-113">Lorsque vous apportez des modifications à votre topologie, celles-ci ne s’appliquent que lorsque vous les avez publiées et activées.</span><span class="sxs-lookup"><span data-stu-id="10bd1-113">When you make changes to your topology, the changes take effect only when they have been both published and enabled.</span></span> <span data-ttu-id="10bd1-114">Vous devez utiliser le générateur de topologie pour apporter des changements de topologie.</span><span class="sxs-lookup"><span data-stu-id="10bd1-114">You must use Topology Builder to make topology changes.</span></span> <span data-ttu-id="10bd1-115">Après avoir apporté des modifications, vous pouvez publier et activer ces modifications à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="10bd1-115">After you make changes, you can then publish and enable those changes by using Topology Builder.</span></span>

<span data-ttu-id="10bd1-116">Lorsque vous publiez les modifications, les nouvelles informations (par exemple, un nouveau site ou un nouveau rôle serveur) sont écrites dans le magasin de gestion central.</span><span class="sxs-lookup"><span data-stu-id="10bd1-116">When you publish the changes, the new information (for example, a new site or a new server role) is written to the Central Management store.</span></span> <span data-ttu-id="10bd1-117">Toutefois, ces nouveaux objets (ou les modifications que vous avez apportées) ne rejoignent pas immédiatement votre topologie.</span><span class="sxs-lookup"><span data-stu-id="10bd1-117">However, these new (or the newly modified) objects do not immediately join your topology.</span></span> <span data-ttu-id="10bd1-118">Les objets rejoignent votre topologie uniquement lors de l’activation de la topologie mise à jour.</span><span class="sxs-lookup"><span data-stu-id="10bd1-118">Objects join your topology only when you enable the updated topology.</span></span> <span data-ttu-id="10bd1-119">Si vous sélectionnez l’option publier dans le générateur de topologie, les deux étapes suivantes se produisent : les modifications sont publiées (c’est-à-dire qu’elles sont écrites dans le magasin de gestion central), puis la nouvelle topologie est activée.</span><span class="sxs-lookup"><span data-stu-id="10bd1-119">If you select the Publish option in Topology Builder both of these steps occur: the changes are published (that is, they are written to the Central Management store) and then the new topology is enabled.</span></span>

<span data-ttu-id="10bd1-120">Par défaut, les membres du groupe RTCUniversalServerAdmins sont autorisés à exécuter l’applet de cmdlet **publishe-CsTopology** et l’applet de passe **Enable-CsTopology** .</span><span class="sxs-lookup"><span data-stu-id="10bd1-120">By default, members of the RTCUniversalServerAdmins group are authorized to run the **Publish-CsTopology** cmdlet and the **Enable-CsTopology** cmdlet.</span></span> <span data-ttu-id="10bd1-121">Toutefois, si vous n’avez pas encore délégué d’autorisations d’installation, vous devez être connecté en tant qu’administrateur de domaine pour exécuter la **fonction de publication-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="10bd1-121">However, if setup permissions have not been delegated, you must be logged on as a domain administrator to run **Publish-CsTopology**.</span></span> <span data-ttu-id="10bd1-122">Pour permettre à RTCUniversalServerAdmins de faire réellement appel à l’applet de contrôle **Publisher-CsTopology** , vous devez exécuter l’applet de contrôle **Grant-CsSetupPermission** dans chaque conteneur Active Directory contenant des ordinateurs exécutant des services serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="10bd1-122">To give RTCUniversalServerAdmins the right to actually use the **Publish-CsTopology** cmdlet, you must run the **Grant-CsSetupPermission** cmdlet on every Active Directory container that contains computers running Lync Server services.</span></span> <span data-ttu-id="10bd1-123">Pour permettre à RTCUniversalServerAdmins d’utiliser l’applet de contrôle **Enable-CsTopology** , vous devez exécuter l’applet **de contrôle Set-CsSetupPermission** sur chaque conteneur services de domaine Active Directory qui contient les ordinateurs exécutant Lync Server services.</span><span class="sxs-lookup"><span data-stu-id="10bd1-123">To give RTCUniversalServerAdmins the right to use the **Enable-CsTopology** cmdlet, you must run the **Set-CsSetupPermission** cmdlet against every Active Directory Domain Services container that contains computers running Lync Server services.</span></span> <span data-ttu-id="10bd1-124">Notez que cela s’applique à l’activation et la publication d’une topologie à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="10bd1-124">Note that this applies to enabling and publishing a topology by using Topology Builder.</span></span> <span data-ttu-id="10bd1-125">Si vous n’avez pas d’autorisations déléguées à l’aide de **Set-CsSetupPermission**, seul un administrateur de domaine peut activer et publier une topologie via le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="10bd1-125">If you have not delegated permissions by using **Set-CsSetupPermission**, only a domain administrator can enable and publish a topology through Topology Builder.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

