---
title: 'Lync Server 2013 : configurer un Trunk sans dérivation multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09fe6841fa8aab5a68017f92313395dc4d8ab55c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a><span data-ttu-id="e803d-102">Configurer un Trunk sans dérivation multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e803d-102">Configure a trunk without media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e803d-103">_**Dernière modification de la rubrique :** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="e803d-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="e803d-104">Pour configurer une jonction sur laquelle la déviation du trafic multimédia est désactivée, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e803d-104">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="e803d-105">Si vous voulez configurer un Trunk avec une dérivation multimédia activée, voir [configurer une Trunk with Media bypass dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="e803d-105">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

<span data-ttu-id="e803d-p102">Une configuration de jonction, comme indiqué dans la suite de cette rubrique, regroupe un ensemble de paramètres appliqués aux jonctions affectées à cette configuration de jonction. Une configuration de jonction spécifique peut s’étendre au niveau global (à toutes les jonctions qui ne disposent plus d’une configuration de site ou de pool spécifique) ou au niveau d’un site ou d’un pool. La configuration de jonction au niveau du pool est utilisée pour étendre une configuration de jonction spécifique à une jonction unique.</span><span class="sxs-lookup"><span data-stu-id="e803d-p102">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="e803d-109">Pour configurer une jonction sans déviation du trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="e803d-109">To configure a trunk without media bypass</span></span>

1.  <span data-ttu-id="e803d-110">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e803d-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e803d-111">Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e803d-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e803d-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e803d-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e803d-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e803d-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e803d-114">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.</span><span class="sxs-lookup"><span data-stu-id="e803d-114">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="e803d-115">Dans la page **Configuration de la jonction**, configurez une jonction à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e803d-115">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="e803d-116">Double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.</span><span class="sxs-lookup"><span data-stu-id="e803d-116">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="e803d-117">Cliquez sur **Nouvelle**, puis sélectionnez une étendue pour la nouvelle configuration de jonction :</span><span class="sxs-lookup"><span data-stu-id="e803d-117">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="e803d-118">**Trunk de site :** Choisissez le site pour cette configuration de Trunk dans **Sélectionner un site** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e803d-118">**Site trunk:** Choose the site for this trunk configuration in **Select a Site** , and then click **OK**.</span></span> <span data-ttu-id="e803d-119">Notez que si une configuration de Trunk a déjà été créée pour un site, ce site n’apparaît pas dans **Sélectionner un site**.</span><span class="sxs-lookup"><span data-stu-id="e803d-119">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="e803d-120">Cette configuration de Trunk est appliquée à tous les Trunks du site.</span><span class="sxs-lookup"><span data-stu-id="e803d-120">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="e803d-121">**Trunk de réserve :** Sélectionnez le nom du Trunk auquel s’applique cette configuration de Trunk dans **Sélectionner un service** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e803d-121">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="e803d-122">Ce Trunk peut être le Trunk racine ou d’éventuelles liaisons supplémentaires définies dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="e803d-122">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="e803d-123">Notez que si une configuration de Trunk a déjà été créée pour une ligne particulière, le Trunk n’apparaît pas dans **Sélectionner un service**.</span><span class="sxs-lookup"><span data-stu-id="e803d-123">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e803d-124">Une fois que l’étendue de la configuration de jonction est sélectionnée, elle ne peut plus être modifiée.</span><span class="sxs-lookup"><span data-stu-id="e803d-124">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="e803d-125">Le champ <STRONG>Nom</STRONG> est prérempli et comporte le nom du site ou du service associé à la configuration de jonction. Ce nom ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="e803d-125">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="e803d-126">Sélectionnez l’une des options de **Niveau de prise en charge du chiffrement** :</span><span class="sxs-lookup"><span data-stu-id="e803d-126">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="e803d-127">**Obligatoire :** Le chiffrement SRTP (Secure Real-Time Transport Protocol) doit être utilisé pour protéger le trafic entre le serveur de médiation et la passerelle ou le PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="e803d-127">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="e803d-128">**Facultatif :** Le chiffrement SRTP est utilisé si le prestataire de services ou le fabricant du matériel le prend en charge.</span><span class="sxs-lookup"><span data-stu-id="e803d-128">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="e803d-129">**Non pris en charge :** Le chiffrement SRTP n’est pas pris en charge par le fabricant du fournisseur de services ou de l’équipement et ne sera donc pas utilisé.</span><span class="sxs-lookup"><span data-stu-id="e803d-129">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6.  <span data-ttu-id="e803d-130">Assurez-vous que la case à cocher **Activer la déviation du trafic multimédia** est désactivée.</span><span class="sxs-lookup"><span data-stu-id="e803d-130">Be sure that the **Enable media bypass** check box is cleared.</span></span>

