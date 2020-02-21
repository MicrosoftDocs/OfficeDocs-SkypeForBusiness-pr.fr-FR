---
title: 'Lync Server 2013 : configuration d’une jonction avec déviation du trafic multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 256962ace879c9d418d877b94f15227959177407
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="a5dea-102">Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5dea-102">Configure a trunk with media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5dea-103">_**Dernière modification de la rubrique :** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="a5dea-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="a5dea-104">Procédez comme suit pour configurer une jonction avec la déviation du trafic multimédia activée.</span><span class="sxs-lookup"><span data-stu-id="a5dea-104">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="a5dea-105">Pour configurer une jonction avec la déviation du trafic multimédia désactivée, consultez [la rubrique Configure a trunk without Media Bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="a5dea-105">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="a5dea-106">Le contournement de média est utile lorsque vous voulez réduire le nombre de serveurs de médiation déployés.</span><span class="sxs-lookup"><span data-stu-id="a5dea-106">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="a5dea-107">Un pool de serveurs de médiation est généralement déployé sur un site central et contrôle des passerelles sur des sites de succursale.</span><span class="sxs-lookup"><span data-stu-id="a5dea-107">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="a5dea-108">L’activation du contournement de média permet aux médias de passer des appels PSTN (Public Switched Telephone Network) depuis des clients situés sur les sites de succursale directement par les passerelles de ces sites.</span><span class="sxs-lookup"><span data-stu-id="a5dea-108">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="a5dea-109">Les itinéraires d’appels sortants et les stratégies de voix entreprise de Lync Server 2013 doivent être correctement configurés de sorte que les appels PSTN des clients d’un site de succursale soient acheminés vers la passerelle appropriée.</span><span class="sxs-lookup"><span data-stu-id="a5dea-109">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="a5dea-110">Nous vous recommandons vivement d’activer la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="a5dea-110">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="a5dea-111">Toutefois, avant d’activer la déviation du trafic multimédia sur une jonction SIP, vérifiez que votre fournisseur de jonction SIP qualifié prend en charge la déviation du trafic multimédia et est capable de s’accommoder de la configuration requise pour activer le scénario.</span><span class="sxs-lookup"><span data-stu-id="a5dea-111">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="a5dea-112">Plus précisément, le fournisseur doit disposer des adresses IP des serveurs sur le réseau interne de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a5dea-112">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="a5dea-113">Si le fournisseur ne prend pas en charge ce scénario, la déviation du trafic multimédia échouera.</span><span class="sxs-lookup"><span data-stu-id="a5dea-113">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="a5dea-114">Pour plus d’informations, reportez-vous à la rubrique [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="a5dea-114">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a5dea-115">La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle PSTN (réseau téléphonique commuté), PBX IP et contrôleur SBC (session Border Controller).</span><span class="sxs-lookup"><span data-stu-id="a5dea-115">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="a5dea-116">Microsoft a testé un ensemble de passerelles PSTN et de contrôleurs SBC avec des partenaires agréés et a effectué quelques tests avec les systèmes IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="a5dea-116">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="a5dea-117">La déviation du trafic multimédia n’est prise en charge qu’avec les produits et versions répertoriés dans la rubrique Unified Communications Open Interoperability Program – Lync Server à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span><span class="sxs-lookup"><span data-stu-id="a5dea-117">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="a5dea-118">Une configuration de jonction, comme décrit ci-dessous, regroupe un ensemble de paramètres appliqués aux jonctions affectées à cette configuration de jonction.</span><span class="sxs-lookup"><span data-stu-id="a5dea-118">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="a5dea-119">Une configuration de jonction spécifique peut s’étendre au niveau global (à toutes les jonctions qui ne disposent plus d’une configuration de site ou de pool spécifique) ou au niveau d’un site ou d’un pool.</span><span class="sxs-lookup"><span data-stu-id="a5dea-119">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="a5dea-120">La configuration de jonction au niveau du pool est utilisée pour étendre une configuration de jonction spécifique à une jonction unique.</span><span class="sxs-lookup"><span data-stu-id="a5dea-120">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="a5dea-121">Pour configurer une jonction avec la déviation du trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="a5dea-121">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="a5dea-122">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a5dea-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="a5dea-123">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a5dea-123">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a5dea-124">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a5dea-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a5dea-125">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a5dea-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a5dea-126">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-126">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="a5dea-127">Dans la page **Configuration de la jonction**, configurez une jonction à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a5dea-127">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="a5dea-128">Double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-128">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="a5dea-129">Cliquez sur **Nouvelle**, puis sélectionnez l’étendue de la nouvelle configuration de jonction :</span><span class="sxs-lookup"><span data-stu-id="a5dea-129">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="a5dea-130">**Jonction de site :** Choisissez le site de cette configuration de jonction dans **Sélectionner un site**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-130">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="a5dea-131">Notez que si une configuration de jonction a déjà été créée pour un site, le site ne s’affiche pas dans **Sélectionner un site**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-131">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="a5dea-132">Cette configuration de jonction sera appliquée à toutes les jonctions du site.</span><span class="sxs-lookup"><span data-stu-id="a5dea-132">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="a5dea-133">**Jonction de pool :** Choisissez le nom de la jonction à laquelle cette configuration de jonction s’applique.</span><span class="sxs-lookup"><span data-stu-id="a5dea-133">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="a5dea-134">Cette jonction peut être la jonction racine ou toute autre jonction définie dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="a5dea-134">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="a5dea-135">Dans **Sélectionner un service**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-135">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="a5dea-136">Notez que si une configuration de jonction a déjà été créée pour une jonction spécifique, la jonction ne s’affiche pas dans **Sélectionner un service**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-136">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a5dea-137">Une fois que vous avez sélectionné l’étendue de la configuration de jonction, elle n’est plus modifiable.</span><span class="sxs-lookup"><span data-stu-id="a5dea-137">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="a5dea-138">Le champ <STRONG>Nom</STRONG> est prérempli et comporte le nom du site ou service associé à la configuration de jonction. Ce nom n’est pas modifiable.</span><span class="sxs-lookup"><span data-stu-id="a5dea-138">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="a5dea-139">Spécifiez une valeur dans la **boîte de dialogue maximum Early pris en charge**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-139">Specify a value in **Maximum early dialogs supported**.</span></span> <span data-ttu-id="a5dea-140">Il s’agit du nombre maximal de réponses avec branches qu’une passerelle PSTN (réseau téléphonique commuté), un système IP-PBX ou un contrôleur SBC (session Border Controller) téléphonie Internet peut recevoir à une invitation qui est envoyée au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="a5dea-140">This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server.</span></span> <span data-ttu-id="a5dea-141">La valeur par défaut est 20.</span><span class="sxs-lookup"><span data-stu-id="a5dea-141">The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a5dea-142">Avant de modifier cette valeur, consultez votre fournisseur de services ou le fabricant de votre équipement pour obtenir plus d’informations sur les fonctionnalités de votre système.</span><span class="sxs-lookup"><span data-stu-id="a5dea-142">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="a5dea-143">Sélectionnez l’une des options de **Niveau de prise en charge du chiffrement** :</span><span class="sxs-lookup"><span data-stu-id="a5dea-143">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="a5dea-144">**Obligatoire :** Le chiffrement SRTP (Secure Real-Time Transport Protocol) doit être utilisé pour protéger le trafic entre le serveur de médiation et la passerelle ou le système PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="a5dea-144">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="a5dea-145">**Facultatif :** Le chiffrement SRTP sera utilisé s’il est pris en charge par le fournisseur de services ou le fabricant.</span><span class="sxs-lookup"><span data-stu-id="a5dea-145">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="a5dea-146">**Non pris en charge :** Le chiffrement SRTP n’est pas pris en charge par le fournisseur de services ou le fabricant de l’équipement et ne sera donc pas utilisé.</span><span class="sxs-lookup"><span data-stu-id="a5dea-146">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="a5dea-147">Activez la case à cocher **activer le contournement de média** si vous souhaitez que les médias contournent le serveur de médiation pour le traitement par l’homologue de jonction.</span><span class="sxs-lookup"><span data-stu-id="a5dea-147">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a5dea-148">Pour que la déviation du trafic multimédia fonctionne correctement, la passerelle PSTN, le système IP-PBX ou le contrôleur de session téléphonie Internet doit prendre en charge certaines fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="a5dea-148">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="a5dea-149">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-planning-for-media-bypass.md">Planning for Media Bypass in Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="a5dea-149">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="a5dea-150">Activez la case à cocher **traitement multimédia centralisé** s’il existe un point de terminaison de média connu (par exemple, une passerelle RTC où l’arrêt du média a la même adresse IP que la terminaison de signalisation).</span><span class="sxs-lookup"><span data-stu-id="a5dea-150">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination).</span></span> <span data-ttu-id="a5dea-151">Désactivez cette case à cocher si la jonction ne comporte pas de point de terminaison multimédia connu.</span><span class="sxs-lookup"><span data-stu-id="a5dea-151">Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="a5dea-152">Si l’homologue de jonction prend en charge la réception des demandes SIP REFER à partir du serveur de médiation, activez la case à cocher **activer l’envoi en tant que passerelle** .</span><span class="sxs-lookup"><span data-stu-id="a5dea-152">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a5dea-153">Si vous désactivez cette option alors que l’option Activer la déviation du trafic <STRONG>multimédia</STRONG> est sélectionnée, des paramètres supplémentaires sont requis.</span><span class="sxs-lookup"><span data-stu-id="a5dea-153">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="a5dea-154">Si l’homologue de jonction ne prend pas en charge la réception des demandes SIP REFER à partir du serveur de médiation et que la déviation du trafic multimédia est activée, vous devez également exécuter l’applet de commande <STRONG>Set-applet cstrunkconfiguration</STRONG> pour désactiver le protocole RTCP pour les appels actifs et conservés afin de prendre en charge les conditions appropriées pour la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="a5dea-154">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="a5dea-155">Pour plus d’informations, reportez-vous à la documentation de <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> .</span><span class="sxs-lookup"><span data-stu-id="a5dea-155">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="a5dea-156">Vous pouvez également sélectionner <STRONG>Enable voir Using tiers-Call Control</STRONG> si vous voulez que les appels transférés soient détournées de médias et que la passerelle ne prenne pas en charge les demandes SIP refer.</span><span class="sxs-lookup"><span data-stu-id="a5dea-156">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="a5dea-p113">(Facultatif) Pour permettre le routage interjonction, associez et configurez les enregistrements d’utilisation PSTN à la configuration de cette jonction. Les utilisations PSTN associées à cette configuration de jonction seront appliquées à tous les appels entrants via la jonction qui ne provient pas d’un point de terminaison Lync. Pour gérer les enregistrements d’utilisation PSTN associés à une configuration de jonction, utilisez l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a5dea-p113">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="a5dea-160">Pour sélectionner un ou plusieurs enregistrements dans la liste de tous les enregistrements d’utilisation RTC disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-160">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a5dea-161">Sélectionnez les enregistrements à associer à cette configuration de jonction, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-161">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="a5dea-162">Pour supprimer un enregistrement d’utilisation PSTN de cette configuration de jonction, sélectionnez l’enregistrement, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-162">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="a5dea-163">Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette configuration de jonction, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a5dea-163">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="a5dea-164">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-164">Click **New**.</span></span>
        
        2.  <span data-ttu-id="a5dea-165">Dans le champ **Nom**, indiquez un nom descriptif unique pour l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="a5dea-165">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="a5dea-p115">Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ <STRONG>Nom</STRONG> ne peut plus être modifié.</span><span class="sxs-lookup"><span data-stu-id="a5dea-p115">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="a5dea-168">Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires pour cet enregistrement d’utilisation PSTN :</span><span class="sxs-lookup"><span data-stu-id="a5dea-168">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="a5dea-169">Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-169">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a5dea-170">Sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-170">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="a5dea-171">Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-171">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="a5dea-172">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-172">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="a5dea-173">Pour plus d’informations, consultez [la rubrique créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="a5dea-173">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="a5dea-174">Pour modifier un itinéraire associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-174">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="a5dea-175">Pour plus d’informations, consultez [la rubrique modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="a5dea-175">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="a5dea-176">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-176">Click **OK**.</span></span>
    
      - <span data-ttu-id="a5dea-177">Pour modifier un enregistrement d’utilisation PSTN déjà associé à cette configuration de jonction, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a5dea-177">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="a5dea-178">Sélectionnez l’enregistrement d’utilisation PSTN que vous voulez modifier, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-178">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="a5dea-179">Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires pour cet enregistrement d’utilisation PSTN :</span><span class="sxs-lookup"><span data-stu-id="a5dea-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="a5dea-180">Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a5dea-181">Sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="a5dea-182">Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="a5dea-183">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="a5dea-184">Pour plus d’informations, consultez [la rubrique créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="a5dea-184">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="a5dea-185">Pour modifier un itinéraire associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="a5dea-186">Pour plus d’informations, consultez [la rubrique modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="a5dea-186">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="a5dea-187">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-187">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a5dea-188">Il est important d’associer les enregistrements d’utilisation PSTN en fonction de l’homologue de serveur de médiation associé à la jonction en cours de configuration.</span><span class="sxs-lookup"><span data-stu-id="a5dea-188">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="a5dea-189">Si l’homologue du serveur de médiation est une passerelle RTC ou un contrôleur de frontière de session (SBC), il est vivement recommandé que la configuration de jonction ne soit pas associée à un enregistrement d’utilisation PSTN qui achemine vers une destination PSTN ou tout autre système en aval connecté via Lync. Serveurs.</span><span class="sxs-lookup"><span data-stu-id="a5dea-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="a5dea-p123">Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez l’enregistrement d’utilisation PSTN, puis cliquez sur la flèche vers le haut ou vers le bas.</span><span class="sxs-lookup"><span data-stu-id="a5dea-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a5dea-192">L’ordre des enregistrements d’utilisation PSTN dans la liste de la configuration de jonction a son importance.</span><span class="sxs-lookup"><span data-stu-id="a5dea-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="a5dea-193">Lync Server parcourt la liste de haut en bas.</span><span class="sxs-lookup"><span data-stu-id="a5dea-193">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="a5dea-194">**Activer le verrouillage RTP** doit être sélectionné pour activer le support de contournement pour les clients derrière une traduction d’adresses réseau (NAT) ou un pare-feu et un contrôleur SBC prenant en charge le verrouillage.</span><span class="sxs-lookup"><span data-stu-id="a5dea-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="a5dea-195">**Activer l’historique du transfert d’appel** doit être sélectionné pour permettre l’envoi des informations d’historique d’appel à l’homologue de passerelle du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="a5dea-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="a5dea-196">**Activer les données de transfert p-asserted-Identity** doit être sélectionné pour permettre aux informations d’origine de l’appel de p-asserted-Identity (PAI) d’être transférées entre le côté serveur de médiation et la passerelle (et vice versa), le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="a5dea-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="a5dea-197">**Activer le minuteur de basculement de routage de trafic sortant** doit être sélectionné pour permettre un basculement rapide.</span><span class="sxs-lookup"><span data-stu-id="a5dea-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="a5dea-198">La passerelle associée à cette jonction peut informer dans les 10 secondes du traitement de l’appel sortant.</span><span class="sxs-lookup"><span data-stu-id="a5dea-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="a5dea-199">La redirection vers une autre jonction se produira si cette notification n’est pas reçue par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="a5dea-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="a5dea-200">Sur des réseaux avec une latence qui peut retarder le temps de réponse ou si la passerelle prend plus de 10 secondes à répondre, le basculement rapide doit être désactivé.</span><span class="sxs-lookup"><span data-stu-id="a5dea-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="a5dea-201">(Facultatif) Associez et configurez les **règles de traduction du numéro d’appel** pour la jonction.</span><span class="sxs-lookup"><span data-stu-id="a5dea-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="a5dea-202">Ces règles de traduction s’appliquent au numéro appelant pour les appels sortants</span><span class="sxs-lookup"><span data-stu-id="a5dea-202">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="a5dea-203">Pour choisir une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a5dea-204">Dans **Sélectionner les règles de traduction**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="a5dea-205">Si vous voulez définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="a5dea-206">Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="a5dea-206">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="a5dea-207">Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="a5dea-208">Pour plus d’informations, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="a5dea-208">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="a5dea-209">Pour copier une règle de traduction existante qui servira de point de départ à la définition d’une nouvelle règle, cliquez sur son nom, sur **Copier**, puis sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-209">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="a5dea-210">Pour plus d’informations, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="a5dea-210">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="a5dea-211">Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-211">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="a5dea-212">N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit.</span><span class="sxs-lookup"><span data-stu-id="a5dea-212">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="a5dea-p131">(Facultatif) Associez et configurez les **règles de traduction de numéro appelé** pour la jonction. Les règles de traduction s’appliquent au numéro appelé dans un appel sortant.</span><span class="sxs-lookup"><span data-stu-id="a5dea-p131">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="a5dea-215">Pour choisir une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-215">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a5dea-216">Dans **Sélectionner les règles de traduction**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-216">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="a5dea-217">Si vous voulez définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-217">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="a5dea-218">Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="a5dea-218">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="a5dea-219">Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-219">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="a5dea-220">Pour plus d’informations, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="a5dea-220">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="a5dea-221">Pour copier une règle de traduction existante qui servira de point de départ à la définition d’une nouvelle règle, cliquez sur son nom, sur **Copier**, puis sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-221">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="a5dea-222">Pour plus d’informations, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="a5dea-222">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="a5dea-223">Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-223">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="a5dea-224">N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit.</span><span class="sxs-lookup"><span data-stu-id="a5dea-224">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="a5dea-225">Assurez-vous que les règles de traduction de la jonction sont organisées dans le bon ordre.</span><span class="sxs-lookup"><span data-stu-id="a5dea-225">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="a5dea-226">Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.</span><span class="sxs-lookup"><span data-stu-id="a5dea-226">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a5dea-227">Lync Server 2013 parcourt la liste de règles de traduction du haut vers le bas et utilise la première règle qui correspond au numéro composé.</span><span class="sxs-lookup"><span data-stu-id="a5dea-227">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="a5dea-228">Si vous configurez une jonction de sorte qu’un numéro composé corresponde à plusieurs règles de traduction, assurez-vous que les règles les plus restrictives apparaissent avant les règles les moins restrictives.</span><span class="sxs-lookup"><span data-stu-id="a5dea-228">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="a5dea-229">Par exemple, si une règle de traduction s’applique à tout numéro à 11 chiffres et une autre s’applique à tout numéro à 11 chiffres commençant par +1425, assurez-vous que la règle qui s’applique à tout numéro à 11 chiffres apparaît <EM>après</EM> la règle la plus restrictive.</span><span class="sxs-lookup"><span data-stu-id="a5dea-229">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="a5dea-230">Lorsque vous avez terminé de configurer la jonction, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-230">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="a5dea-231">Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="a5dea-231">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a5dea-232">À chaque fois que vous créez ou modifiez une configuration de jonction, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="a5dea-232">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="a5dea-233">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="a5dea-233">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="a5dea-234">Une fois que vous avez configuré la jonction, poursuivez la configuration du contournement de média en choisissant entre les options de contournement de média global, comme décrit dans [Global Media Bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="a5dea-234">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a5dea-235">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a5dea-235">See Also</span></span>


[<span data-ttu-id="a5dea-236">Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5dea-236">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="a5dea-237">Configurer la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5dea-237">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="a5dea-238">Options globales de déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5dea-238">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="a5dea-239">Définition de règles de conversion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5dea-239">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

