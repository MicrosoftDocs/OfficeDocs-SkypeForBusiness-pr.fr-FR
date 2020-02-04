---
title: 'Lync Server 2013 : modifier l’URL des services Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 934e448f48413df2938deab8a0d08389cfad37bd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a><span data-ttu-id="96aa9-102">Changer l’URL de services Web dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96aa9-102">Change the Web Services URL in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96aa9-103">_**Dernière modification de la rubrique :** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="96aa9-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="96aa9-104">Lorsque vous configurez vos pools frontaux et les serveurs Standard Edition, vous avez la possibilité de configurer un nom de domaine complet (FQDN) externe et des ports associés.</span><span class="sxs-lookup"><span data-stu-id="96aa9-104">When you set up your Front End pools and Standard Edition servers, you have the option to configure an external Web farm fully qualified domain name (FQDN) and associated ports.</span></span> <span data-ttu-id="96aa9-105">Si vous n’avez pas configuré cette URL lors de l’exécution de l’Assistant Déploiement de Lync Server, vous devez configurer vos paramètres manuellement.</span><span class="sxs-lookup"><span data-stu-id="96aa9-105">If you did not configure this URL when you ran the Lync Server Deployment Wizard, you need to manually configure these settings.</span></span> <span data-ttu-id="96aa9-106">En règle générale, un administrateur n’a pas besoin de modifier ces paramètres, car il s’agit des ports recommandés et par défaut.</span><span class="sxs-lookup"><span data-stu-id="96aa9-106">An administrator typically does not need to modify these settings, as these are the recommended and default ports.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="96aa9-107">La capture d’écran suivante a été prise lors de la configuration d’un serveur Standard Edition Server, de sorte que l’option de remplacement de nom de domaine complet est désactivée.</span><span class="sxs-lookup"><span data-stu-id="96aa9-107">The following screen shot was taken while configuring a Standard Edition server, so the Override FQDN option is disabled.</span></span> <span data-ttu-id="96aa9-108">Cette option est activée lors de la configuration d’un serveur Enterprise Edition dans un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="96aa9-108">That option is enabled when configuring an Enterprise Edition server in a Front End pool.</span></span>



</div>

<span data-ttu-id="96aa9-109">![Modifier les paramètres du pool de services Web](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Modifier les paramètres du pool de services Web")</span><span class="sxs-lookup"><span data-stu-id="96aa9-109">![Edit Web Services Pool Settings](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Edit Web Services Pool Settings")</span></span>

<div>

## <a name="to-configure-web-services"></a><span data-ttu-id="96aa9-110">Pour configurer les services Web</span><span class="sxs-lookup"><span data-stu-id="96aa9-110">To configure web services</span></span>

1.  <span data-ttu-id="96aa9-111">Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="96aa9-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="96aa9-112">Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="96aa9-112">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="96aa9-113">Dans le générateur de topologie, dans l’arborescence de la console sous **serveurs front end Standard Edition**, **regroupements front**end et **pools d’annuaires**, sélectionnez le nom du pool.</span><span class="sxs-lookup"><span data-stu-id="96aa9-113">In Topology Builder, in the console tree under **Standard Edition Front End Servers**, **Enterprise Edition Front End pools**, and **Directory pools**, select the pool name.</span></span> <span data-ttu-id="96aa9-114">Cliquez avec le bouton droit sur le nom, cliquez sur **modifier les propriétés**, puis cliquez sur **services Web**.</span><span class="sxs-lookup"><span data-stu-id="96aa9-114">Right-click the name, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="96aa9-115">Ajoutez ou modifiez le **nom de domaine complet des services Web externes**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="96aa9-115">Add or edit the **External Web Services FQDN**, and then click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="96aa9-116">Si vous avez plusieurs pools front-end ou serveur frontal, le nom de domaine complet des services Web externes doit être unique.</span><span class="sxs-lookup"><span data-stu-id="96aa9-116">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="96aa9-117">Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que <STRONG>pool01.contoso.com</STRONG>, vous ne pouvez pas utiliser <STRONG>pool01.contoso.com</STRONG> pour un autre pool frontal ou serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="96aa9-117">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="96aa9-118">Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour n’importe quel directeur ou pool de réalisateur doit être unique à partir d’un autre directeur ou pool de directeurs, ainsi que sur n’importe quel pool frontal ou serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="96aa9-118">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="96aa9-119">Vérifiez que les ports d’écoute et de publication sont configurés correctement pour votre environnement.</span><span class="sxs-lookup"><span data-stu-id="96aa9-119">Verify the listening and published ports are configured correctly for your environment.</span></span>

