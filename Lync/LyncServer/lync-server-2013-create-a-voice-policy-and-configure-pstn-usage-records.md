---
title: 'Lync Server 2013 : création d’une stratégie de voix et configuration des enregistrements d’utilisation PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice policy and configure PSTN usage records
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399027(v=OCS.15)
ms:contentKeyID: 48185693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbf6a0c8e6d1d2e72ba7381af41fe86f645b827d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501831"
---
# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="17991-102">Création d’une stratégie de voix et configuration des enregistrements d’utilisation PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17991-102">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17991-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="17991-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="17991-104">Procédez comme suit pour créer une stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="17991-104">Follow these steps if you want to create a new voice policy.</span></span> <span data-ttu-id="17991-105">Si vous souhaitez modifier une stratégie de voix, voir [modifier une stratégie de voix et configurer les enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) pour la procédure.</span><span class="sxs-lookup"><span data-stu-id="17991-105">If you want to edit a voice policy, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17991-106">Chaque stratégie de voix doit être associée à au moins un enregistrement d’utilisation réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="17991-106">Each voice policy must have at least one associated public switched telephone network (PSTN) usage record.</span></span> <span data-ttu-id="17991-107">Pour afficher la liste de tous les enregistrements d’utilisation RTC disponibles dans votre déploiement voix entreprise et afficher leurs propriétés, voir <A href="lync-server-2013-view-pstn-usage-records.md">afficher les enregistrements d’utilisation PSTN dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="17991-107">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-voice-policy"></a><span data-ttu-id="17991-108">Pour créer une stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="17991-108">To create a voice policy</span></span>

1.  <span data-ttu-id="17991-109">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="17991-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="17991-110">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="17991-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="17991-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="17991-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="17991-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="17991-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="17991-113">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Stratégie de la voix**.</span><span class="sxs-lookup"><span data-stu-id="17991-113">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="17991-114">Dans la page **Stratégie de la voix**, cliquez sur **Nouveau** puis sélectionnez l’étendue de la nouvelle stratégie :</span><span class="sxs-lookup"><span data-stu-id="17991-114">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>
    
      - <span data-ttu-id="17991-p105">La **stratégie de site** s’applique à l’ensemble d’un site, à l’exception des utilisateurs ou groupes attribués à une stratégie d’utilisateur. Si vous sélectionnez l’étendue Site pour une stratégie, choisissez le site dans la boîte de dialogue **Sélectionner un site**. Si une stratégie de voix a déjà été créée pour un site, le site n’apparaît pas dans la boîte de dialogue **Sélectionner un site**.</span><span class="sxs-lookup"><span data-stu-id="17991-p105">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy. If you select Site for a policy scope, choose the site from the **Select a Site** dialog box. If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="17991-118">Une **stratégie d’utilisateur** peut être appliquée à des utilisateurs ou à des groupes spécifiés.</span><span class="sxs-lookup"><span data-stu-id="17991-118">**User policy** can be applied to specified users or groups.</span></span>

5.  <span data-ttu-id="17991-119">Si l’étendue de la stratégie de voix est Utilisateur, entrez un nom descriptif de la stratégie dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="17991-119">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="17991-120">Si l’étendue de la stratégie de voix est Site, le champ <STRONG>Nom</STRONG> de la boîte de dialogue <STRONG>Nouvelle stratégie de voix</STRONG> est prérempli avec le nom du site et ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="17991-120">If the voice policy scope is Site, the <STRONG>Name</STRONG> field in <STRONG>New Voice Policy</STRONG> is prepopulated with the site name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="17991-121">(Optionnel) Entrez une description supplémentaire de la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="17991-121">(Optional) Enter additional descriptive information for the voice policy.</span></span>

