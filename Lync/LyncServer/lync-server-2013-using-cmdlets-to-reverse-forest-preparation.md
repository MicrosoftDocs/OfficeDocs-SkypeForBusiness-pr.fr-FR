---
title: 'Lync Server 2013 : utilisation d’applets de commande pour inverser la préparation de la forêt'
description: 'Lync Server 2013 : utilisation d’applets de commande pour inverser la préparation de la forêt.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acac87bdaeb7e730f93401fa62ea2678a713bb8f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580390"
---
# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="ce4a3-103">Utilisation d’applets de commande pour inverser la préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce4a3-103">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce4a3-104">_**Dernière modification de la rubrique :** 2013-06-19_</span><span class="sxs-lookup"><span data-stu-id="ce4a3-104">_**Topic Last Modified:** 2013-06-19_</span></span>

<span data-ttu-id="ce4a3-105">Utilisez la cmdlet **Disable-CsAdForest** pour inverser la procédure de préparation d’une forêt.</span><span class="sxs-lookup"><span data-stu-id="ce4a3-105">Use the **Disable-CsAdForest** cmdlet to reverse the forest preparation step.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="ce4a3-106">Si vous exécutez l’applet de commande <STRONG>Disable-CsAdForest</STRONG> dans un environnement où vous avez également une version antérieure de Lync Server déployée, les paramètres globaux de la version précédente seront également supprimés.</span><span class="sxs-lookup"><span data-stu-id="ce4a3-106">If you run the <STRONG>Disable-CsAdForest</STRONG> cmdlet in an environment where you also have a previous version of Lync Server deployed, the global settings for the previous version will also be deleted.</span></span>



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a><span data-ttu-id="ce4a3-107">Pour utiliser des cmdlets afin d’inverser la préparation d’une forêt</span><span class="sxs-lookup"><span data-stu-id="ce4a3-107">To use cmdlets to reverse forest preparation</span></span>

1.  <span data-ttu-id="ce4a3-108">Ouvrez une session sur un ordinateur qui est associé à un domaine en tant que membre du groupe Administrateurs du domaine dans le domaine racine de la forêt.</span><span class="sxs-lookup"><span data-stu-id="ce4a3-108">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="ce4a3-109">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ce4a3-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ce4a3-110">Générer</span><span class="sxs-lookup"><span data-stu-id="ce4a3-110">Run:</span></span>
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    <span data-ttu-id="ce4a3-111">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ce4a3-111">For example:</span></span>
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    <span data-ttu-id="ce4a3-112">Le paramètre Force spécifie s’il faut forcer l’exécution de la tâche.</span><span class="sxs-lookup"><span data-stu-id="ce4a3-112">The Force parameter specifies whether to force running the task.</span></span> <span data-ttu-id="ce4a3-113">Si ce paramètre n’est pas présent, la commande ne s’exécutera pas si un seul domaine de la forêt est toujours préparé pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce4a3-113">If this parameter is not present, the command will not run if even one domain in the forest is still prepared for Lync Server 2013.</span></span> <span data-ttu-id="ce4a3-114">Si le paramètre Force est spécifié, l’action se poursuit quel que soit l’état des autres domaines dans la forêt.</span><span class="sxs-lookup"><span data-stu-id="ce4a3-114">If the Force parameter is specified, the action will continue regardless of the state of other domains in the forest.</span></span>
    
    <span data-ttu-id="ce4a3-115">Si vous omettez le paramètre GroupDomain, le domaine local est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="ce4a3-115">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ce4a3-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ce4a3-116">See Also</span></span>


[<span data-ttu-id="ce4a3-117">Exécution de la préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce4a3-117">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)  


[<span data-ttu-id="ce4a3-118">Préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce4a3-118">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

