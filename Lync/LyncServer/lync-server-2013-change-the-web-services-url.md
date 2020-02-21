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
ms.openlocfilehash: 94424edc38cf1cc0eacac2638a4ed30a18f06779
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a><span data-ttu-id="d2a2c-102">Modifier l’URL des services Web dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2a2c-102">Change the Web Services URL in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2a2c-103">_**Dernière modification de la rubrique :** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="d2a2c-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="d2a2c-104">Lorsque vous configurez vos pools frontaux et vos serveurs Standard Edition, vous avez la possibilité de configurer un nom de domaine complet (FQDN) de batterie de serveurs web externes et des ports associés.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-104">When you set up your Front End pools and Standard Edition servers, you have the option to configure an external Web farm fully qualified domain name (FQDN) and associated ports.</span></span> <span data-ttu-id="d2a2c-105">Si vous n’avez pas configuré cette URL lors de l’exécution de l’Assistant Déploiement de Lync Server, vous devez configurer manuellement ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-105">If you did not configure this URL when you ran the Lync Server Deployment Wizard, you need to manually configure these settings.</span></span> <span data-ttu-id="d2a2c-106">Un administrateur n’a généralement pas besoin de modifier ces paramètres, puisqu’il s’agit des valeurs recommandées et des ports par défaut.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-106">An administrator typically does not need to modify these settings, as these are the recommended and default ports.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d2a2c-107">La capture d’écran suivante a été effectuée lors de la configuration d’un serveur Standard Edition, de sorte que l’option remplacer le nom de domaine complet est désactivée.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-107">The following screen shot was taken while configuring a Standard Edition server, so the Override FQDN option is disabled.</span></span> <span data-ttu-id="d2a2c-108">Cette option est activée lors de la configuration d’un serveur Enterprise Edition dans un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-108">That option is enabled when configuring an Enterprise Edition server in a Front End pool.</span></span>



</div>

<span data-ttu-id="d2a2c-109">![Modifier les paramètres du pool des services Web](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Modifier les paramètres du pool des services Web")</span><span class="sxs-lookup"><span data-stu-id="d2a2c-109">![Edit Web Services Pool Settings](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Edit Web Services Pool Settings")</span></span>

<div>

## <a name="to-configure-web-services"></a><span data-ttu-id="d2a2c-110">Pour configurer les services Web</span><span class="sxs-lookup"><span data-stu-id="d2a2c-110">To configure web services</span></span>

1.  <span data-ttu-id="d2a2c-111">Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d2a2c-112">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-112">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="d2a2c-113">Dans le générateur de topologie, dans l’arborescence de la console, sous **serveurs frontaux Standard Edition**, **Pools frontaux Enterprise Edition**et **pools de répertoires**, sélectionnez le nom du pool.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-113">In Topology Builder, in the console tree under **Standard Edition Front End Servers**, **Enterprise Edition Front End pools**, and **Directory pools**, select the pool name.</span></span> <span data-ttu-id="d2a2c-114">Cliquez avec le bouton droit sur le nom, cliquez sur **Modifier les propriétés**, puis cliquez sur **Services web**.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-114">Right-click the name, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="d2a2c-115">Ajoutez ou modifiez le **Nom de domaine complet (FQDN) des services web externes**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-115">Add or edit the **External Web Services FQDN**, and then click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d2a2c-116">Si vous avez plusieurs pools frontaux ou serveurs frontaux, le nom de domaine complet (FQDN) des services Web externes doit être unique.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-116">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="d2a2c-117">Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que <STRONG>pool01.contoso.com</STRONG>, vous ne pouvez pas utiliser <STRONG>pool01.contoso.com</STRONG> pour un autre pool frontal ou serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-117">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="d2a2c-118">Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour tout directeur ou pool directeur doit être unique à partir d’un autre directeur ou pool Directeur, ainsi que d’un pool frontal ou d’un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-118">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="d2a2c-119">Vérifiez que les ports d’écoute et les ports publiés sont correctement configurés pour votre environnement.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-119">Verify the listening and published ports are configured correctly for your environment.</span></span>

6.  <span data-ttu-id="d2a2c-120">Répétez ces étapes pour tous les serveurs Standard Edition, pools frontaux et pools directeurs dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-120">Repeat these steps for all Standard Edition servers, Front End Pools, and Director pools in your environment.</span></span>

7.  <span data-ttu-id="d2a2c-121">Dans l’arborescence de la console, cliquez sur **Lync Server 2013** puis, dans le volet **Actions**, cliquez sur **Publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-121">In the console tree, click **Lync Server 2013**, and then, in the **Actions** pane, click **Publish Topology**.</span></span>

