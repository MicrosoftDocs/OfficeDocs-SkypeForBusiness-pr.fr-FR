---
title: 'Lync Server 2013 : afficher les paramètres du serveur Edge'
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
ms.openlocfilehash: e978e28ea2c9d64a842c40237f1e5943c30d0a41
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="20f17-102">Afficher les paramètres du serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20f17-102">View Edge Server settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20f17-103">_**Dernière modification de la rubrique :** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="20f17-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="20f17-104">Les configurations de serveur Edge général doivent être comparées aux données de la base de données de gestion de la configuration pour garantir que toutes les modifications ont été documentées conformément aux procédures de contrôle des modifications définies.</span><span class="sxs-lookup"><span data-stu-id="20f17-104">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="20f17-105">Les vérifications supplémentaires peuvent inclure celles qui sont décrites dans les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="20f17-105">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="20f17-106">Vérifier les listes verte et rouge</span><span class="sxs-lookup"><span data-stu-id="20f17-106">Verify the Allow and block lists</span></span>

<span data-ttu-id="20f17-107">Vérifiez les listes d’URI SIP « autoriser » et « bloquer » pour les domaines fédérés afin de déterminer si les espaces de noms répertoriés sont toujours valides.</span><span class="sxs-lookup"><span data-stu-id="20f17-107">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="20f17-108">Vous pouvez utiliser Windows PowerShell pour afficher les listes autorisées et bloquées.</span><span class="sxs-lookup"><span data-stu-id="20f17-108">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="20f17-109">Pour passer en revue les domaines de la liste des domaines autorisés, exécutez la commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="20f17-109">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="20f17-110">Cette commande renvoie des informations semblables à celles-ci pour les domaines de la liste des domaines autorisés :</span><span class="sxs-lookup"><span data-stu-id="20f17-110">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="20f17-111">Identity : contoso.com</span><span class="sxs-lookup"><span data-stu-id="20f17-111">Identity : contoso.com</span></span>

<span data-ttu-id="20f17-112">Domaine : contoso.com</span><span class="sxs-lookup"><span data-stu-id="20f17-112">Domain : contoso.com</span></span>

<span data-ttu-id="20f17-113">ProxyFqdn</span><span class="sxs-lookup"><span data-stu-id="20f17-113">ProxyFqdn :</span></span>

<span data-ttu-id="20f17-114">Commentaire</span><span class="sxs-lookup"><span data-stu-id="20f17-114">Comment :</span></span>

<span data-ttu-id="20f17-115">MarkForMonitoring : false</span><span class="sxs-lookup"><span data-stu-id="20f17-115">MarkForMonitoring : False</span></span>

<span data-ttu-id="20f17-116">Commentaire</span><span class="sxs-lookup"><span data-stu-id="20f17-116">Comment :</span></span>

<span data-ttu-id="20f17-117">Pour passer en revue les domaines de la liste des domaines bloqués, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="20f17-117">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="20f17-118">En retour, vous recevrez des informations comme celles-ci pour chaque domaine bloqué :</span><span class="sxs-lookup"><span data-stu-id="20f17-118">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="20f17-119">Identity : tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="20f17-119">Identity : tailspintoys.com</span></span>

<span data-ttu-id="20f17-120">Domaine : tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="20f17-120">Domain : tailspintoys.com</span></span>

<span data-ttu-id="20f17-121">Windows PowerShell vous permet également de vérifier que vous pouvez vous connecter aux domaines de votre liste de domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="20f17-121">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="20f17-122">Par exemple, cette commande vérifie la connexion entre votre serveur Edge (TargetFqdn) et le domaine fédéré contoso.com :</span><span class="sxs-lookup"><span data-stu-id="20f17-122">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="20f17-123">Cette commande vérifie la connexion entre votre serveur Edge et tous les domaines figurant dans la liste des domaines autorisés :</span><span class="sxs-lookup"><span data-stu-id="20f17-123">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="20f17-124">Vérifier que plusieurs serveurs Edge sont identiques</span><span class="sxs-lookup"><span data-stu-id="20f17-124">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="20f17-125">Si plusieurs serveurs Edge sont déployés dans un tableau à charge équilibrée, nous vous recommandons de vérifier que tous les serveurs Edge du groupe sont configurés de la même manière.</span><span class="sxs-lookup"><span data-stu-id="20f17-125">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="20f17-126">Vous pouvez afficher les paramètres des serveurs Edge dans le volet d’informations de l’extension Lync Server 2013 pour le composant logiciel enfichable Gestion de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="20f17-126">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="20f17-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="20f17-127">See Also</span></span>


[<span data-ttu-id="20f17-128">Get-CsAllowedDomain</span><span class="sxs-lookup"><span data-stu-id="20f17-128">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="20f17-129">Get-applet csblockeddomain</span><span class="sxs-lookup"><span data-stu-id="20f17-129">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="20f17-130">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="20f17-130">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