7.  <span data-ttu-id="e803d-131">Activez la case à cocher **traitement multimédia centralisé** s’il y a un point de terminaison de média bien connu (par exemple, une passerelle RTC (réseau téléphonique commuté) pour laquelle la terminaison du signalement a la même adresse IP.</span><span class="sxs-lookup"><span data-stu-id="e803d-131">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a public switched telephone network (PSTN) gateway where the media termination has the same IP as the signaling termination).</span></span> <span data-ttu-id="e803d-132">Désactivez cette case à cocher si la jonction ne comporte pas de point de terminaison multimédia connu.</span><span class="sxs-lookup"><span data-stu-id="e803d-132">Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8.  <span data-ttu-id="e803d-133">Si l’homologue de Trunk prend en charge la réception des demandes de renvoi SIP du serveur de médiation, activez la case à cocher **activer l’envoi** .</span><span class="sxs-lookup"><span data-stu-id="e803d-133">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

9.  <span data-ttu-id="e803d-134">(Facultatif) Pour permettre le routage interjonction, associez et configurez les enregistrements d’utilisation RTC à cette configuration de jonction.</span><span class="sxs-lookup"><span data-stu-id="e803d-134">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="e803d-135">Les utilisations RTC associées à cette configuration de Trunk s’appliquent à tous les appels entrants par le biais du Trunk qui n’est pas provenant d’un point de terminaison Lync.</span><span class="sxs-lookup"><span data-stu-id="e803d-135">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint.</span></span> <span data-ttu-id="e803d-136">Pour gérer les enregistrements d’utilisation RTC associés à une configuration de jonction, appliquez l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e803d-136">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="e803d-137">Pour sélectionner un ou plusieurs enregistrements dans la liste de tous les enregistrements d’utilisation RTC disponibles dans le déploiement de votre voix entreprise, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="e803d-137">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="e803d-138">Sélectionnez les enregistrements à associer à cette configuration de jonction, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e803d-138">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="e803d-139">Pour supprimer un enregistrement d’utilisation RTC de cette configuration de jonction, sélectionnez l’enregistrement, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e803d-139">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="e803d-140">Pour définir un nouvel enregistrement d’utilisation RTC et l’associer à cette configuration de jonction, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e803d-140">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="e803d-141">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e803d-141">Click **New**.</span></span>
        
        2.  <span data-ttu-id="e803d-142">Dans le champ **Nom**, indiquez un nom descriptif unique pour l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="e803d-142">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="e803d-p110">Le nom de l’enregistrement d’utilisation RTC doit être unique dans le déploiement Voix Entreprise. Une fois que vous avez enregistré l’enregistrement, vous ne pouvez plus modifier le champ <STRONG>Nom</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e803d-p110">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="e803d-145">Pour associer et configurer les itinéraires pour cet enregistrement d’utilisation RTC, appliquez l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e803d-145">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="e803d-146">Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans le déploiement de votre voix entreprise, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="e803d-146">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="e803d-147">Sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e803d-147">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="e803d-148">Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e803d-148">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="e803d-149">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e803d-149">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="e803d-150">Pour plus d’informations, reportez-vous à [créer un itinéraire vocal dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="e803d-150">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="e803d-151">Pour modifier un itinéraire associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="e803d-151">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="e803d-152">Pour plus d’informations, voir [modifier un itinéraire vocal dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="e803d-152">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="e803d-153">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e803d-153">Click **OK**.</span></span>
    
      - <span data-ttu-id="e803d-154">Pour modifier un enregistrement d’utilisation RTC déjà associé à cette configuration de jonction, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e803d-154">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="e803d-155">Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="e803d-155">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="e803d-156">Pour associer et configurer les itinéraires pour cet enregistrement d’utilisation RTC, appliquez l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e803d-156">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="e803d-157">Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans le déploiement de votre voix entreprise, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="e803d-157">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="e803d-158">Sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e803d-158">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="e803d-159">Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e803d-159">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="e803d-160">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e803d-160">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="e803d-161">Pour plus d’informations, reportez-vous à [créer un itinéraire vocal dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="e803d-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="e803d-162">Pour modifier un itinéraire associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="e803d-162">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="e803d-163">Pour plus d’informations, voir [modifier un itinéraire vocal dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="e803d-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="e803d-164">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e803d-164">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e803d-165">Il est important d’associer les enregistrements d’utilisation RTC en fonction de l’homologue du serveur de médiation associé au Trunk en cours de configuration.</span><span class="sxs-lookup"><span data-stu-id="e803d-165">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="e803d-166">S’il s’agit d’une passerelle PSTN ou d’un contrôleur de bordure de session (SBC), il est vivement recommandé que la configuration de Trunk ne soit pas associée à un enregistrement d’utilisation RTC qui achemine vers une destination PSTN ou tout autre système en aval connecté via Lync. Serveurs.</span><span class="sxs-lookup"><span data-stu-id="e803d-166">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

10. <span data-ttu-id="e803d-p118">Organisez les enregistrements d’utilisation RTC pour bénéficier de performances optimales. Pour modifier la position d’un enregistrement dans la liste, sélectionnez l’enregistrement d’utilisation RTC, puis cliquez sur la flèche vers le haut ou vers le bas.</span><span class="sxs-lookup"><span data-stu-id="e803d-p118">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e803d-169">L’ordre des enregistrements d’utilisation RTC dans la liste de la configuration de jonction a son importance.</span><span class="sxs-lookup"><span data-stu-id="e803d-169">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="e803d-170">Lync Server parcourt la liste de haut en bas.</span><span class="sxs-lookup"><span data-stu-id="e803d-170">Lync Server traverses the list from top to down.</span></span>

    
    </div>

11. <span data-ttu-id="e803d-171">**Activer l’accrochage RTP** doit être sélectionné pour activer la déviation du trafic multimédia pour les clients se trouvant derrière un convertisseur d’adresses réseau (NAT) ou un pare-feu et un contrôleur SBC prenant en charge l’accrochage.</span><span class="sxs-lookup"><span data-stu-id="e803d-171">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="e803d-172">L’option **activer l’historique des appels en aval** doit être sélectionnée pour permettre l’envoi des informations de l’historique des appels à l’homologue de la passerelle du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="e803d-172">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="e803d-173">**Autorisez les données de renvoi d’identité P** qui doivent être sélectionnées pour permettre aux informations de l’appelant d’appeler PAI d’être transmises entre le côté du serveur de médiation et la passerelle (et vice versa), le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="e803d-173">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="e803d-174">L’option **Activer le minuteur de basculement de routage de trafic sortant** doit être sélectionnée pour permettre un basculement rapide.</span><span class="sxs-lookup"><span data-stu-id="e803d-174">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="e803d-175">La passerelle associée à cette jonction peut avertir dans les 10 secondes du traitement de l’appel sortant.</span><span class="sxs-lookup"><span data-stu-id="e803d-175">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="e803d-176">Le reroutage vers un autre Trunk se produit si la notification n’est pas reçue par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="e803d-176">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="e803d-177">Sur les réseaux dont la latence peut retarder le temps de réponse ou si la passerelle met plus de 10 secondes à répondre, le basculement rapide doit être désactivé.</span><span class="sxs-lookup"><span data-stu-id="e803d-177">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="e803d-178">(Facultatif) Associez et configurez les **règles de conversion du numéro d’appel** pour la jonction.</span><span class="sxs-lookup"><span data-stu-id="e803d-178">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="e803d-179">Ces règles de conversion s’appliquent au numéro appelant pour les appels sortants</span><span class="sxs-lookup"><span data-stu-id="e803d-179">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="e803d-180">Pour sélectionner une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="e803d-180">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="e803d-181">Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e803d-181">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="e803d-182">Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="e803d-182">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="e803d-183">Pour plus d’informations sur la définition d’une règle, voir [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="e803d-183">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="e803d-184">Pour modifier une règle de conversion déjà associée à la jonction, sélectionnez le nom de la règle, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="e803d-184">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="e803d-185">Pour plus d’informations, reportez-vous à [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="e803d-185">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="e803d-186">Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle, sur **Copier**, puis sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="e803d-186">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="e803d-187">Pour plus d’informations, reportez-vous à [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="e803d-187">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="e803d-188">Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e803d-188">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="sûreté" alt="security" /><span data-ttu-id="e803d-190">Note de sécurité :</span><span class="sxs-lookup"><span data-stu-id="e803d-190">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="e803d-191">N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit.</span><span class="sxs-lookup"><span data-stu-id="e803d-191">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. <span data-ttu-id="e803d-p126">(Facultatif) Associez et configurez les **règles de conversion de numéro appelé** pour la jonction. Les règles de conversion s’appliquent au numéro appelé dans un appel sortant.</span><span class="sxs-lookup"><span data-stu-id="e803d-p126">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="e803d-194">Pour sélectionner une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="e803d-194">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="e803d-195">Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e803d-195">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="e803d-196">Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="e803d-196">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="e803d-197">Pour plus d’informations sur la définition d’une règle, voir [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="e803d-197">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="e803d-198">Pour modifier une règle de conversion déjà associée à la jonction, sélectionnez le nom de la règle, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="e803d-198">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="e803d-199">Pour plus d’informations, reportez-vous à [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="e803d-199">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="e803d-200">Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle, sur **Copier**, puis sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="e803d-200">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="e803d-201">Pour plus d’informations, reportez-vous à [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="e803d-201">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="e803d-202">Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e803d-202">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e803d-203">N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit.</span><span class="sxs-lookup"><span data-stu-id="e803d-203">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="e803d-p131">Vérifiez que les règles de conversion s’affichent dans l’ordre adéquat. Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.</span><span class="sxs-lookup"><span data-stu-id="e803d-p131">Make sure that the trunk’s translation rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name, and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e803d-206">Lync Server parcourt la liste des règles de traduction du haut vers le bas et utilise la première règle correspondant au numéro numéroté.</span><span class="sxs-lookup"><span data-stu-id="e803d-206">Lync Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="e803d-207">Si vous configurez une jonction de sorte qu’un numéro composé corresponde à plusieurs règles de conversion, vérifiez que les règles les plus restrictives s’affichent avant les règles les moins restrictives.</span><span class="sxs-lookup"><span data-stu-id="e803d-207">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="e803d-208">Par exemple, si une règle de conversion s’applique à tout numéro à 11 chiffres et qu’une autre s’applique à tout numéro à 11 chiffres commençant par +1425, vérifiez que la règle qui s’applique à tout numéro à 11 chiffres s’affiche <EM>après</EM> la règle la plus restrictive.</span><span class="sxs-lookup"><span data-stu-id="e803d-208">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

18. <span data-ttu-id="e803d-209">Lorsque vous avez fini de configurer la jonction, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e803d-209">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="e803d-210">Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Tout valider**.</span><span class="sxs-lookup"><span data-stu-id="e803d-210">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e803d-211">Chaque fois que vous créez ou modifiez une configuration de jonction, vous devez exécuter la commande <STRONG>Tout valider</STRONG> pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="e803d-211">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="e803d-212">Pour plus d’informations, reportez-vous <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">à la rubrique publier des modifications en attente sur la configuration de l’acheminement de la voix dans Lync Server 2013</A> dans la documentation</span><span class="sxs-lookup"><span data-stu-id="e803d-212">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e803d-213">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e803d-213">See Also</span></span>


[<span data-ttu-id="e803d-214">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e803d-214">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="e803d-215">Définition de règles de conversion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e803d-215">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

