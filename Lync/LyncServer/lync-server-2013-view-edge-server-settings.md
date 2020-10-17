---
title: 'Lync Server 2013 : afficher les paramètres du serveur Edge'
description: 'Lync Server 2013 : afficher les paramètres du serveur Edge.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4318b8c97f53f267bb79953af504977f6437214d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569680"
---
# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="b602b-103">Afficher les paramètres du serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b602b-103">View Edge Server settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b602b-104">_**Dernière modification de la rubrique :** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="b602b-104">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="b602b-105">Les configurations de serveur Edge général doivent être comparées aux données de la base de données de gestion de la configuration pour garantir que toutes les modifications ont été documentées conformément aux procédures de contrôle des modifications définies.</span><span class="sxs-lookup"><span data-stu-id="b602b-105">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="b602b-106">Les vérifications supplémentaires peuvent inclure celles qui sont décrites dans les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="b602b-106">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="b602b-107">Vérifier les listes verte et rouge</span><span class="sxs-lookup"><span data-stu-id="b602b-107">Verify the Allow and block lists</span></span>

<span data-ttu-id="b602b-108">Vérifiez les listes d’URI SIP « autoriser » et « bloquer » pour les domaines fédérés afin de déterminer si les espaces de noms répertoriés sont toujours valides.</span><span class="sxs-lookup"><span data-stu-id="b602b-108">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="b602b-109">Vous pouvez utiliser Windows PowerShell pour afficher les listes autorisées et bloquées.</span><span class="sxs-lookup"><span data-stu-id="b602b-109">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="b602b-110">Pour passer en revue les domaines de la liste des domaines autorisés, exécutez la commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="b602b-110">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="b602b-111">Cette commande renvoie des informations semblables à celles-ci pour les domaines de la liste des domaines autorisés :</span><span class="sxs-lookup"><span data-stu-id="b602b-111">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="b602b-112">Identity : contoso.com</span><span class="sxs-lookup"><span data-stu-id="b602b-112">Identity : contoso.com</span></span>

<span data-ttu-id="b602b-113">Domaine : contoso.com</span><span class="sxs-lookup"><span data-stu-id="b602b-113">Domain : contoso.com</span></span>

<span data-ttu-id="b602b-114">ProxyFqdn</span><span class="sxs-lookup"><span data-stu-id="b602b-114">ProxyFqdn :</span></span>

<span data-ttu-id="b602b-115">Commentaire</span><span class="sxs-lookup"><span data-stu-id="b602b-115">Comment :</span></span>

<span data-ttu-id="b602b-116">MarkForMonitoring : false</span><span class="sxs-lookup"><span data-stu-id="b602b-116">MarkForMonitoring : False</span></span>

<span data-ttu-id="b602b-117">Commentaire</span><span class="sxs-lookup"><span data-stu-id="b602b-117">Comment :</span></span>

<span data-ttu-id="b602b-118">Pour passer en revue les domaines de la liste des domaines bloqués, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b602b-118">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="b602b-119">En retour, vous recevrez des informations comme celles-ci pour chaque domaine bloqué :</span><span class="sxs-lookup"><span data-stu-id="b602b-119">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="b602b-120">Identity : tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="b602b-120">Identity : tailspintoys.com</span></span>

<span data-ttu-id="b602b-121">Domaine : tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="b602b-121">Domain : tailspintoys.com</span></span>

<span data-ttu-id="b602b-122">Windows PowerShell vous permet également de vérifier que vous pouvez vous connecter aux domaines de votre liste de domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="b602b-122">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="b602b-123">Par exemple, cette commande vérifie la connexion entre votre serveur Edge (TargetFqdn) et le domaine fédéré contoso.com :</span><span class="sxs-lookup"><span data-stu-id="b602b-123">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="b602b-124">Cette commande vérifie la connexion entre votre serveur Edge et tous les domaines figurant dans la liste des domaines autorisés :</span><span class="sxs-lookup"><span data-stu-id="b602b-124">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="b602b-125">Vérifier que plusieurs serveurs Edge sont identiques</span><span class="sxs-lookup"><span data-stu-id="b602b-125">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="b602b-126">Si plusieurs serveurs Edge sont déployés dans un tableau à charge équilibrée, nous vous recommandons de vérifier que tous les serveurs Edge du groupe sont configurés de la même manière.</span><span class="sxs-lookup"><span data-stu-id="b602b-126">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="b602b-127">Vous pouvez afficher les paramètres des serveurs Edge dans le volet d’informations de l’extension Lync Server 2013 pour le composant logiciel enfichable Gestion de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b602b-127">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b602b-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b602b-128">See Also</span></span>


[<span data-ttu-id="b602b-129">Get-CsAllowedDomain</span><span class="sxs-lookup"><span data-stu-id="b602b-129">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="b602b-130">Get-applet csblockeddomain</span><span class="sxs-lookup"><span data-stu-id="b602b-130">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="b602b-131">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="b602b-131">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

