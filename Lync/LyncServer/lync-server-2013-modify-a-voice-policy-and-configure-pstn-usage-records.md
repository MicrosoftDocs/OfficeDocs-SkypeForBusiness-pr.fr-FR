---
title: 'Lync Server 2013 : modifiez une stratégie vocale et configurez les enregistrements d’utilisation RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dda549bbb8b1f29a3aef8690a8e666e7a182bd29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="cdd02-102">Modifier une stratégie vocale et configurer les enregistrements d’utilisation RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdd02-102">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdd02-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cdd02-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cdd02-104">Pour modifier une stratégie vocale, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="cdd02-104">Follow these steps if you want to modify a voice policy.</span></span> <span data-ttu-id="cdd02-105">Si vous voulez créer une nouvelle stratégie vocale, voir [créer une stratégie vocale et configurer les enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) pour la procédure.</span><span class="sxs-lookup"><span data-stu-id="cdd02-105">If you want to create a new voice policy, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cdd02-106">Si un utilisateur est affecté à une stratégie vocale et qu’aucun enregistrement d’utilisation de réseau téléphonique commuté (PSTN) n’est associé, l’utilisateur ne peut pas passer d’appel sortant.</span><span class="sxs-lookup"><span data-stu-id="cdd02-106">If a user is assigned to a voice policy has no associated public switched telephone network (PSTN) usage records, the user cannot place outbound calls.</span></span> <span data-ttu-id="cdd02-107">Pour obtenir la liste de tous les enregistrements d’utilisation RTC disponibles dans le déploiement de votre voix entreprise et afficher leurs propriétés, voir <A href="lync-server-2013-view-pstn-usage-records.md">afficher les enregistrements d’utilisation RTC dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cdd02-107">For a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-modify-a-voice-policy"></a><span data-ttu-id="cdd02-108">Pour modifier une stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="cdd02-108">To modify a voice policy</span></span>

1.  <span data-ttu-id="cdd02-109">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cdd02-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="cdd02-110">Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="cdd02-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="cdd02-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cdd02-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cdd02-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cdd02-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cdd02-113">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Stratégie de voix**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-113">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="cdd02-114">Dans la page **Stratégie de voix**, double-cliquez sur le nom d’une stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="cdd02-114">On the **Voice Policy** page, double-click a voice policy name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cdd02-p105">L’étendue et le nom ont été définis lors de la création de la stratégie de voix. Ils ne peuvent pas être modifiés.</span><span class="sxs-lookup"><span data-stu-id="cdd02-p105">The scope and name were set when the voice policy was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="cdd02-117">(Facultatif) Dans **Modifier la stratégie de voix**, entrez d’autres informations décrivant la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="cdd02-117">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

