---
title: 'Lync Server 2013: configurer la contournement multimédia pour ignorer toujours le serveur de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aca094110036692c5ac5327b166a3f81e4b769f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a><span data-ttu-id="4bae9-102">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span><span class="sxs-lookup"><span data-stu-id="4bae9-102">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bae9-103">_**Dernière modification de la rubrique:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="4bae9-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4bae9-104">Dans cette rubrique, nous partons du principe que vous avez déjà configuré le contournement multimédia pour n’importe quelle connexion de Trunk vers un homologue (passerelle RTC (réseau téléphonique commuté), un PBX IP ou un contrôleur de bordure de session (SBC) sur un fournisseur de services de téléphonie Internet (ITSP) le service ou le site pour lequel vous souhaitez que le média ignore le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="4bae9-104">This topic assumes that you have already configured media bypass for any trunk connections to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP)) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="4bae9-105">Vous ne pouvez pas configurer le contenu multimédia pour ignorer toujours le serveur de médiation tout en activant également le contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="4bae9-105">You cannot configure media to always bypass the Mediation Server while also enabling call admission control.</span></span> <span data-ttu-id="4bae9-106">Ces paramètres ne sont pas compatibles et sont donc mutuellement exclusifs dans l’interface utilisateur du panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bae9-106">These settings are incompatible and are therefore mutually exclusive settings in the Lync Server Control Panel user interface.</span></span>



</div>

<span data-ttu-id="4bae9-107">Outre l’activation de l’exclusion de médias pour les connexions de Trunk individuelles associées à un homologue au serveur de médiation, vous devez également configurer des paramètres globaux pour le contournement multimédia.</span><span class="sxs-lookup"><span data-stu-id="4bae9-107">In addition to enabling media bypass for individual trunk connections associated with a peer to the Mediation Server, you must also configure global settings for media bypass.</span></span> <span data-ttu-id="4bae9-108">Si vous suivez les étapes décrites dans cette rubrique pour configurer des paramètres globaux pour le contournement du média multimédia, il est supposé que vous disposez d’une bonne connectivité entre les points de terminaison Lync et les homologues pour lesquels vous avez configuré une contournement multimédia sur la connexion Trunk.</span><span class="sxs-lookup"><span data-stu-id="4bae9-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Lync endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>

<span data-ttu-id="4bae9-109">Si vous n’avez pas de bonne connectivité entre les points de terminaison de Lync Server et tous les homologues sur le serveur de médiation pour lesquels une connexion de ligne respective a été activée, vous devez configurer des paramètres globaux de contournement de médias pour utiliser les informations de site et de région lorsque utilisation du contournement de média.</span><span class="sxs-lookup"><span data-stu-id="4bae9-109">If you do not have good connectivity between Lync Server endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="4bae9-110">Cela permet d’augmenter le contrôle lors du contournement du serveur de médiation par le média.</span><span class="sxs-lookup"><span data-stu-id="4bae9-110">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="4bae9-111">Pour cela, suivez les étapes décrites dans [configurer les paramètres globaux de contournement de médias dans Lync server 2013 pour utiliser les informations de site et de région](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) , puis [associez un sous-réseau à un site réseau dans Lync Server 2013 à la](lync-server-2013-associate-a-subnet-with-a-network-site.md) place.</span><span class="sxs-lookup"><span data-stu-id="4bae9-111">To do this, use the steps in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) and [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) instead.</span></span>

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="4bae9-112">Pour activer la déviation du trafic multimédia au niveau global pour qu’il contourne toujours le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="4bae9-112">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1.  <span data-ttu-id="4bae9-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bae9-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4bae9-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4bae9-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="4bae9-115">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="4bae9-115">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="4bae9-116">Double-cliquez sur la configuration **Globale** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="4bae9-116">Double-click the **Global** configuration in the list.</span></span>

4.  <span data-ttu-id="4bae9-117">Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer la déviation du trafic multimédia**.</span><span class="sxs-lookup"><span data-stu-id="4bae9-117">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="4bae9-118">Cliquez sur **Toujours ignorer**.</span><span class="sxs-lookup"><span data-stu-id="4bae9-118">Click **Always bypass**.</span></span>

6.  <span data-ttu-id="4bae9-119">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="4bae9-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4bae9-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4bae9-120">See Also</span></span>


[<span data-ttu-id="4bae9-121">Configuration de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bae9-121">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="4bae9-122">Options de contournement global de médias dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bae9-122">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
[<span data-ttu-id="4bae9-123">Déviation du trafic multimédia et serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bae9-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  


[<span data-ttu-id="4bae9-124">Planification de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bae9-124">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

