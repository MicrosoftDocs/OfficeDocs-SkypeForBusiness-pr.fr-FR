---
title: 'Lync Server 2013 : configuration d’une jonction sans déviation du trafic multimédia'
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
ms.openlocfilehash: bd810c64f546c907f0fd00d2dc2fea43e09fa1bf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a><span data-ttu-id="b5a54-102">Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5a54-102">Configure a trunk without media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5a54-103">_**Dernière modification de la rubrique :** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="b5a54-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="b5a54-104">Pour configurer une jonction sur laquelle le contournement de média est désactivé, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b5a54-104">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="b5a54-105">Si vous souhaitez configurer une jonction avec la déviation du trafic multimédia activée, consultez [la rubrique Configure a trunk with Media Bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="b5a54-105">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

<span data-ttu-id="b5a54-p102">Une configuration de jonction, comme décrit plus bas, regroupe un ensemble de paramètres appliqués aux jonctions affectées à cette configuration de jonction. Une configuration de jonction spécifique peut s’étendre au niveau global (à toutes les jonctions qui ne disposent plus d’une configuration de site ou de pool spécifique) ou au niveau d’un site ou d’un pool. La configuration de jonction au niveau du pool est utilisée pour étendre une configuration de jonction spécifique à une jonction unique.</span><span class="sxs-lookup"><span data-stu-id="b5a54-p102">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="b5a54-109">Pour configurer une jonction sans contournement de média</span><span class="sxs-lookup"><span data-stu-id="b5a54-109">To configure a trunk without media bypass</span></span>

1.  <span data-ttu-id="b5a54-110">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b5a54-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="b5a54-111">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b5a54-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="b5a54-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5a54-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b5a54-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b5a54-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b5a54-114">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-114">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="b5a54-115">Dans la page **Configuration de la jonction**, configurez une jonction à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="b5a54-115">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="b5a54-116">Double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-116">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="b5a54-117">Cliquez sur **Nouvelle**, puis sélectionnez l’étendue de la nouvelle configuration de jonction :</span><span class="sxs-lookup"><span data-stu-id="b5a54-117">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="b5a54-118">**Jonction de site :** Choisissez le site pour cette configuration de jonction dans **Sélectionner un site** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-118">**Site trunk:** Choose the site for this trunk configuration in **Select a Site** , and then click **OK**.</span></span> <span data-ttu-id="b5a54-119">Notez que si une configuration de jonction a déjà été créée pour un site, le site ne s’affiche pas dans **Sélectionner un site**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-119">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="b5a54-120">Cette configuration de jonction sera appliquée à toutes les jonctions du site.</span><span class="sxs-lookup"><span data-stu-id="b5a54-120">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="b5a54-121">**Jonction de pool :** Choisissez le nom de la jonction à laquelle s’applique cette configuration de jonction dans **Sélectionner un service** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-121">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="b5a54-122">Cette jonction peut être la jonction racine ou toute autre jonction définie dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="b5a54-122">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="b5a54-123">Notez que si une configuration de jonction a déjà été créée pour une jonction spécifique, la jonction ne s’affiche pas dans **Sélectionner un service**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-123">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b5a54-124">Une fois que vous avez sélectionné l’étendue de la configuration de jonction, elle n’est plus modifiable.</span><span class="sxs-lookup"><span data-stu-id="b5a54-124">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="b5a54-125">Le champ <STRONG>Nom</STRONG> est prérempli et comporte le nom du site ou service associé à la configuration de jonction. Ce nom n’est pas modifiable.</span><span class="sxs-lookup"><span data-stu-id="b5a54-125">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="b5a54-126">Sélectionnez l’une des options de **Niveau de prise en charge du chiffrement** :</span><span class="sxs-lookup"><span data-stu-id="b5a54-126">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="b5a54-127">**Obligatoire :** Le chiffrement SRTP (Secure Real-Time Transport Protocol) doit être utilisé pour protéger le trafic entre le serveur de médiation et la passerelle ou le système PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="b5a54-127">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="b5a54-128">**Facultatif :** Le chiffrement SRTP sera utilisé s’il est pris en charge par le fournisseur de services ou le fabricant.</span><span class="sxs-lookup"><span data-stu-id="b5a54-128">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="b5a54-129">**Non pris en charge :** Le chiffrement SRTP n’est pas pris en charge par le fournisseur de services ou le fabricant de l’équipement et ne sera donc pas utilisé.</span><span class="sxs-lookup"><span data-stu-id="b5a54-129">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6.  <span data-ttu-id="b5a54-130">Assurez-vous que la case à cocher **Activer le contournement de média** est désactivée.</span><span class="sxs-lookup"><span data-stu-id="b5a54-130">Be sure that the **Enable media bypass** check box is cleared.</span></span>

7.  <span data-ttu-id="b5a54-p107">Activez la case à cocher **Traitement multimédia centralisé** si un point de terminaison média connu existe (par exemple, une passerelle PSTN sur laquelle la terminaison multimédia possède la même adresse IP que la terminaison de signalisation). Désactivez cette case à cocher si la jonction ne comporte pas de point de terminaison multimédia connu.</span><span class="sxs-lookup"><span data-stu-id="b5a54-p107">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a public switched telephone network (PSTN) gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8.  <span data-ttu-id="b5a54-133">Si l’homologue de jonction prend en charge la réception des demandes SIP REFER à partir du serveur de médiation, activez la case à cocher **activer l’envoi en tant que passerelle** .</span><span class="sxs-lookup"><span data-stu-id="b5a54-133">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

9.  <span data-ttu-id="b5a54-p108">(Facultatif) Pour permettre le routage interjonction, associez et configurez les enregistrements d’utilisation PSTN à la configuration de cette jonction. Les utilisations PSTN associées à cette configuration de jonction seront appliquées à tous les appels entrants via la jonction qui ne provient pas d’un point de terminaison Lync. Pour gérer les enregistrements d’utilisation PSTN associés à une configuration de jonction, utilisez l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="b5a54-p108">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="b5a54-137">Pour sélectionner un ou plusieurs enregistrements dans la liste de tous les enregistrements d’utilisation RTC disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-137">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="b5a54-138">Sélectionnez les enregistrements à associer à cette configuration de jonction, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-138">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="b5a54-139">Pour supprimer un enregistrement d’utilisation PSTN de cette configuration de jonction, sélectionnez l’enregistrement, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-139">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="b5a54-140">Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette configuration de jonction, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b5a54-140">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="b5a54-141">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-141">Click **New**.</span></span>
        
        2.  <span data-ttu-id="b5a54-142">Dans le champ **Nom**, indiquez un nom descriptif unique pour l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="b5a54-142">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="b5a54-p110">Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ <STRONG>Nom</STRONG> ne peut plus être modifié.</span><span class="sxs-lookup"><span data-stu-id="b5a54-p110">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="b5a54-145">Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires pour cet enregistrement d’utilisation PSTN :</span><span class="sxs-lookup"><span data-stu-id="b5a54-145">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="b5a54-146">Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-146">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="b5a54-147">Sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-147">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="b5a54-148">Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-148">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="b5a54-149">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-149">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="b5a54-150">Pour plus d’informations, consultez [la rubrique créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="b5a54-150">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="b5a54-151">Pour modifier un itinéraire associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-151">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="b5a54-152">Pour plus d’informations, consultez [la rubrique modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="b5a54-152">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="b5a54-153">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-153">Click **OK**.</span></span>
    
      - <span data-ttu-id="b5a54-154">Pour modifier un enregistrement d’utilisation PSTN déjà associé à cette configuration de jonction, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b5a54-154">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="b5a54-155">Sélectionnez l’enregistrement d’utilisation PSTN que vous voulez modifier, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-155">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="b5a54-156">Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires pour cet enregistrement d’utilisation PSTN :</span><span class="sxs-lookup"><span data-stu-id="b5a54-156">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="b5a54-157">Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-157">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="b5a54-158">Sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-158">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="b5a54-159">Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-159">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="b5a54-160">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-160">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="b5a54-161">Pour plus d’informations, consultez [la rubrique créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="b5a54-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="b5a54-162">Pour modifier un itinéraire associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-162">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="b5a54-163">Pour plus d’informations, consultez [la rubrique modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="b5a54-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="b5a54-164">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-164">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b5a54-165">Il est important d’associer les enregistrements d’utilisation PSTN en fonction de l’homologue de serveur de médiation associé à la jonction en cours de configuration.</span><span class="sxs-lookup"><span data-stu-id="b5a54-165">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="b5a54-166">Si l’homologue du serveur de médiation est une passerelle RTC ou un contrôleur de frontière de session (SBC), il est vivement recommandé que la configuration de jonction ne soit pas associée à un enregistrement d’utilisation PSTN qui achemine vers une destination PSTN ou tout autre système en aval connecté via Lync. Serveurs.</span><span class="sxs-lookup"><span data-stu-id="b5a54-166">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

10. <span data-ttu-id="b5a54-p118">Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez l’enregistrement d’utilisation PSTN, puis cliquez sur la flèche vers le haut ou vers le bas.</span><span class="sxs-lookup"><span data-stu-id="b5a54-p118">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b5a54-169">L’ordre des enregistrements d’utilisation PSTN dans la liste de la configuration de jonction a son importance.</span><span class="sxs-lookup"><span data-stu-id="b5a54-169">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="b5a54-170">Lync Server parcourt la liste de haut en bas.</span><span class="sxs-lookup"><span data-stu-id="b5a54-170">Lync Server traverses the list from top to down.</span></span>

    
    </div>

11. <span data-ttu-id="b5a54-171">**Activer l’accrochage RTP** doit être sélectionné pour activer la déviation du trafic multimédia pour les clients se trouvant derrière une NAT ou un pare-feu et un contrôleur SBC prenant en charge l’accrochage.</span><span class="sxs-lookup"><span data-stu-id="b5a54-171">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="b5a54-172">**Activer l’historique du transfert d’appel** doit être sélectionné pour permettre l’envoi des informations d’historique d’appel à l’homologue de passerelle du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="b5a54-172">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="b5a54-173">**Activation des données de transfert P-asserted-Identity** doivent être sélectionnées pour permettre le transfert des informations de l’expéditeur de l’appel PAI entre le côté serveur de médiation et la passerelle (et vice versa), le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="b5a54-173">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="b5a54-174">**Activer le minuteur de basculement de routage de trafic sortant** doit être sélectionné pour permettre un basculement rapide.</span><span class="sxs-lookup"><span data-stu-id="b5a54-174">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="b5a54-175">La passerelle associée à cette jonction peut informer dans les 10 secondes du traitement de l’appel sortant.</span><span class="sxs-lookup"><span data-stu-id="b5a54-175">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="b5a54-176">La redirection vers une autre jonction se produira si cette notification n’est pas reçue par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="b5a54-176">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="b5a54-177">Sur des réseaux avec une latence qui peut retarder le temps de réponse ou si la passerelle prend plus de 10 secondes à répondre, le basculement rapide doit être désactivé.</span><span class="sxs-lookup"><span data-stu-id="b5a54-177">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="b5a54-178">(Facultatif) Associez et configurez les **règles de traduction du numéro d’appel** pour la jonction.</span><span class="sxs-lookup"><span data-stu-id="b5a54-178">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="b5a54-179">Ces règles de traduction s’appliquent au numéro appelant pour les appels sortants</span><span class="sxs-lookup"><span data-stu-id="b5a54-179">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="b5a54-180">Pour choisir une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-180">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="b5a54-181">Dans **Sélectionner les règles de traduction**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-181">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="b5a54-182">Si vous voulez définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-182">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="b5a54-183">Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b5a54-183">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="b5a54-184">Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-184">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="b5a54-185">Pour plus d’informations, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b5a54-185">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="b5a54-186">Pour copier une règle de traduction existante qui servira de point de départ à la définition d’une nouvelle règle, cliquez sur son nom, sur **Copier**, puis sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-186">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="b5a54-187">Pour plus d’informations, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="b5a54-187">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="b5a54-188">Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-188">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="caution" alt="security" /><span data-ttu-id="b5a54-190">Note de sécurité :</span><span class="sxs-lookup"><span data-stu-id="b5a54-190">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="b5a54-191">N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit.</span><span class="sxs-lookup"><span data-stu-id="b5a54-191">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. <span data-ttu-id="b5a54-p126">(Facultatif) Associez et configurez les **règles de traduction de numéro appelé** pour la jonction. Les règles de traduction s’appliquent au numéro appelé dans un appel sortant.</span><span class="sxs-lookup"><span data-stu-id="b5a54-p126">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="b5a54-194">Pour choisir une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-194">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="b5a54-195">Dans **Sélectionner les règles de traduction**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-195">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="b5a54-196">Si vous voulez définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-196">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="b5a54-197">Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b5a54-197">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="b5a54-198">Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-198">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="b5a54-199">Pour plus d’informations, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b5a54-199">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="b5a54-200">Pour copier une règle de traduction existante qui servira de point de départ à la définition d’une nouvelle règle, cliquez sur son nom, sur **Copier**, puis sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-200">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="b5a54-201">Pour plus d’informations, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="b5a54-201">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="b5a54-202">Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-202">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b5a54-203">N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit.</span><span class="sxs-lookup"><span data-stu-id="b5a54-203">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="b5a54-204">Assurez-vous que les règles de traduction de la jonction sont organisées dans le bon ordre.</span><span class="sxs-lookup"><span data-stu-id="b5a54-204">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="b5a54-205">Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.</span><span class="sxs-lookup"><span data-stu-id="b5a54-205">To change a rule’s position in the list, highlight the rule name, and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b5a54-206">Lync Server parcourt la liste de règles de traduction du haut vers le bas et utilise la première règle qui correspond au numéro composé.</span><span class="sxs-lookup"><span data-stu-id="b5a54-206">Lync Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="b5a54-207">Si vous configurez une jonction de sorte qu’un numéro composé corresponde à plusieurs règles de traduction, assurez-vous que les règles les plus restrictives apparaissent avant les règles les moins restrictives.</span><span class="sxs-lookup"><span data-stu-id="b5a54-207">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="b5a54-208">Par exemple, si une règle de traduction s’applique à tout numéro à 11 chiffres et une autre s’applique à tout numéro à 11 chiffres commençant par +1425, assurez-vous que la règle qui s’applique à tout numéro à 11 chiffres apparaît <EM>après</EM> la règle la plus restrictive.</span><span class="sxs-lookup"><span data-stu-id="b5a54-208">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

18. <span data-ttu-id="b5a54-209">Lorsque vous avez terminé de configurer la jonction, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-209">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="b5a54-210">Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="b5a54-210">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b5a54-211">À chaque fois que vous créez ou modifiez une configuration de jonction, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="b5a54-211">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="b5a54-212">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="b5a54-212">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b5a54-213">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b5a54-213">See Also</span></span>


[<span data-ttu-id="b5a54-214">Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5a54-214">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="b5a54-215">Définition de règles de conversion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5a54-215">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

