---
title: 'Lync Server 2013 : création ou modification d’une stratégie de version de client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a941908c30a338c12f6c0a7731ade2f1e411dc38
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="96feb-102">Création ou modification d’une nouvelle stratégie de version du client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96feb-102">Create or modify a new client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96feb-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="96feb-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="96feb-104">Vous pouvez utiliser les stratégies de version du client pour spécifier les versions des clients prises en charge dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="96feb-104">You can use client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="96feb-105">L’utilisation du contrôle de version du client permet de réduire les coûts associés à la prise en charge de plusieurs versions du client.</span><span class="sxs-lookup"><span data-stu-id="96feb-105">Using client versioning can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="96feb-106">Elle peut également améliorer l’expérience globale de l’utilisateur, car lorsque des versions antérieures et ultérieures de clients interagissent, les fonctionnalités disponibles peuvent être limitées par la version antérieure du client.</span><span class="sxs-lookup"><span data-stu-id="96feb-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span> <span data-ttu-id="96feb-107">Vous pouvez créer ou modifier des stratégies de version des clients à partir du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="96feb-107">You can create or modify client version policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="96feb-108">Pour créer ou modifier des stratégies de version des clients à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="96feb-108">To create or modify client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="96feb-109">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="96feb-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="96feb-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96feb-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="96feb-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="96feb-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="96feb-112">Dans la barre de navigation de gauche, cliquez sur **Clients**.</span><span class="sxs-lookup"><span data-stu-id="96feb-112">In the left navigation bar, click **Clients**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="96feb-113">L’onglet <STRONG>Stratégie de version du client</STRONG> est sélectionné par défaut.</span><span class="sxs-lookup"><span data-stu-id="96feb-113">The <STRONG>Client Version Policy</STRONG> tab is selected by default.</span></span>

    
    </div>

4.  <span data-ttu-id="96feb-114">Sur la page **stratégie de version du client** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="96feb-114">On the **Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="96feb-115">Pour créer une stratégie de version de client, cliquez sur **nouveau**, sélectionnez **stratégie de site**, **stratégie de pool**ou **stratégie utilisateur**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="96feb-115">To create a client version policy, click **New**, select **Site policy**, **Pool policy**, or **User policy**, and then click **OK**.</span></span>
    
      - <span data-ttu-id="96feb-116">Pour modifier la stratégie globale ou une autre stratégie de version de client existante, sélectionnez la stratégie, cliquez sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="96feb-116">To modify the global policy or another existing client version policy, select the policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="96feb-117">Sur la page **modifier la stratégie de version du client** , créez ou modifiez des règles comme décrit dans [créer ou modifier une règle de stratégie de version des clients dans Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span><span class="sxs-lookup"><span data-stu-id="96feb-117">On the **Edit Client Version Policy** page, create or modify rules as described in [Create or modify a new client version policy rule in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="96feb-118">Création ou modification des stratégies de version des clients à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96feb-118">Creating or Modifying Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="96feb-119">Vous pouvez créer des stratégies de version du client à l’aide de la cmdlet **New-CsClientVersionPolicy** et les modifier à l’aide de la cmdlet **Set-CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="96feb-119">You can create client version policies by using the **New-CsClientVersionPolicy** cmdlet, and modify them by using the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="96feb-120">Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96feb-120">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="96feb-121">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="96feb-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a><span data-ttu-id="96feb-122">Pour créer une stratégie de version de client étendue site</span><span class="sxs-lookup"><span data-stu-id="96feb-122">To create a new site-scoped client version policy</span></span>

  - <span data-ttu-id="96feb-123">La commande suivante crée une stratégie de version de client appliquée au site Redmond.</span><span class="sxs-lookup"><span data-stu-id="96feb-123">The following command creates a new client version policy applied to the Redmond site.</span></span> <span data-ttu-id="96feb-124">Étant donné qu’aucun paramètre supplémentaire n’est spécifié, la nouvelle stratégie utilisera les paramètres de version du client par défaut.</span><span class="sxs-lookup"><span data-stu-id="96feb-124">Because no additional parameters are specified, the new policy will use the default client version settings.</span></span>
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a><span data-ttu-id="96feb-125">Pour créer une stratégie de version de client par utilisateur</span><span class="sxs-lookup"><span data-stu-id="96feb-125">To create a new per-user client version policy</span></span>

  - <span data-ttu-id="96feb-126">Pour créer une stratégie par utilisateur, utilisez une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="96feb-126">To create a per-user policy, use a command similar to this:</span></span>
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

<span data-ttu-id="96feb-127">Pour plus d’informations, reportez-vous aux rubriques d’aide pour la cmdlet [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) et la cmdlet [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) .</span><span class="sxs-lookup"><span data-stu-id="96feb-127">For details, see the Help topics for the [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) cmdlet and the [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