6.  <span data-ttu-id="96aa9-120">Répétez ces étapes pour tous les serveurs Standard Edition, les listes frontales et les pools de directeurs de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="96aa9-120">Repeat these steps for all Standard Edition servers, Front End Pools, and Director pools in your environment.</span></span>

7.  <span data-ttu-id="96aa9-121">Dans l’arborescence de la console, cliquez sur **Lync Server 2013**, puis, dans le volet **actions** , cliquez sur nouvelle **topologie de publication**.</span><span class="sxs-lookup"><span data-stu-id="96aa9-121">In the console tree, click **Lync Server 2013**, and then, in the **Actions** pane, click **Publish Topology**.</span></span>

<span data-ttu-id="96aa9-122">Quelques exigences sont à prendre en compte lorsque vous configurez les ports d’écoute et de publication :</span><span class="sxs-lookup"><span data-stu-id="96aa9-122">There are a few requirements you should be aware of when configuring the Listening and Publishing ports:</span></span>

  - <span data-ttu-id="96aa9-123">Le port Listening indiqué est celui qui est configuré pour Internet Information Server (IIS) sur chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="96aa9-123">The listening ports shown are the ports that are configured for Internet Information Server (IIS) on each Front End Server.</span></span>

  - <span data-ttu-id="96aa9-124">Les ports d’écoute interne et externe doivent être différents pour les services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="96aa9-124">The internal and external listening ports must be different for IIS.</span></span> <span data-ttu-id="96aa9-125">Pour les ports d’écoute externes, ces derniers sont généralement les mêmes, car l’un représente l’équilibreur de charge matérielle pour le trafic Web interne et l’autre représente le serveur proxy inverse pour le trafic Web externe.</span><span class="sxs-lookup"><span data-stu-id="96aa9-125">For the external listening ports, these are typically the same because one represents the hardware load balancer for internal web traffic and one represents the reverse proxy server for external web traffic.</span></span>

  - <span data-ttu-id="96aa9-126">Vous pouvez remplacer les services Web internes sur un pool frontal, un réalisateur ou un pool de réalisateurs et définir votre propre nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="96aa9-126">You can override the Internal web services on a Front End pool, Director or a Director pool and define your own FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="96aa9-127">Si vous décidez de remplacer les services Web internes par un nom de domaine complet autonome, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool de directeurs.</span><span class="sxs-lookup"><span data-stu-id="96aa9-127">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

  - <span data-ttu-id="96aa9-128">Vous devez configurer les ports publiés sur le proxy inverse ou le service d’équilibrage de la charge matérielle comme ports d’écoute.</span><span class="sxs-lookup"><span data-stu-id="96aa9-128">The published ports must be configured on the reverse proxy or hardware load balancer as listening ports.</span></span>

  - <span data-ttu-id="96aa9-129">Dans le cas d’une réserve frontale (non illustrée dans l’exemple), le nom de domaine complet (FQDN) du pool SIP interne doit être différent du nom de domaine complet des services Web internes, car le trafic Web est transmis par le biais de l’équilibrage de charge DNS. .</span><span class="sxs-lookup"><span data-stu-id="96aa9-129">For an Front End pool (not shown in the example), the internal SIP pool FQDN must be different from the internal web services FQDN, because web traffic comes through the hardware load balancer and the internal SIP pool traffic travels comes through the DNS load balancer.</span></span> <span data-ttu-id="96aa9-130">Cette obligation doit être remplie.</span><span class="sxs-lookup"><span data-stu-id="96aa9-130">This requirement must be met.</span></span>

  - <span data-ttu-id="96aa9-131">Le déploiement de Lync Server Standard Edition n’a pas besoin ou ne permet pas le remplacement de nom de domaine complet des services Web internes, car ce serveur ne peut pas être équilibré.</span><span class="sxs-lookup"><span data-stu-id="96aa9-131">A Lync Server Standard Edition deployment does not need or allow an internal web services FQDN to be overridden because this server cannot be load balanced.</span></span>

  - <span data-ttu-id="96aa9-132">Si vous disposez d’un outil d’équilibrage de la charge matérielle dans votre environnement que vous utilisez pour le trafic SIP et Web interne, le générateur de topologie ne peut pas faire la distinction.</span><span class="sxs-lookup"><span data-stu-id="96aa9-132">If you have a hardware load balancer in your environment that you use for both internal SIP and web traffic, the Topology Builder cannot make the distinction.</span></span>
    
    <span data-ttu-id="96aa9-133">Les noms de domaine complets de service Web doivent être facilement différenciés les uns des autres. Cela permet de s’assurer que la redirection d’URL pointe vers le serveur approprié.</span><span class="sxs-lookup"><span data-stu-id="96aa9-133">Web service FQDNs should be easily-differentiated from one another; that helps to ensure that URL redirection points clients towards the appropriate server.</span></span> <span data-ttu-id="96aa9-134">Par exemple, si vous avez deux noms de domaine complets, vous pouvez envisager d’attribuer un nom à un meeting.contoso.com et à l’autre conferencing.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="96aa9-134">For example, if you have two FQDNs you might consider naming one meeting.contoso.com and the other conferencing.contoso.com.</span></span> <span data-ttu-id="96aa9-135">Vous risquez de rencontrer des problèmes de redirection si vous avez des noms de domaine complets portant des noms similaires, par exemple meet1.contoso.com et meet2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="96aa9-135">You could potentially run into redirection issues if you have FQDNs with more similar names, such as meet1.contoso.com and meet2.contoso.com.</span></span>

