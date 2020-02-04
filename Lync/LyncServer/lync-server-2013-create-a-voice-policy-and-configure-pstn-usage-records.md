---
title: 'Lync Server 2013 : création d’une stratégie vocale et configuration des enregistrements d’utilisation RTC'
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
ms.openlocfilehash: 80537aabe132f1b83714d42244409224ca53f72d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="50cf2-102">Créer une stratégie de voix et configurer les enregistrements d’utilisation RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50cf2-102">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50cf2-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="50cf2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="50cf2-104">Suivez ces étapes si vous voulez créer une nouvelle politique vocale.</span><span class="sxs-lookup"><span data-stu-id="50cf2-104">Follow these steps if you want to create a new voice policy.</span></span> <span data-ttu-id="50cf2-105">Pour modifier une stratégie vocale, voir [modifier une stratégie vocale et configurer les enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) pour la procédure.</span><span class="sxs-lookup"><span data-stu-id="50cf2-105">If you want to edit a voice policy, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="50cf2-106">Chaque stratégie vocale doit avoir au moins un enregistrement d’utilisation de réseau téléphonique commuté (PSTN) associé.</span><span class="sxs-lookup"><span data-stu-id="50cf2-106">Each voice policy must have at least one associated public switched telephone network (PSTN) usage record.</span></span> <span data-ttu-id="50cf2-107">Pour afficher une liste de tous les enregistrements d’utilisation RTC disponibles dans le déploiement de votre voix entreprise et afficher leurs propriétés, voir <A href="lync-server-2013-view-pstn-usage-records.md">afficher les enregistrements d’utilisation RTC dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="50cf2-107">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-voice-policy"></a><span data-ttu-id="50cf2-108">Pour créer une stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="50cf2-108">To create a voice policy</span></span>

1.  <span data-ttu-id="50cf2-109">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="50cf2-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="50cf2-110">Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="50cf2-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="50cf2-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50cf2-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="50cf2-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="50cf2-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="50cf2-113">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Stratégie de voix**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-113">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="50cf2-114">Dans la page **Stratégie de voix**, cliquez sur **Nouveau** puis sélectionnez l’étendue de la nouvelle stratégie :</span><span class="sxs-lookup"><span data-stu-id="50cf2-114">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>
    
      - <span data-ttu-id="50cf2-p105">La **stratégie de site** s’applique à l’ensemble d’un site, à l’exception des utilisateurs ou des groupes attribués à une stratégie d’utilisateur. Si vous sélectionnez l’étendue Site pour une stratégie, sélectionnez le site dans la boîte de dialogue **Sélectionner un site**. Si une stratégie de voix a déjà été créée pour un site, le site ne s’affiche pas dans la boîte de dialogue **Sélectionner un site**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-p105">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy. If you select Site for a policy scope, choose the site from the **Select a Site** dialog box. If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="50cf2-118">Une **stratégie d’utilisateur** peut être appliquée à des utilisateurs ou à des groupes spécifiés.</span><span class="sxs-lookup"><span data-stu-id="50cf2-118">**User policy** can be applied to specified users or groups.</span></span>

5.  <span data-ttu-id="50cf2-119">Si l’étendue de la stratégie de voix est Utilisateur, entrez un nom décrivant la stratégie dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-119">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="50cf2-120">Si l’étendue de la stratégie de voix est Site, le champ <STRONG>Nom</STRONG> de la boîte de dialogue <STRONG>Nouvelle stratégie de voix</STRONG> est prérempli avec le nom du site et ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="50cf2-120">If the voice policy scope is Site, the <STRONG>Name</STRONG> field in <STRONG>New Voice Policy</STRONG> is prepopulated with the site name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="50cf2-121">(Facultatif) Entrez une description supplémentaire de la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="50cf2-121">(Optional) Enter additional descriptive information for the voice policy.</span></span>