7.  <span data-ttu-id="17991-122">Activez ou désactivez les cases à cocher suivantes pour activer ou désactiver chacune des **fonctionnalités d’appel** pour cette stratégie de voix :</span><span class="sxs-lookup"><span data-stu-id="17991-122">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>
    
      - <span data-ttu-id="17991-123">**Voice mail escape** empêche les appels d’être immédiatement routés vers le système de messagerie vocale du téléphone mobile de l’utilisateur lorsque la sonnerie simultanée est configurée et que le téléphone est éteint, déchargé ou en dehors de la plage.</span><span class="sxs-lookup"><span data-stu-id="17991-123">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="17991-124">Cette fonctionnalité est configurable uniquement par le biais de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="17991-124">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="17991-125">**Transfert d’appel** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients.</span><span class="sxs-lookup"><span data-stu-id="17991-125">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="17991-126">Lync Server 2013 offre un large éventail d’options de configuration pour le transfert d’appel.</span><span class="sxs-lookup"><span data-stu-id="17991-126">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="17991-127">Par exemple, si une organisation ne souhaite pas autoriser le transfert des appels entrants à l’extérieur vers le réseau téléphonique commuté (PSTN), un administrateur peut appliquer une stratégie de voix spéciale pour déployer cette restriction.</span><span class="sxs-lookup"><span data-stu-id="17991-127">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="17991-128">Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="17991-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="17991-129">**Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place.</span><span class="sxs-lookup"><span data-stu-id="17991-129">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="17991-130">Dans Lync Server 2013, un délégué peut configurer la sonnerie simultanée qui permet aux appels entrants vers son responsable de sonner dans toutes les cibles de sonnerie simultanées du délégué.</span><span class="sxs-lookup"><span data-stu-id="17991-130">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="17991-131">Le délégué peut ainsi répondre avec une plus grande souplesse aux appels destinés au responsable.</span><span class="sxs-lookup"><span data-stu-id="17991-131">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="17991-132">Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="17991-132">Enabled by default.</span></span>
    
      - <span data-ttu-id="17991-p108">**Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="17991-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="17991-p109">**Parcage d’appel** permet aux utilisateurs de parquer des appels en attente, puis de les reprendre depuis un autre téléphone ou client. Désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="17991-p109">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="17991-137">**Sonnerie simultanée** permet aux appels entrants de sonner sur des téléphones supplémentaires (par exemple, un téléphone mobile) ou d’autres périphériques de système d’extrémité.</span><span class="sxs-lookup"><span data-stu-id="17991-137">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="17991-138">Lync Server 2013 offre un large éventail d’options de configuration pour la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="17991-138">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="17991-139">Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="17991-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="17991-p111">**Appel d’équipe** permet aux utilisateurs d’une équipe définie de répondre aux appels destinés à d’autres membres de l’équipe. Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="17991-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>
    
      - <span data-ttu-id="17991-p112">**Réacheminement PSTN** permet aux appels des utilisateurs (auxquels cette stratégie est affectée) destinés à d’autres utilisateurs de l’entreprise d’être réacheminés sur le réseau téléphonique commuté (PSTN) si le réseau étendu (WAN) est saturé ou indisponible. Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="17991-p112">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>
    
      - <span data-ttu-id="17991-p113">Le **remplacement de stratégie de bande passante** permet aux administrateurs de remplacer les décisions de stratégie du contrôle d’admission des appels pour un utilisateur particulier. Désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="17991-p113">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="17991-p114">La stratégie sera uniquement remplacée pour les appels entrants vers l’utilisateur et non pour les appels sortants qui sont passés par l’utilisateur. Une fois la session établie, la consommation de bande passante est précisément enregistrée. Ce paramètre doit être utilisé avec modération et doit être réservé à la prise de décision appropriée en matière de contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="17991-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

        
        </div>
    
      - <span data-ttu-id="17991-p115">**Suivi des appels malveillants** permet aux utilisateurs de consigner des appels malveillants (comme une alerte à la bombe) à l’aide de l’interface utilisateur du client, qui signale ensuite ces appels dans les enregistrements des détails des appels (CDR). Désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="17991-p115">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) by using the client UI, which in turn flags the calls in the call detail records (CDRs). Disabled by default.</span></span>

