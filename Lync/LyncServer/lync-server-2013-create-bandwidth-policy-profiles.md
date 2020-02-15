---
title: 'Lync Server 2013 : créer des profils de stratégie de bande passante'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea1e44f7c8c0d81757d6d10a63194de7c0d12c08
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="7fb2b-102">Créer des profils de stratégie de bande passante dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fb2b-102">Create bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fb2b-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="7fb2b-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="7fb2b-p101">Des *stratégies de bande passante* définissent des restrictions d’utilisation de la bande passante pour des modes audio et vidéo en temps réel. Des stratégies de bande passante sont appliquées à des *profils de stratégie de bande passante* qui peuvent être appliqués à des sites réseau multiples pour le contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="7fb2b-p101">*Bandwidth policies* define limitations on bandwidth usage for real-time audio and video modalities. Bandwidth policies are applied to *bandwidth policy profiles*, which can be applied to multiple network sites for call admission control.</span></span>

<span data-ttu-id="7fb2b-106">Pour obtenir des instructions sur les limites de bande passante que vous devez définir dans votre déploiement CAC, voir [définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="7fb2b-106">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Defining your requirements for call admission control in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="7fb2b-107">Pour plus d’informations sur l’utilisation des stratégies de bande passante et des profils de stratégie, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="7fb2b-107">For details about working with bandwidth policies and policy profiles, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="7fb2b-108">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="7fb2b-108">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="7fb2b-109">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="7fb2b-109">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="7fb2b-110">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="7fb2b-110">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="7fb2b-111">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="7fb2b-111">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

<span data-ttu-id="7fb2b-112">Les stratégies d’exemple créées lors de la procédure suivante définissent des limites pour l’ensemble du trafic audio, les sessions audio individuelles, l’ensemble du trafic vidéo et les sessions vidéo individuelles.</span><span class="sxs-lookup"><span data-stu-id="7fb2b-112">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions.</span></span> <span data-ttu-id="7fb2b-113">Par exemple, le profil\_de stratégie de bande passante de 5 Mo définit les limites suivantes :</span><span class="sxs-lookup"><span data-stu-id="7fb2b-113">For example, the 5Mb\_Link bandwidth policy profile sets the following limits:</span></span>

  - <span data-ttu-id="7fb2b-114">Limite audio : 2 000 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="7fb2b-114">Audio Limit: 2,000 kbps</span></span>

  - <span data-ttu-id="7fb2b-115">Limite de session audio : 200 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="7fb2b-115">Audio Session Limit: 200 kbps</span></span>

  - <span data-ttu-id="7fb2b-116">Limite vidéo : 1 400 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="7fb2b-116">Video Limit: 1,400 kbps</span></span>

  - <span data-ttu-id="7fb2b-117">Limite de session vidéo : 700 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="7fb2b-117">Video Session Limit: 700 kbps</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="7fb2b-p103">La valeur minimum de limite de session audio est 40 Kbits/s La valeur minimum de limite de session vidéo est 100 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="7fb2b-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span>



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a><span data-ttu-id="7fb2b-120">Pour créer des profils de stratégie de bande passante à l’aide de Management Shell</span><span class="sxs-lookup"><span data-stu-id="7fb2b-120">To create bandwidth policy profiles by using Management Shell</span></span>

1.  <span data-ttu-id="7fb2b-121">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7fb2b-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7fb2b-p104">Pour chaque profil de stratégie de bande passante que vous voulez créer, exécutez l’applet de commande New-CsNetworkBandwidthPolicyProfile. Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="7fb2b-p104">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet. For example, run:</span></span>
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
       ```

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a><span data-ttu-id="7fb2b-124">Pour créer des profils de stratégie de bande passante à l’aide du Panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="7fb2b-124">To create bandwidth policy profiles by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7fb2b-125">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7fb2b-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7fb2b-126">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7fb2b-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="7fb2b-127">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="7fb2b-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="7fb2b-128">Cliquez sur le bouton de navigation **Profil de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="7fb2b-128">Click the **Policy Profile** navigation button.</span></span>

4.  <span data-ttu-id="7fb2b-129">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="7fb2b-129">Click **New**.</span></span>

5.  <span data-ttu-id="7fb2b-130">A la page **Nouveau profil de stratégie**, cliquez sur **Nom**, puis tapez un nom pour le profil de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="7fb2b-130">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>

6.  <span data-ttu-id="7fb2b-131">Cliquez sur **Limite audio**, puis tapez le nombre maximum de Kbits/s à autoriser pour toutes les sessions audio combinées.</span><span class="sxs-lookup"><span data-stu-id="7fb2b-131">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>

7.  <span data-ttu-id="7fb2b-132">Cliquez sur **Limite de session audio**, puis tapez le nombre maximum de Kbits/s à autoriser pour chaque session audio individuelle.</span><span class="sxs-lookup"><span data-stu-id="7fb2b-132">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>

8.  <span data-ttu-id="7fb2b-133">Cliquez sur **Limite vidéo**, puis tapez le nombre maximum de Kbits/s à autoriser pour toutes les sessions vidéo combinées.</span><span class="sxs-lookup"><span data-stu-id="7fb2b-133">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>

9.  <span data-ttu-id="7fb2b-134">Cliquez sur **Limite de session vidéo**, puis tapez le nombre maximum de Kbits/s à autoriser pour chaque session vidéo individuelle.</span><span class="sxs-lookup"><span data-stu-id="7fb2b-134">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>

10. <span data-ttu-id="7fb2b-135">En option, cliquez sur **Description**, puis tapez des informations supplémentaires pour décrire ce profil de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="7fb2b-135">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>

11. <span data-ttu-id="7fb2b-136">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="7fb2b-136">Click **Commit**.</span></span>

12. <span data-ttu-id="7fb2b-137">Pour finir de créer des profils de stratégie de bande passante pour votre topologie, répétez les étapes 4 à 11 avec des paramètres pour d’autres profils de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="7fb2b-137">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