7.  <span data-ttu-id="50cf2-122">Activez ou désactivez les cases à cocher ci-dessous pour activer ou désactiver chacune des **fonctionnalités d’appel** pour cette stratégie de voix :</span><span class="sxs-lookup"><span data-stu-id="50cf2-122">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>
    
      - <span data-ttu-id="50cf2-123">**Redirection vers la messagerie vocale** empêche les appels d’être routés immédiatement vers le système de messagerie vocale du téléphone mobile de l’utilisateur lorsque la sonnerie simultanée est configurée et que le téléphone est éteint, déchargé ou en dehors de la plage.</span><span class="sxs-lookup"><span data-stu-id="50cf2-123">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="50cf2-124">Cette fonctionnalité est configurable uniquement via Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="50cf2-124">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="50cf2-125">**Transfert d’appel** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients.</span><span class="sxs-lookup"><span data-stu-id="50cf2-125">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="50cf2-126">Lync Server 2013 fournit une gamme d’options de configuration considérablement plus large pour le renvoi d’appel.</span><span class="sxs-lookup"><span data-stu-id="50cf2-126">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="50cf2-127">Par exemple, si une entreprise ne souhaite pas autoriser le transfert des appels entrants en externe vers le RTC, un administrateur peut appliquer une stratégie de voix spéciale pour déployer cette restriction.</span><span class="sxs-lookup"><span data-stu-id="50cf2-127">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="50cf2-128">Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="50cf2-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="50cf2-129">**Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place.</span><span class="sxs-lookup"><span data-stu-id="50cf2-129">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="50cf2-130">Dans Lync Server 2013, un délégué peut configurer une sonnerie simultanée qui permet aux appels entrants vers son responsable de sonner dans toutes les cibles de sonnerie simultanées du délégué.</span><span class="sxs-lookup"><span data-stu-id="50cf2-130">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="50cf2-131">Celui-ci bénéficie ainsi d’une plus grande flexibilité pour répondre aux appels destinés au responsable.</span><span class="sxs-lookup"><span data-stu-id="50cf2-131">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="50cf2-132">Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="50cf2-132">Enabled by default.</span></span>
    
      - <span data-ttu-id="50cf2-p108">**Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Cette fonctionnalité est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="50cf2-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="50cf2-p109">**Parcage d’appel** permet aux utilisateurs de parquer des appels en attente, puis de les reprendre avec un autre téléphone ou client. Cette fonctionnalité est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="50cf2-p109">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="50cf2-137">**Sonnerie simultanée** permet de faire sonner les appels entrants sur des téléphones supplémentaires (par exemple, un téléphone portable) ou d’autres périphériques de point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="50cf2-137">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="50cf2-138">Lync Server 2013 offre une large gamme d’options de configuration pour la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="50cf2-138">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="50cf2-139">Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="50cf2-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="50cf2-140">**Appel d’équipe** permet aux utilisateurs d’une équipe définie de répondre aux appels destinés à d’autres membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="50cf2-140">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="50cf2-141">Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="50cf2-141">Enabled by default.</span></span>
    
      - <span data-ttu-id="50cf2-142">Le **rétablissement RTC** permet aux utilisateurs qui sont affectés à cette stratégie d’être redirigés vers le réseau téléphonique public commuté (RTC) si le WAN est encombré ou indisponible.</span><span class="sxs-lookup"><span data-stu-id="50cf2-142">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable.</span></span> <span data-ttu-id="50cf2-143">Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="50cf2-143">Enabled by default.</span></span>
    
      - <span data-ttu-id="50cf2-p113">**Remplacement de stratégie de bande passante** permet aux administrateurs de remplacer les décisions de stratégie du contrôle d’admission des appels pour un utilisateur particulier. Cette fonctionnalité est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="50cf2-p113">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="50cf2-p114">La stratégie ne sera remplacée que pour les appels entrants vers l’utilisateur et non pour les appels sortants passés par l’utilisateur. Une fois la session établie, la consommation de bande passante est enregistrée avec précision. Ce paramètre doit être utilisé avec modération et doit être réservé à des décisions appropriées en matière de contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="50cf2-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

        
        </div>
    
      - <span data-ttu-id="50cf2-149">Le **suivi des appels malveillants** permet aux utilisateurs de signaler des appels malveillants (par exemple, des menaces de bombes) à l’aide de l’interface utilisateur du client, qui à son tour indique les appels dans les enregistrements des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="50cf2-149">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) by using the client UI, which in turn flags the calls in the call detail records (CDRs).</span></span> <span data-ttu-id="50cf2-150">Cette fonctionnalité est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="50cf2-150">Disabled by default.</span></span>

