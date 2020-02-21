---
title: 'Lync Server 2013 : utilisation d’applets de commande pour inverser la préparation de la forêt'
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
ms.openlocfilehash: 4d39992255bfe6f93d9f41380b4f6b5fb9af1f5b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="545f7-102">Utilisation d’applets de commande pour inverser la préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="545f7-102">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="545f7-103">_**Dernière modification de la rubrique :** 2013-06-19_</span><span class="sxs-lookup"><span data-stu-id="545f7-103">_**Topic Last Modified:** 2013-06-19_</span></span>

<span data-ttu-id="545f7-104">Utilisez la cmdlet **Disable-CsAdForest** pour inverser la procédure de préparation d’une forêt.</span><span class="sxs-lookup"><span data-stu-id="545f7-104">Use the **Disable-CsAdForest** cmdlet to reverse the forest preparation step.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="545f7-105">Si vous exécutez l’applet de commande <STRONG>Disable-CsAdForest</STRONG> dans un environnement où vous avez également une version antérieure de Lync Server déployée, les paramètres globaux de la version précédente seront également supprimés.</span><span class="sxs-lookup"><span data-stu-id="545f7-105">If you run the <STRONG>Disable-CsAdForest</STRONG> cmdlet in an environment where you also have a previous version of Lync Server deployed, the global settings for the previous version will also be deleted.</span></span>



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a><span data-ttu-id="545f7-106">Pour utiliser des cmdlets afin d’inverser la préparation d’une forêt</span><span class="sxs-lookup"><span data-stu-id="545f7-106">To use cmdlets to reverse forest preparation</span></span>

1.  <span data-ttu-id="545f7-107">Ouvrez une session sur un ordinateur qui est associé à un domaine en tant que membre du groupe Administrateurs du domaine dans le domaine racine de la forêt.</span><span class="sxs-lookup"><span data-stu-id="545f7-107">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="545f7-108">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="545f7-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="545f7-109">Générer</span><span class="sxs-lookup"><span data-stu-id="545f7-109">Run:</span></span>
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    <span data-ttu-id="545f7-110">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="545f7-110">For example:</span></span>
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    <span data-ttu-id="545f7-111">Le paramètre Force spécifie s’il faut forcer l’exécution de la tâche.</span><span class="sxs-lookup"><span data-stu-id="545f7-111">The Force parameter specifies whether to force running the task.</span></span> <span data-ttu-id="545f7-112">Si ce paramètre n’est pas présent, la commande ne s’exécutera pas si un seul domaine de la forêt est toujours préparé pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="545f7-112">If this parameter is not present, the command will not run if even one domain in the forest is still prepared for Lync Server 2013.</span></span> <span data-ttu-id="545f7-113">Si le paramètre Force est spécifié, l’action se poursuit quel que soit l’état des autres domaines dans la forêt.</span><span class="sxs-lookup"><span data-stu-id="545f7-113">If the Force parameter is specified, the action will continue regardless of the state of other domains in the forest.</span></span>
    
    <span data-ttu-id="545f7-114">Si vous omettez le paramètre GroupDomain, le domaine local est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="545f7-114">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="545f7-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="545f7-115">See Also</span></span>


[<span data-ttu-id="545f7-116">Exécution de la préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="545f7-116">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)  


[<span data-ttu-id="545f7-117">Préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="545f7-117">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

