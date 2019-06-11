---
title: 'Lync Server 2013: afficher les paramètres du serveur de périphérie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972a5861af803dbaf66843883595c446345ac29a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="24b5e-102">Afficher les paramètres de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24b5e-102">View Edge Server settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24b5e-103">_**Dernière modification de la rubrique:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="24b5e-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="24b5e-104">Les configurations de serveur Edge générales doivent être révisées par rapport aux données de la base de données de gestion de la configuration pour garantir que toutes les modifications étaient étayées par les procédures de contrôle de modification définies.</span><span class="sxs-lookup"><span data-stu-id="24b5e-104">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="24b5e-105">D’autres tests peuvent inclure ceux décrits dans les sections suivantes:</span><span class="sxs-lookup"><span data-stu-id="24b5e-105">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="24b5e-106">Vérifier les listes d’autorisation et de blocage</span><span class="sxs-lookup"><span data-stu-id="24b5e-106">Verify the Allow and block lists</span></span>

<span data-ttu-id="24b5e-107">Vérifiez les listes d’URI SIP «allow» et «Block» pour les domaines fédérés pour déterminer si les espaces de noms répertoriés sont toujours valides.</span><span class="sxs-lookup"><span data-stu-id="24b5e-107">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="24b5e-108">Vous pouvez utiliser Windows PowerShell pour afficher les listes autorisées et bloquées.</span><span class="sxs-lookup"><span data-stu-id="24b5e-108">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="24b5e-109">Pour passer en revue les domaines de la liste des domaines autorisés, exécutez la commande Windows PowerShell suivante:</span><span class="sxs-lookup"><span data-stu-id="24b5e-109">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="24b5e-110">Cette commande renvoie des informations similaires à ce qui suit pour les domaines figurant dans la liste des domaines autorisés:</span><span class="sxs-lookup"><span data-stu-id="24b5e-110">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="24b5e-111">Identité: contoso.com</span><span class="sxs-lookup"><span data-stu-id="24b5e-111">Identity : contoso.com</span></span>

<span data-ttu-id="24b5e-112">Domain: contoso.com</span><span class="sxs-lookup"><span data-stu-id="24b5e-112">Domain : contoso.com</span></span>

<span data-ttu-id="24b5e-113">ProxyFqdn :</span><span class="sxs-lookup"><span data-stu-id="24b5e-113">ProxyFqdn :</span></span>

<span data-ttu-id="24b5e-114">Comment</span><span class="sxs-lookup"><span data-stu-id="24b5e-114">Comment :</span></span>

<span data-ttu-id="24b5e-115">MarkForMonitoring: false</span><span class="sxs-lookup"><span data-stu-id="24b5e-115">MarkForMonitoring : False</span></span>

<span data-ttu-id="24b5e-116">Comment</span><span class="sxs-lookup"><span data-stu-id="24b5e-116">Comment :</span></span>

<span data-ttu-id="24b5e-117">Pour passer en revue les domaines de la liste des domaines bloqués, utilisez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="24b5e-117">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="24b5e-118">En retour, vous recevrez des informations telles que celle-ci pour chaque domaine bloqué:</span><span class="sxs-lookup"><span data-stu-id="24b5e-118">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="24b5e-119">Identité: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="24b5e-119">Identity : tailspintoys.com</span></span>

<span data-ttu-id="24b5e-120">Domain: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="24b5e-120">Domain : tailspintoys.com</span></span>

<span data-ttu-id="24b5e-121">Windows PowerShell vous permet également de vérifier que vous pouvez vous connecter aux domaines dans votre liste de domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="24b5e-121">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="24b5e-122">Par exemple, cette commande vérifie la connexion entre votre serveur Edge (TargetFqdn) et le domaine fédéré contoso.com:</span><span class="sxs-lookup"><span data-stu-id="24b5e-122">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="24b5e-123">Cette commande vérifie la connexion entre votre serveur Edge et tous les domaines qui figurent dans votre liste de domaines autorisés:</span><span class="sxs-lookup"><span data-stu-id="24b5e-123">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="24b5e-124">Vérifier que plusieurs serveurs Edge sont identiques</span><span class="sxs-lookup"><span data-stu-id="24b5e-124">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="24b5e-125">Si plusieurs serveurs Edge sont déployés dans un tableau équilibré en charge, nous vous conseillons de vérifier que tous les serveurs Edge du tableau sont configurés de la même manière.</span><span class="sxs-lookup"><span data-stu-id="24b5e-125">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="24b5e-126">Vous pouvez afficher les paramètres des serveurs de périphérie dans le volet d’informations de l’extension 2013 du serveur Lync pour le composant logiciel enfichable Gestion de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="24b5e-126">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="24b5e-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="24b5e-127">See Also</span></span>


[<span data-ttu-id="24b5e-128">Get-CsAllowedDomain</span><span class="sxs-lookup"><span data-stu-id="24b5e-128">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="24b5e-129">Get-CsBlockedDomain</span><span class="sxs-lookup"><span data-stu-id="24b5e-129">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="24b5e-130">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="24b5e-130">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