8.  <span data-ttu-id="17991-151">Afin d’associer et de configurer des enregistrements d’utilisation PSTN pour cette stratégie de voix, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="17991-151">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="17991-p116">Pour choisir un ou plusieurs enregistrements dans une liste de tous les enregistrements d’utilisation PSTN disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette stratégie de voix, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="17991-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="17991-154">Pour supprimer un enregistrement d’utilisation PSTN de cette stratégie de voix, sélectionnez l’enregistrement et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="17991-154">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="17991-155">Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette stratégie de voix, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="17991-155">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="17991-156">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="17991-156">Click **New**.</span></span>
        
        2.  <span data-ttu-id="17991-p117">Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement. Par exemple, vous pouvez créer un enregistrement d’utilisation PSTN appelé **Redmond** pour les employés qui travaillent à plein temps situés à Redmond et un autre appelé **RedmondTemps** pour les employés qui travaillent à temps partiel.</span><span class="sxs-lookup"><span data-stu-id="17991-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="17991-p118">Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ <STRONG>Nom</STRONG> ne peut plus être modifié.</span><span class="sxs-lookup"><span data-stu-id="17991-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="17991-161">Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :</span><span class="sxs-lookup"><span data-stu-id="17991-161">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="17991-162">Pour choisir un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="17991-162">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="17991-163">Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="17991-163">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="17991-164">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="17991-164">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="17991-165">Pour plus d’informations, consultez [la rubrique créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="17991-165">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="17991-166">Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="17991-166">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="17991-167">Pour plus d’informations, consultez [la rubrique modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="17991-167">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="17991-168">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="17991-168">Click **OK**.</span></span>
    
      - <span data-ttu-id="17991-169">Pour modifier un enregistrement d’utilisation PSTN qui est déjà associé à cette stratégie de voix, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="17991-169">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="17991-170">Sélectionnez l’enregistrement d’utilisation PSTN que vous voulez modifier, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="17991-170">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>
        
        2.  <span data-ttu-id="17991-171">Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :</span><span class="sxs-lookup"><span data-stu-id="17991-171">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="17991-172">Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="17991-172">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="17991-173">Pour supprimer un itinéraire de cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="17991-173">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="17991-174">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="17991-174">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="17991-175">Pour plus d’informations, consultez [la rubrique créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="17991-175">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="17991-176">Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="17991-176">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span> <span data-ttu-id="17991-177">Pour plus d’informations, consultez [la rubrique modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="17991-177">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="17991-178">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="17991-178">Click **OK**.</span></span>

9.  <span data-ttu-id="17991-p123">Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez le nom de l’enregistrement, puis cliquez sur la flèche vers le haut ou vers le bas.</span><span class="sxs-lookup"><span data-stu-id="17991-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="17991-181">L’ordre dans lequel les enregistrements d’utilisation apparaissent dans la stratégie de voix est essentiel.</span><span class="sxs-lookup"><span data-stu-id="17991-181">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="17991-182">Lync Server parcourt la liste du haut vers le bas.</span><span class="sxs-lookup"><span data-stu-id="17991-182">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="17991-183">Nous vous conseillons d’organiser la liste par fréquence d’utilisation ; par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="17991-183">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

10. <span data-ttu-id="17991-184">Afin d’associer et de configurer des enregistrements d’utilisation PSTN pour le transfert d’appel et la sonnerie simultanée dans cette stratégie de voix, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="17991-184">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="17991-185">Pour utiliser les mêmes enregistrements d’utilisation PSTN pour le transfert d’appels et la sonnerie simultanée que cette stratégie de voix, sélectionnez l’option **Acheminer à l’aide des utilisations PSTN d’appel** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="17991-185">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="17991-p125">Pour activer le transfert d’appels et la sonnerie simultanée pour les utilisateurs internes de Lync uniquement, sélectionnez l’option **Acheminer vers les utilisateurs internes de Lync uniquement** dans le menu déroulant. Les appels ne seront pas transférés vers des numéros PSTN externes.</span><span class="sxs-lookup"><span data-stu-id="17991-p125">To allow call forwarding and simultaneous ringing to internal Lync users only, select the option **Route to internal Lync users only** from the drop-down menu. Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="17991-p126">Pour spécifier des enregistrements d’utilisation PSTN pour le transfert d’appels et la sonnerie simultanée différents de ceux utilisés pour cette stratégie de voix, sélectionnez l’option **Acheminer à l’aide d’utilisations PSTN personnalisées** dans le menu déroulant. Cette option affiche un contrôle pour sélectionner des enregistrements d’utilisation PSTN existants ou créer des enregistrements d’utilisation PSTN spécifiquement pour le transfert d’appels et la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="17991-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="17991-p127">Pour choisir un ou plusieurs enregistrements dans une liste des enregistrements d’utilisation PSTN pour le transfert d’appels et la sonnerie simultanée, cliquez sur **Sélectionner**. Sélectionnez les enregistrements que vous voulez associer à cette stratégie de transfert d’appels et de sonnerie simultanée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="17991-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="17991-192">Pour supprimer un enregistrement d’utilisation PSTN de cette stratégie de transfert d’appel et de sonnerie simultanée, sélectionnez l’enregistrement et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="17991-192">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="17991-193">Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette stratégie de transfert d’appel et de sonnerie simultanée, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="17991-193">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="17991-194">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="17991-194">Click **New**.</span></span>
            
            2.  <span data-ttu-id="17991-195">Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="17991-195">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="17991-p128">Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ <STRONG>Nom</STRONG> ne peut plus être modifié.</span><span class="sxs-lookup"><span data-stu-id="17991-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="17991-198">Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :</span><span class="sxs-lookup"><span data-stu-id="17991-198">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="17991-199">Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="17991-199">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="17991-200">Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="17991-200">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="17991-201">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="17991-201">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="17991-202">Pour plus d’informations, consultez [la rubrique créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="17991-202">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="17991-203">Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="17991-203">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="17991-204">Pour plus d’informations, consultez [la rubrique modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="17991-204">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="17991-205">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="17991-205">Click **OK**.</span></span>
        
          - <span data-ttu-id="17991-206">Pour modifier un enregistrement d’utilisation PSTN déjà associé à cette stratégie de voix, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="17991-206">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="17991-207">Sélectionnez l’enregistrement d’utilisation PSTN à modifier, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="17991-207">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="17991-208">Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :</span><span class="sxs-lookup"><span data-stu-id="17991-208">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="17991-209">Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="17991-209">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="17991-210">Pour supprimer un itinéraire de cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="17991-210">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="17991-211">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="17991-211">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="17991-212">Pour plus d’informations, consultez [la rubrique créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="17991-212">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="17991-213">Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="17991-213">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="17991-214">Pour plus d’informations, consultez [la rubrique modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="17991-214">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="17991-215">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="17991-215">Click **OK**.</span></span>

11. <span data-ttu-id="17991-p133">(Facultatif) Entrez un numéro pour tester la stratégie de voix, puis cliquez sur **OK**. Les résultats du test apparaissent sous **Numéro traduit à tester**.</span><span class="sxs-lookup"><span data-stu-id="17991-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="17991-218">Vous pouvez enregistrer une stratégie de voix qui ne réussit pour l’instant pas le test, puis la reconfigurer ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="17991-218">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="17991-219">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-test-voice-routing.md">test de routage des communications vocales dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="17991-219">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="17991-220">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="17991-220">Click **OK**.</span></span>

13. <span data-ttu-id="17991-221">Dans la page **Stratégie de la voix**, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="17991-221">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="17991-222">À chaque fois que vous créez ou modifiez une stratégie de voix, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="17991-222">Any time you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="17991-223">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="17991-223">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

14. <span data-ttu-id="17991-224">(Facultatif) L’échappement de la messagerie vocale détecte qu’un appel a été immédiatement pris en charge par la messagerie vocale du téléphone mobile de l’utilisateur et déconnecte l’appel vers la messagerie vocale du téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="17991-224">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="17991-225">Cela permet à l’appel de continuer de sonner sur les autres systèmes d’extrémité de l’utilisateur, donnant ainsi à l’utilisateur la possibilité de répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="17991-225">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="17991-226">Pour plus d’informations sur la configuration d’une stratégie de messagerie vocale, reportez-vous à la rubrique [configuration de l’échappement de la messagerie vocale dans Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span><span class="sxs-lookup"><span data-stu-id="17991-226">For details on how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17991-227">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="17991-227">See Also</span></span>


[<span data-ttu-id="17991-228">Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17991-228">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="17991-229">Afficher les enregistrements d’utilisation RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17991-229">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="17991-230">Créer un itinéraire des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17991-230">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="17991-231">Modifier un itinéraire des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17991-231">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="17991-232">Publier les modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17991-232">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="17991-233">Configuration de l’échappement de la messagerie vocale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17991-233">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="17991-234">Tester le routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17991-234">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

