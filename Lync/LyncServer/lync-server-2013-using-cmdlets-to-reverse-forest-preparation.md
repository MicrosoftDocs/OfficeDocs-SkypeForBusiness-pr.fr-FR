---
title: 'Lync Server 2013 : Utilisation des commandes d’applet pour inverser la préparation d’une forêt'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd186fc3b2c6171b49cf3fd4c9e78b8e66b4cc71
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="b7bb8-102">Utilisation des commandes d’applet pour inverser la préparation d’une forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7bb8-102">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7bb8-103">_**Dernière modification de la rubrique:** 2013-06-19_</span><span class="sxs-lookup"><span data-stu-id="b7bb8-103">_**Topic Last Modified:** 2013-06-19_</span></span>

<span data-ttu-id="b7bb8-104">Utilisez l’applet de action **Disable-CsAdForest** pour inverser l’étape de préparation de la forêt.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-104">Use the **Disable-CsAdForest** cmdlet to reverse the forest preparation step.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b7bb8-105">Si vous exécutez l’applet de contrôle <STRONG>Disable-CsAdForest</STRONG> dans un environnement dans lequel vous avez également une version antérieure de Lync Server déployée, les paramètres globaux de la version précédente sont également supprimés.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-105">If you run the <STRONG>Disable-CsAdForest</STRONG> cmdlet in an environment where you also have a previous version of Lync Server deployed, the global settings for the previous version will also be deleted.</span></span>



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a><span data-ttu-id="b7bb8-106">Pour utiliser des applets de cmdlet pour inverser la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="b7bb8-106">To use cmdlets to reverse forest preparation</span></span>

1.  <span data-ttu-id="b7bb8-107">Ouvrez une session sur un ordinateur qui est joint à un domaine en tant que membre du groupe Domain Admins dans le domaine racine de la forêt.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-107">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="b7bb8-108">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b7bb8-109">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="b7bb8-109">Run:</span></span>
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    <span data-ttu-id="b7bb8-110">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b7bb8-110">For example:</span></span>
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    <span data-ttu-id="b7bb8-111">Le paramètre Force spécifie si l’exécution de la tâche doit être forcée.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-111">The Force parameter specifies whether to force running the task.</span></span> <span data-ttu-id="b7bb8-112">Si ce paramètre n’est pas présent, la commande ne s’exécute pas s’il n’y a pas encore de domaine dans la forêt pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-112">If this parameter is not present, the command will not run if even one domain in the forest is still prepared for Lync Server 2013.</span></span> <span data-ttu-id="b7bb8-113">Si le paramètre force est spécifié, l’action se poursuit indépendamment de l’état des autres domaines dans la forêt.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-113">If the Force parameter is specified, the action will continue regardless of the state of other domains in the forest.</span></span>
    
    <span data-ttu-id="b7bb8-114">Si vous ne spécifiez pas le paramètre GroupDomain, la valeur par défaut est le domaine local.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-114">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b7bb8-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b7bb8-115">See Also</span></span>


[<span data-ttu-id="b7bb8-116">Exécution de la préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7bb8-116">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)  


[<span data-ttu-id="b7bb8-117">Préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7bb8-117">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

