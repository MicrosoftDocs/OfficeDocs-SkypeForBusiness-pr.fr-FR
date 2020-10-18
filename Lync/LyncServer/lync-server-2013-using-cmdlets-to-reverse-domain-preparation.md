---
title: 'Lync Server 2013 : utilisation d’applets de commande pour inverser la préparation du domaine'
description: 'Lync Server 2013 : utilisation d’applets de commande pour inverser la préparation du domaine.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d26cc97ee934ee959838f38f4e2f52f9bf89566
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580410"
---
# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="ffc85-103">Utilisation d’applets de commande pour inverser la préparation du domaine pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffc85-103">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffc85-104">_**Dernière modification de la rubrique :** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="ffc85-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="ffc85-105">Utilisez l’applet de commande **Disable-CsAdDomain** pour inverser l’étape de préparation d’un domaine.</span><span class="sxs-lookup"><span data-stu-id="ffc85-105">Use the **Disable-CsAdDomain** cmdlet to reverse the domain preparation step.</span></span>

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a><span data-ttu-id="ffc85-106">Pour utiliser des applets de commande afin d’inverser la préparation d’un domaine</span><span class="sxs-lookup"><span data-stu-id="ffc85-106">To use cmdlets to reverse domain preparation</span></span>

1.  <span data-ttu-id="ffc85-107">Ouvrez une session sur un serveur dans le domaine en tant que membre du groupe Administrateurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="ffc85-107">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="ffc85-108">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ffc85-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ffc85-109">Générer</span><span class="sxs-lookup"><span data-stu-id="ffc85-109">Run:</span></span>
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    <span data-ttu-id="ffc85-110">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ffc85-110">For example:</span></span>
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    <span data-ttu-id="ffc85-111">Si le paramètre force est présent, la préparation du domaine est annulée, même si un ou plusieurs serveurs frontaux ou serveurs de conférence A/V dans le domaine sont activés.</span><span class="sxs-lookup"><span data-stu-id="ffc85-111">If the Force parameter is present, domain preparation is rolled back, even if one or more Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span> <span data-ttu-id="ffc85-112">Si le paramètre force n’est pas présent, la préparation du domaine est restaurée si un serveur frontal ou un serveur de conférence A/V dans le domaine est activé.</span><span class="sxs-lookup"><span data-stu-id="ffc85-112">If the Force parameter is not present, domain preparation rollback is terminated if any Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ffc85-113">Le paramètre GlobalSettingsDomainController vous permet d'indiquer où sont stockés les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="ffc85-113">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="ffc85-114">Si vos paramètres sont stockés dans le conteneur système (ce qui est caractéristique des déploiements de mise à niveau qui n'ont pas eu leur paramètre global migré vers le conteneur de configuration), vous définissez un contrôleur de domaine dans la racine de votre forêt Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ffc85-114">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="ffc85-115">Si les paramètres globaux se trouvent dans le conteneur de configuration (ce qui est caractéristique des nouveaux déploiements ou des déploiements de mise à niveau où les paramètres ont été migrés vers le conteneur de configuration, vous définissez tout contrôleur de domaine de la forêt.</span><span class="sxs-lookup"><span data-stu-id="ffc85-115">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="ffc85-116">Si vous ne spécifiez pas ce paramètre, l’applet de commande suppose que les paramètres sont stockés dans le conteneur de configuration et font référence à n’importe quel contrôleur de domaine dans AD &nbsp; DS.</span><span class="sxs-lookup"><span data-stu-id="ffc85-116">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ffc85-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ffc85-117">See Also</span></span>


[<span data-ttu-id="ffc85-118">Exécution de la préparation du domaine pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffc85-118">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)  


[<span data-ttu-id="ffc85-119">Préparation des domaines pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffc85-119">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