6.  <span data-ttu-id="cdd02-118">Activez ou désactivez les cases à cocher ci-dessous pour activer ou désactiver chacune des **fonctionnalités d’appel** :</span><span class="sxs-lookup"><span data-stu-id="cdd02-118">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>
    
      - <span data-ttu-id="cdd02-119">**Redirection vers la messagerie vocale** empêche les appels d’être routés immédiatement vers le système de messagerie vocale du téléphone mobile de l’utilisateur lorsque la sonnerie simultanée est configurée et que le téléphone est éteint, déchargé ou en dehors de la plage.</span><span class="sxs-lookup"><span data-stu-id="cdd02-119">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cdd02-120">Cette fonctionnalité est configurable uniquement via Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="cdd02-120">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="cdd02-121">**Transfert d’appel** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients.</span><span class="sxs-lookup"><span data-stu-id="cdd02-121">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="cdd02-122">Lync Server 2013 fournit une gamme d’options de configuration considérablement plus large pour le renvoi d’appel.</span><span class="sxs-lookup"><span data-stu-id="cdd02-122">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="cdd02-123">Par exemple, si une entreprise ne souhaite pas autoriser le transfert des appels entrants en externe vers le RTC, un administrateur peut appliquer une stratégie de voix spéciale pour déployer cette restriction.</span><span class="sxs-lookup"><span data-stu-id="cdd02-123">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="cdd02-124">Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="cdd02-124">Enabled by default.</span></span>
    
      - <span data-ttu-id="cdd02-125">**Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place.</span><span class="sxs-lookup"><span data-stu-id="cdd02-125">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="cdd02-126">Dans Lync Server 2013, un délégué peut configurer une sonnerie simultanée qui permet aux appels entrants vers son responsable de sonner dans toutes les cibles de sonnerie simultanées du délégué.</span><span class="sxs-lookup"><span data-stu-id="cdd02-126">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="cdd02-127">Celui-ci bénéficie ainsi d’une plus grande flexibilité pour répondre aux appels destinés au responsable.</span><span class="sxs-lookup"><span data-stu-id="cdd02-127">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="cdd02-128">Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="cdd02-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="cdd02-p108">**Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Cette fonctionnalité est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="cdd02-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="cdd02-p109">**Parcage d’appel** permet aux utilisateurs de parquer des appels en attente, puis de les reprendre avec un autre téléphone ou client. Cette fonctionnalité est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="cdd02-p109">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="cdd02-133">**Sonnerie simultanée** permet de faire sonner les appels entrants sur des téléphones supplémentaires (par exemple, un téléphone portable) ou d’autres périphériques de point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="cdd02-133">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="cdd02-134">Lync Server 2013 offre une large gamme d’options de configuration pour la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="cdd02-134">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="cdd02-135">Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="cdd02-135">Enabled by default.</span></span>
    
      - <span data-ttu-id="cdd02-136">**Appel d’équipe** permet aux utilisateurs d’une équipe définie de répondre aux appels destinés à d’autres membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="cdd02-136">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="cdd02-137">Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="cdd02-137">Enabled by default.</span></span>
    
      - <span data-ttu-id="cdd02-138">Le **rétablissement RTC** permet aux utilisateurs qui sont affectés à cette stratégie d’être redirigés vers le réseau téléphonique public commuté (RTC) si le WAN est encombré ou indisponible.</span><span class="sxs-lookup"><span data-stu-id="cdd02-138">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable.</span></span> <span data-ttu-id="cdd02-139">Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="cdd02-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="cdd02-140">Le **remplacement de la stratégie de bande passante** permet aux administrateurs de remplacer les décisions de stratégie d’admission des appels (CAC) pour un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="cdd02-140">**Bandwidth policy override** enables administrators to override call admission control (CAC) policy decisions for a particular user.</span></span> <span data-ttu-id="cdd02-141">Désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="cdd02-141">Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cdd02-p114">La stratégie n’est remplacée que pour les appels entrants vers l’utilisateur et non pour les appels sortants passés par l’utilisateur. Une fois la session établie, la consommation de bande passante est enregistrée avec précision. Ce paramètre doit être utilisé avec modération.</span><span class="sxs-lookup"><span data-stu-id="cdd02-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly.</span></span>

        
        </div>
    
      - <span data-ttu-id="cdd02-145">Le **suivi des appels malveillants** permet aux utilisateurs de signaler des appels malveillants (par exemple, des menaces de bombes) à l’aide de l’interface utilisateur du client, qui à son tour indique les appels dans les enregistrements des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="cdd02-145">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) using the client UI, which in turn flags the calls in the call detail records (CDRs).</span></span> <span data-ttu-id="cdd02-146">Cette fonctionnalité est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="cdd02-146">Disabled by default.</span></span>