<span data-ttu-id="d2a2c-122">Vous devez respecter quelques conditions préalables lorsque vous configurez les ports d’écoute et de publication :</span><span class="sxs-lookup"><span data-stu-id="d2a2c-122">There are a few requirements you should be aware of when configuring the Listening and Publishing ports:</span></span>

  - <span data-ttu-id="d2a2c-123">Les ports d’écoute présentés sont les ports configurés pour Internet Information Server (IIS) sur chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-123">The listening ports shown are the ports that are configured for Internet Information Server (IIS) on each Front End Server.</span></span>

  - <span data-ttu-id="d2a2c-p105">Les ports d’écoute internes et externes doivent être différents pour IIS. En ce qui concerne les ports d’écoute externes, ils sont généralement identiques, car l’un représente le programme d’équilibrage de la charge matérielle pour le trafic web interne et l’autre représente le serveur proxy inverse pour le trafic web externe.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-p105">The internal and external listening ports must be different for IIS. For the external listening ports, these are typically the same because one represents the hardware load balancer for internal web traffic and one represents the reverse proxy server for external web traffic.</span></span>

  - <span data-ttu-id="d2a2c-126">Vous pouvez remplacer les services Web internes sur un pool frontal, un directeur ou un pool directeur et définir votre propre nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-126">You can override the Internal web services on a Front End pool, Director or a Director pool and define your own FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d2a2c-127">Si vous décidez de remplacer les services Web internes par un nom de domaine complet indépendant, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool directeur.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-127">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

  - <span data-ttu-id="d2a2c-128">Les ports publiés doivent être configurés sur le proxy inverse ou le programme d’équilibrage de la charge matérielle en tant que ports d’écoute.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-128">The published ports must be configured on the reverse proxy or hardware load balancer as listening ports.</span></span>

  - <span data-ttu-id="d2a2c-p106">Pour un pool frontal (non présenté dans l’exemple), le nom de domaine complet (FQDN) du pool SIP interne doit être différent du nom de domaine complet (FQDN) des services web internes, car le trafic web passe par le programme d’équilibrage de la charge matérielle et le trafic du pool SIP interne passe par le programme d’équilibrage de la charge DNS. Cette condition préalable doit être respectée.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-p106">For an Front End pool (not shown in the example), the internal SIP pool FQDN must be different from the internal web services FQDN, because web traffic comes through the hardware load balancer and the internal SIP pool traffic travels comes through the DNS load balancer. This requirement must be met.</span></span>

  - <span data-ttu-id="d2a2c-131">Un déploiement Lync Server Standard Edition n’a pas besoin ou n’autorise pas le remplacement d’un nom de domaine complet (FQDN) des services Web internes car ce serveur ne peut pas être équilibré en charge.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-131">A Lync Server Standard Edition deployment does not need or allow an internal web services FQDN to be overridden because this server cannot be load balanced.</span></span>

  - <span data-ttu-id="d2a2c-132">Si vous disposez d’un programme d’équilibrage de la charge matérielle dans votre environnement que vous utilisez pour le trafic SIP et Web interne, le générateur de topologies ne peut pas faire la distinction.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-132">If you have a hardware load balancer in your environment that you use for both internal SIP and web traffic, the Topology Builder cannot make the distinction.</span></span>
    
    <span data-ttu-id="d2a2c-133">Les noms de domaine complets des services Web doivent être facilement différenciés les uns des autres ; Cela permet de s’assurer que la redirection d’URL pointe vers le serveur approprié.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-133">Web service FQDNs should be easily-differentiated from one another; that helps to ensure that URL redirection points clients towards the appropriate server.</span></span> <span data-ttu-id="d2a2c-134">Par exemple, si vous avez deux noms de domaine complets, vous pouvez nommer un meeting.contoso.com et l’autre conferencing.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-134">For example, if you have two FQDNs you might consider naming one meeting.contoso.com and the other conferencing.contoso.com.</span></span> <span data-ttu-id="d2a2c-135">Vous pouvez potentiellement rencontrer des problèmes de redirection si vous avez des noms de domaine complets avec des noms plus similaires, tels que meet1.contoso.com et meet2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-135">You could potentially run into redirection issues if you have FQDNs with more similar names, such as meet1.contoso.com and meet2.contoso.com.</span></span>

<span data-ttu-id="d2a2c-136">Les services web externes fonctionnent conjointement avec un proxy inverse dans le réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-136">The external web services works in conjunction with a reverse proxy in the perimeter network.</span></span> <span data-ttu-id="d2a2c-137">Elle offre aux clients un accès externe à l’aide de ces services Web.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-137">It provides clients external access to by using these web services.</span></span> <span data-ttu-id="d2a2c-138">Les noms de domaine complets configurés ici sont envoyés aux clients quand ils se connectent et sont utilisés pour établir une connexion HTTPS au proxy inverse en cas de connexion à distance.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-138">The FQDNs configured here are sent to clients when they log on, and are used to make an HTTPS connection back to the reverse proxy when connecting remotely.</span></span> <span data-ttu-id="d2a2c-139">Le serveur proxy inverse transfère le nom de domaine complet des services web externes à un appareil d’équilibrage de charge interne ou directement au pool.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-139">The reverse-proxy server forwards the external web service FQDN to an internal hardware load balancer, or directly to the pool.</span></span> <span data-ttu-id="d2a2c-140">Le serveur proxy doit pouvoir résoudre le nom de domaine complet des services web externes en adresse IP du serveur web interne.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-140">The reverse proxy must be able to resolve the external web services FQDN to the IP address of the internal Web server.</span></span> <span data-ttu-id="d2a2c-141">Le nom de domaine complet des services web externes doit pouvoir être résolu sur le réseau Internet public.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-141">The external web services FDQN must be resolvable in the public Internet.</span></span>

<span data-ttu-id="d2a2c-142">Si votre serveur interne est un serveur Standard Edition, le nom de domaine complet interne est le nom de domaine complet du serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-142">If your internal server is a Standard Edition server, the internal FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="d2a2c-143">Si votre serveur interne est un pool frontal, le nom de domaine complet (FQDN) est une adresse IP virtuelle (VIP) du programme d’équilibrage de la charge matérielle, qui équilibre la charge des serveurs de la batterie de serveurs web internes.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-143">If your internal server is a Front End pool, the FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="d2a2c-144">Un programme d’équilibrage de la charge matérielle est nécessaire dans un pool frontal comportant plusieurs serveurs Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-144">A hardware load balancer is required in a Front End pool with more than one Enterprise Edition server.</span></span> <span data-ttu-id="d2a2c-145">Un programme d’équilibrage de la charge n’est pas nécessaire pour un serveur Standard Edition ou un seul serveur frontal Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="d2a2c-145">A load balancer is not required for a Standard Edition server or a single Enterprise Edition Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