8.  <span data-ttu-id="50cf2-151">Pour associer et configurer des enregistrements d’utilisation RTC pour cette stratégie de voix, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="50cf2-151">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="50cf2-p116">Pour sélectionner un ou plusieurs enregistrements dans une liste de tous les enregistrements d’utilisation RTC disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette stratégie de voix, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="50cf2-154">Pour supprimer un enregistrement d’utilisation RTC de cette stratégie de voix, sélectionnez l’enregistrement et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-154">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="50cf2-155">Pour définir un nouvel enregistrement d’utilisation RTC et l’associer à cette stratégie de voix, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="50cf2-155">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="50cf2-156">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-156">Click **New**.</span></span>
        
        2.  <span data-ttu-id="50cf2-p117">Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement. Par exemple, vous pouvez créer un enregistrement d’utilisation RTC appelé **Redmond** pour les employés qui travaillent à plein temps à Redmond et un autre appelé **RedmondTemps** pour les employés qui travaillent à temps partiel.</span><span class="sxs-lookup"><span data-stu-id="50cf2-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="50cf2-p118">Le nom de l’enregistrement d’utilisation RTC doit être unique dans le déploiement Voix Entreprise. Une fois l’enregistrement enregistré, le champ <STRONG>Nom</STRONG> ne peut plus être modifié.</span><span class="sxs-lookup"><span data-stu-id="50cf2-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="50cf2-161">Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :</span><span class="sxs-lookup"><span data-stu-id="50cf2-161">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="50cf2-162">Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-162">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="50cf2-163">Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-163">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="50cf2-164">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-164">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="50cf2-165">Pour plus d’informations, reportez-vous à [créer un itinéraire vocal dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="50cf2-165">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="50cf2-166">Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-166">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="50cf2-167">Pour plus d’informations, voir [modifier un itinéraire vocal dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="50cf2-167">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="50cf2-168">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-168">Click **OK**.</span></span>
    
      - <span data-ttu-id="50cf2-169">Pour modifier un enregistrement d’utilisation RTC déjà associé à cette stratégie de voix, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="50cf2-169">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="50cf2-170">Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-170">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>
        
        2.  <span data-ttu-id="50cf2-171">Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :</span><span class="sxs-lookup"><span data-stu-id="50cf2-171">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="50cf2-172">Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-172">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="50cf2-173">Pour supprimer un itinéraire de cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-173">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="50cf2-174">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-174">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="50cf2-175">Pour plus d’informations, reportez-vous à [créer un itinéraire vocal dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="50cf2-175">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="50cf2-176">Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-176">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span> <span data-ttu-id="50cf2-177">Pour plus d’informations, voir [modifier un itinéraire vocal dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="50cf2-177">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="50cf2-178">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-178">Click **OK**.</span></span>

9.  <span data-ttu-id="50cf2-p123">Organisez les enregistrements d’utilisation RTC pour obtenir des performances optimales. Pour modifier la position d’un enregistrement dans la liste, sélectionnez son nom, puis cliquez sur la flèche vers le haut ou vers le bas.</span><span class="sxs-lookup"><span data-stu-id="50cf2-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="50cf2-181">L’ordre dans lequel les enregistrements d’utilisation RTC apparaissent dans la stratégie vocale est significatif.</span><span class="sxs-lookup"><span data-stu-id="50cf2-181">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="50cf2-182">Lync Server parcourt la liste du haut vers le bas.</span><span class="sxs-lookup"><span data-stu-id="50cf2-182">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="50cf2-183">Nous vous recommandons d’organiser la liste en fonction de la fréquence d’utilisation, par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="50cf2-183">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

10. <span data-ttu-id="50cf2-184">Pour associer et configurer les enregistrements d’utilisation RTC pour cette stratégie de voix, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="50cf2-184">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="50cf2-185">Pour utiliser les mêmes enregistrements d’utilisation RTC pour le transfert d’appels et la sonnerie simultanée que cette stratégie de voix, sélectionnez l’option **Router à l’aide des utilisations RTC d’appel** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="50cf2-185">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="50cf2-186">Pour autoriser le transfert d’appel et la sonnerie simultanée aux utilisateurs de Lync internes uniquement, sélectionnez l’option **acheminer uniquement vers les utilisateurs internes de Lync** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="50cf2-186">To allow call forwarding and simultaneous ringing to internal Lync users only, select the option **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="50cf2-187">Calls will not be forwarded to external PSTN numbers.</span><span class="sxs-lookup"><span data-stu-id="50cf2-187">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="50cf2-p126">Pour spécifier des enregistrements d’utilisation RTC pour le transfert d’appels et la sonnerie simultanée différents de ceux utilisés pour cette stratégie de voix, sélectionnez l’option **Router à l’aide d’utilisations RTC personnalisées** dans le menu déroulant. Cette option affiche un contrôle pour sélectionner des enregistrements d’utilisation RTC existants ou créer des enregistrements d’utilisation RTC spécifiquement pour le transfert d’appels et la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="50cf2-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="50cf2-p127">Pour sélectionner un ou plusieurs enregistrements dans une liste des enregistrements d’utilisation RTC pour le transfert d’appels et la sonnerie simultanée, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette stratégie de transfert d’appels et de sonnerie simultanée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="50cf2-192">Pour supprimer un enregistrement d’utilisation RTC de cette stratégie de transfert d’appels et de sonnerie simultanée, sélectionnez l’enregistrement et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-192">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="50cf2-193">Pour définir un nouvel enregistrement d’utilisation RTC et l’associer à cette stratégie de transfert d’appels et de sonnerie simultanée, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="50cf2-193">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="50cf2-194">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-194">Click **New**.</span></span>
            
            2.  <span data-ttu-id="50cf2-195">Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="50cf2-195">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="50cf2-p128">Le nom de l’enregistrement d’utilisation RTC doit être unique dans le déploiement Voix Entreprise. Une fois que vous avez enregistré l’enregistrement, vous ne pouvez plus modifier le champ <STRONG>Nom</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="50cf2-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="50cf2-198">Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :</span><span class="sxs-lookup"><span data-stu-id="50cf2-198">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="50cf2-199">Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-199">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="50cf2-200">Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-200">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="50cf2-201">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-201">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="50cf2-202">Pour plus d’informations, reportez-vous à [créer un itinéraire vocal dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="50cf2-202">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="50cf2-203">Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-203">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="50cf2-204">Pour plus d’informations, voir [modifier un itinéraire vocal dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="50cf2-204">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="50cf2-205">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-205">Click **OK**.</span></span>
        
          - <span data-ttu-id="50cf2-206">Pour modifier un enregistrement d’utilisation RTC déjà associé à cette stratégie de voix, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="50cf2-206">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="50cf2-207">Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-207">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="50cf2-208">Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :</span><span class="sxs-lookup"><span data-stu-id="50cf2-208">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="50cf2-209">Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-209">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="50cf2-210">Pour supprimer un itinéraire de cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-210">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="50cf2-211">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-211">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="50cf2-212">Pour plus d’informations, reportez-vous à [créer un itinéraire vocal dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="50cf2-212">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="50cf2-213">Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-213">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="50cf2-214">Pour plus d’informations, voir [modifier un itinéraire vocal dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="50cf2-214">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="50cf2-215">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-215">Click **OK**.</span></span>

11. <span data-ttu-id="50cf2-p133">(Facultatif) Entrez un numéro pour tester la stratégie de voix, puis cliquez sur **OK**. Les résultats du test s’affichent dans **Numéro converti à tester**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="50cf2-218">Vous pouvez enregistrer une stratégie de voix qui ne transmet pas encore le test et la reconfigurer plus tard.</span><span class="sxs-lookup"><span data-stu-id="50cf2-218">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="50cf2-219">Pour plus d’informations, consultez <A href="lync-server-2013-test-voice-routing.md">tester le routage vocal dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="50cf2-219">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="50cf2-220">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-220">Click **OK**.</span></span>

13. <span data-ttu-id="50cf2-221">Dans la page **Stratégie de voix**, cliquez sur **Valider**, puis sur **Tout valider**.</span><span class="sxs-lookup"><span data-stu-id="50cf2-221">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="50cf2-222">Chaque fois que vous créez ou modifiez une stratégie de voix, vous devez exécuter la commande <STRONG>Tout valider</STRONG> pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="50cf2-222">Any time you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="50cf2-223">Pour plus d’informations, reportez-vous <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">à la rubrique publier des modifications en attente sur la configuration de l’acheminement de la voix dans Lync Server 2013</A> dans la documentation</span><span class="sxs-lookup"><span data-stu-id="50cf2-223">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

14. <span data-ttu-id="50cf2-224">(Facultatif) La redirection vers la messagerie vocale détecte qu’un appel a été intercepté immédiatement par la messagerie vocale du téléphone portable de l’utilisateur et déconnecte l’appel de la messagerie vocale du téléphone portable.</span><span class="sxs-lookup"><span data-stu-id="50cf2-224">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="50cf2-225">L’appel continue de sonner sur les autres points de terminaison de l’utilisateur pour lui permettre de répondre.</span><span class="sxs-lookup"><span data-stu-id="50cf2-225">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="50cf2-226">Pour plus d’informations sur la configuration d’une stratégie de messagerie vocale, consultez la rubrique [configuration de l’échappement de la messagerie vocale dans Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span><span class="sxs-lookup"><span data-stu-id="50cf2-226">For details on how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50cf2-227">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="50cf2-227">See Also</span></span>


[<span data-ttu-id="50cf2-228">Modifier une stratégie vocale et configurer les enregistrements d’utilisation RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50cf2-228">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="50cf2-229">Afficher les enregistrements d’utilisation RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50cf2-229">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="50cf2-230">Créer un itinéraire vocal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50cf2-230">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="50cf2-231">Modifier un itinéraire vocal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50cf2-231">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="50cf2-232">Publier les modifications en attente apportées à la configuration du routage de la voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50cf2-232">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="50cf2-233">Configuration de l’échappement de la messagerie vocale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50cf2-233">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="50cf2-234">Test du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50cf2-234">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