<span data-ttu-id="96aa9-136">Les services Web externes fonctionnent conjointement avec un proxy inverse dans le réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="96aa9-136">The external web services works in conjunction with a reverse proxy in the perimeter network.</span></span> <span data-ttu-id="96aa9-137">Il offre aux clients un accès externe à l’aide de ces services Web.</span><span class="sxs-lookup"><span data-stu-id="96aa9-137">It provides clients external access to by using these web services.</span></span> <span data-ttu-id="96aa9-138">Les noms de domaine complets configurés ici sont envoyés aux clients lorsqu’ils ouvrent une session et permettent de rétablir une connexion HTTPs au proxy inverse lors de la connexion à distance.</span><span class="sxs-lookup"><span data-stu-id="96aa9-138">The FQDNs configured here are sent to clients when they log on, and are used to make an HTTPS connection back to the reverse proxy when connecting remotely.</span></span> <span data-ttu-id="96aa9-139">Le serveur proxy inverse transfère le nom de domaine complet du service Web externe à un équilibreur de charge matériel interne, ou directement au pool.</span><span class="sxs-lookup"><span data-stu-id="96aa9-139">The reverse-proxy server forwards the external web service FQDN to an internal hardware load balancer, or directly to the pool.</span></span> <span data-ttu-id="96aa9-140">Le proxy inverse doit être en mesure de résoudre le nom de domaine complet des services Web externes en adresse IP du serveur Web interne.</span><span class="sxs-lookup"><span data-stu-id="96aa9-140">The reverse proxy must be able to resolve the external web services FQDN to the IP address of the internal Web server.</span></span> <span data-ttu-id="96aa9-141">Le FDQN des services Web externes doit être résolu sur l’Internet public.</span><span class="sxs-lookup"><span data-stu-id="96aa9-141">The external web services FDQN must be resolvable in the public Internet.</span></span>

<span data-ttu-id="96aa9-142">Si votre serveur interne est un serveur Standard Edition Server, le FQDN interne est le FQDN du serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="96aa9-142">If your internal server is a Standard Edition server, the internal FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="96aa9-143">Si votre serveur interne est une réserve frontale, le nom de domaine complet est une adresse IP virtuelle d’équilibrage de charge matérielle qui charge les serveurs de batterie de serveurs Web internes.</span><span class="sxs-lookup"><span data-stu-id="96aa9-143">If your internal server is a Front End pool, the FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="96aa9-144">Un équilibrage de charge matérielle est requis dans un pool frontal doté de plus d’un serveur Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="96aa9-144">A hardware load balancer is required in a Front End pool with more than one Enterprise Edition server.</span></span> <span data-ttu-id="96aa9-145">Un équilibrage de charge n’est pas requis pour un serveur Standard Edition Server ou un serveur frontal Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="96aa9-145">A load balancer is not required for a Standard Edition server or a single Enterprise Edition Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