7.  <span data-ttu-id="cdd02-147">Pour associer et configurer des enregistrements d’utilisation RTC pour cette stratégie de voix, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="cdd02-147">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="cdd02-p116">Pour sélectionner un ou plusieurs enregistrements dans une liste de tous les enregistrements d’utilisation RTC disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette stratégie de voix, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="cdd02-150">Pour supprimer un enregistrement d’utilisation RTC de cette stratégie de voix, sélectionnez l’enregistrement et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-150">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="cdd02-151">Pour définir un nouvel enregistrement d’utilisation RTC et l’associer à cette stratégie de voix, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="cdd02-151">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="cdd02-152">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-152">Click **New**.</span></span>
        
        2.  <span data-ttu-id="cdd02-p117">Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement. Par exemple, vous pouvez créer un enregistrement d’utilisation RTC appelé **Redmond** pour les employés qui travaillent à plein temps à Redmond et un autre appelé **RedmondTemps** pour les employés qui travaillent à temps partiel.</span><span class="sxs-lookup"><span data-stu-id="cdd02-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another record named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="cdd02-p118">Le nom de l’enregistrement d’utilisation RTC doit être unique dans le déploiement Voix Entreprise. Une fois que vous avez enregistré l’enregistrement, vous ne pouvez plus modifier le champ <STRONG>Nom</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="cdd02-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="cdd02-157">Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :</span><span class="sxs-lookup"><span data-stu-id="cdd02-157">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="cdd02-158">Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-158">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="cdd02-159">Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-159">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="cdd02-160">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-160">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="cdd02-161">Pour plus d’informations, reportez-vous à [créer un itinéraire vocal dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="cdd02-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="cdd02-162">Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-162">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="cdd02-163">Pour plus d’informations, voir [modifier un itinéraire vocal dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="cdd02-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="cdd02-164">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-164">Click **OK**.</span></span>
    
      - <span data-ttu-id="cdd02-165">Pour modifier un enregistrement d’utilisation RTC déjà associé à cette stratégie de voix, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="cdd02-165">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="cdd02-166">Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-166">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="cdd02-167">Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :</span><span class="sxs-lookup"><span data-stu-id="cdd02-167">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="cdd02-168">Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-168">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="cdd02-169">Pour supprimer un itinéraire de cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-169">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="cdd02-170">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-170">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="cdd02-171">Pour plus d’informations, reportez-vous à [créer un itinéraire vocal dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="cdd02-171">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="cdd02-172">Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-172">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="cdd02-173">Pour plus d’informations, voir [modifier un itinéraire vocal dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="cdd02-173">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="cdd02-174">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-174">Click **OK**.</span></span>

8.  <span data-ttu-id="cdd02-p123">Organisez les enregistrements d’utilisation RTC pour obtenir des performances optimales. Pour modifier la position d’un enregistrement dans la liste, sélectionnez son nom, puis cliquez sur la flèche vers le haut ou vers le bas.</span><span class="sxs-lookup"><span data-stu-id="cdd02-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cdd02-177">L’ordre dans lequel les enregistrements d’utilisation RTC apparaissent dans la stratégie vocale est significatif.</span><span class="sxs-lookup"><span data-stu-id="cdd02-177">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="cdd02-178">Lync Server parcourt la liste du haut vers le bas.</span><span class="sxs-lookup"><span data-stu-id="cdd02-178">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="cdd02-179">Nous vous recommandons d’organiser la liste en fonction de la fréquence d’utilisation, par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="cdd02-179">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

9.  <span data-ttu-id="cdd02-180">Pour associer et configurer les enregistrements d’utilisation RTC pour cette stratégie de voix, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="cdd02-180">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="cdd02-181">Pour utiliser les mêmes enregistrements d’utilisation RTC pour le transfert d’appels et la sonnerie simultanée que cette stratégie de voix, sélectionnez l’option **Router à l’aide des utilisations RTC d’appel** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="cdd02-181">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="cdd02-182">Pour autoriser le transfert d’appel et la sonnerie simultanée aux utilisateurs de Lync internes uniquement, sélectionnez **diriger vers les utilisateurs internes de Lync uniquement** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="cdd02-182">To allow call forwarding and simultaneous ringing to internal Lync users only, select **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="cdd02-183">Calls will not be forwarded to external PSTN numbers.</span><span class="sxs-lookup"><span data-stu-id="cdd02-183">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="cdd02-p126">Pour spécifier des enregistrements d’utilisation RTC pour le transfert d’appel et la sonnerie simultanée différents de ceux utilisés pour cette stratégie de voix, sélectionnez l’option **Routage avec des utilisations RTC personnalisées** dans le menu déroulant. Cette option affiche un contrôle pour sélectionner les enregistrements d’utilisation RTC existants ou créer des enregistrements d’utilisation RTC spécifiquement pour le transfert d’appel et la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="cdd02-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="cdd02-p127">Pour sélectionner un ou plusieurs enregistrements dans une liste des enregistrements d’utilisation RTC pour le transfert d’appels et la sonnerie simultanée, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette stratégie de transfert d’appels et de sonnerie simultanée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="cdd02-188">Pour supprimer un enregistrement d’utilisation RTC de cette stratégie de transfert d’appels et de sonnerie simultanée, sélectionnez l’enregistrement et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-188">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="cdd02-189">Pour définir un nouvel enregistrement d’utilisation RTC et l’associer à cette stratégie de transfert d’appels et de sonnerie simultanée, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="cdd02-189">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="cdd02-190">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-190">Click **New**.</span></span>
            
            2.  <span data-ttu-id="cdd02-191">Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="cdd02-191">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="cdd02-p128">Le nom de l’enregistrement d’utilisation RTC doit être unique dans le déploiement Voix Entreprise. Une fois que vous avez enregistré l’enregistrement, vous ne pouvez plus modifier le champ <STRONG>Nom</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="cdd02-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="cdd02-194">Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :</span><span class="sxs-lookup"><span data-stu-id="cdd02-194">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="cdd02-195">Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-195">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="cdd02-196">Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-196">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="cdd02-197">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-197">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="cdd02-198">Pour plus d’informations, reportez-vous à [créer un itinéraire vocal dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="cdd02-198">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="cdd02-199">Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-199">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="cdd02-200">Pour plus d’informations, voir [modifier un itinéraire vocal dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="cdd02-200">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="cdd02-201">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-201">Click **OK**.</span></span>
        
          - <span data-ttu-id="cdd02-202">Pour modifier un enregistrement d’utilisation RTC déjà associé à cette stratégie de voix, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="cdd02-202">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="cdd02-203">Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-203">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="cdd02-204">Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :</span><span class="sxs-lookup"><span data-stu-id="cdd02-204">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="cdd02-205">Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-205">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="cdd02-206">Pour supprimer un itinéraire de cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-206">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="cdd02-207">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-207">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="cdd02-208">Pour plus d’informations, reportez-vous à [créer un itinéraire vocal dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="cdd02-208">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="cdd02-209">Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-209">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="cdd02-210">Pour plus d’informations, voir [modifier un itinéraire vocal dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="cdd02-210">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="cdd02-211">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-211">Click **OK**.</span></span>

10. <span data-ttu-id="cdd02-p133">(Facultatif) Entrez un numéro pour tester la stratégie de voix, puis cliquez sur **OK**. Les résultats du test s’affichent dans **Numéro converti à tester**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cdd02-214">Vous pouvez enregistrer une stratégie de voix qui ne transmet pas encore le test et la reconfigurer plus tard.</span><span class="sxs-lookup"><span data-stu-id="cdd02-214">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="cdd02-215">Pour plus d’informations, consultez <A href="lync-server-2013-test-voice-routing.md">tester le routage vocal dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cdd02-215">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="cdd02-216">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-216">Click **OK**.</span></span>

12. <span data-ttu-id="cdd02-217">Dans la page **Stratégie de voix**, cliquez sur **Valider**, puis sur **Tout valider**.</span><span class="sxs-lookup"><span data-stu-id="cdd02-217">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cdd02-218">Chaque fois que vous créez ou modifiez une stratégie de voix, vous devez exécuter la commande <STRONG>Tout valider</STRONG> pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="cdd02-218">Whenever you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="cdd02-219">Pour plus d’informations, reportez-vous <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">à la rubrique publier des modifications en attente sur la configuration de l’acheminement de la voix dans Lync Server 2013</A> dans la documentation</span><span class="sxs-lookup"><span data-stu-id="cdd02-219">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

13. <span data-ttu-id="cdd02-220">(Facultatif) La redirection vers la messagerie vocale détecte qu’un appel a été intercepté immédiatement par la messagerie vocale du téléphone portable de l’utilisateur et déconnecte l’appel de la messagerie vocale du téléphone portable.</span><span class="sxs-lookup"><span data-stu-id="cdd02-220">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="cdd02-221">L’appel continue de sonner sur les autres points de terminaison de l’utilisateur pour lui permettre de répondre.</span><span class="sxs-lookup"><span data-stu-id="cdd02-221">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="cdd02-222">Pour plus d’informations sur la configuration d’une stratégie de messagerie vocale, voir [configurer l’échappement de la messagerie vocale dans Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span><span class="sxs-lookup"><span data-stu-id="cdd02-222">For details about how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cdd02-223">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cdd02-223">See Also</span></span>


[<span data-ttu-id="cdd02-224">Créer une stratégie de voix et configurer les enregistrements d’utilisation RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdd02-224">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="cdd02-225">Afficher les enregistrements d’utilisation RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdd02-225">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="cdd02-226">Créer un itinéraire vocal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdd02-226">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="cdd02-227">Modifier un itinéraire vocal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdd02-227">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="cdd02-228">Publier les modifications en attente apportées à la configuration du routage de la voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdd02-228">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="cdd02-229">Configuration de l’échappement de la messagerie vocale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdd02-229">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="cdd02-230">Test du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdd02-230">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

