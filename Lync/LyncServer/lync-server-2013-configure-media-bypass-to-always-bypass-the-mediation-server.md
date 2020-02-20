---
title: 'Lync Server 2013 : configuration de la déviation du trafic multimédia pour toujours contourner le serveur de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76cf44ee24c94b4a243fe84db1f3bbf7a28ba2e2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a><span data-ttu-id="e13c4-102">Configuration de la déviation du trafic multimédia dans Lync Server 2013 pour toujours contourner le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="e13c4-102">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e13c4-103">_**Dernière modification de la rubrique :** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="e13c4-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e13c4-104">Cette rubrique suppose que vous avez déjà configuré le contournement de média pour des connexions de jonction vers un homologue (une passerelle PSTN, un PBX IP ou un contrôleur SBC chez un fournisseur de services de téléphonie Internet) pour un site ou un service spécifique pour lequel vous souhaitez que le contournement de média contourne toujours le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="e13c4-104">This topic assumes that you have already configured media bypass for any trunk connections to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP)) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="e13c4-105">Vous ne pouvez pas configurer le contournement de média pour qu’il contourne toujours le serveur de médiation alors que le contrôle d’admission des appels est activé.</span><span class="sxs-lookup"><span data-stu-id="e13c4-105">You cannot configure media to always bypass the Mediation Server while also enabling call admission control.</span></span> <span data-ttu-id="e13c4-106">Ces paramètres sont incompatibles et sont par conséquent mutuellement exclusifs dans l’interface utilisateur du panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e13c4-106">These settings are incompatible and are therefore mutually exclusive settings in the Lync Server Control Panel user interface.</span></span>



</div>

<span data-ttu-id="e13c4-107">Outre l’activation du contournement de média pour des connexions de jonction individuelles associées à un homologue vers le serveur de médiation, vous devez également configurer les paramètres globaux du contournement de média.</span><span class="sxs-lookup"><span data-stu-id="e13c4-107">In addition to enabling media bypass for individual trunk connections associated with a peer to the Mediation Server, you must also configure global settings for media bypass.</span></span> <span data-ttu-id="e13c4-108">Si vous utilisez les étapes de cette rubrique pour configurer les paramètres globaux pour la déviation du trafic multimédia, il est supposé que vous disposez d’une connexion correcte entre les points de terminaison Lync et tout homologue pour lequel vous avez configuré le contournement de média sur la connexion de jonction.</span><span class="sxs-lookup"><span data-stu-id="e13c4-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Lync endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>

<span data-ttu-id="e13c4-109">Si vous n’avez pas une connectivité correcte entre les points de terminaison Lync Server et tous les homologues du serveur de médiation dont les connexions de jonction respectives ont été activées pour la déviation du trafic multimédia, vous devez configurer les paramètres globaux de contournement de média pour utiliser les informations de site et de région lorsque utilisation de la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="e13c4-109">If you do not have good connectivity between Lync Server endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="e13c4-110">Cela permet de déterminer plus précisément le moment auquel le média contourne le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="e13c4-110">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="e13c4-111">Pour ce faire, suivez les étapes décrites dans [configure Media Bypass Global Settings in Lync Server 2013 pour utiliser les informations de site et de région](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) , et [associer un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) .</span><span class="sxs-lookup"><span data-stu-id="e13c4-111">To do this, use the steps in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) and [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) instead.</span></span>

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="e13c4-112">Pour activer le contournement de média au niveau global pour qu’il contourne toujours le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="e13c4-112">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1.  <span data-ttu-id="e13c4-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e13c4-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e13c4-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e13c4-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="e13c4-115">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="e13c4-115">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="e13c4-116">Double-cliquez sur la configuration **Globale** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e13c4-116">Double-click the **Global** configuration in the list.</span></span>

4.  <span data-ttu-id="e13c4-117">Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contournement de média**.</span><span class="sxs-lookup"><span data-stu-id="e13c4-117">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="e13c4-118">Cliquez sur **Toujours ignorer**.</span><span class="sxs-lookup"><span data-stu-id="e13c4-118">Click **Always bypass**.</span></span>

6.  <span data-ttu-id="e13c4-119">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="e13c4-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e13c4-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e13c4-120">See Also</span></span>


[<span data-ttu-id="e13c4-121">Configurer la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e13c4-121">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="e13c4-122">Options globales de déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e13c4-122">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
[<span data-ttu-id="e13c4-123">Contournement de média et serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e13c4-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  


[<span data-ttu-id="e13c4-124">Planification de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e13c4-124">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

