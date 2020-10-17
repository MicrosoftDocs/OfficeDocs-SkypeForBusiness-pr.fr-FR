---
title: 'Lync Server 2013 : modification d’une stratégie de voix et configuration des enregistrements d’utilisation PSTN'
description: 'Lync Server 2013 : modifiez une stratégie de voix et configurez les enregistrements d’utilisation PSTN.'
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
ms.openlocfilehash: e26d6c8654ebf758f8b5a185c21468443e0451a9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559370"
---
# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="e239b-103">Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e239b-103">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e239b-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e239b-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e239b-105">Si vous souhaitez modifier une stratégie de voix, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e239b-105">Follow these steps if you want to modify a voice policy.</span></span> <span data-ttu-id="e239b-106">Si vous souhaitez créer une nouvelle stratégie de voix, voir [créer une stratégie de voix et configurer les enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) pour la procédure.</span><span class="sxs-lookup"><span data-stu-id="e239b-106">If you want to create a new voice policy, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e239b-107">Si un utilisateur est affecté à une stratégie de voix à laquelle aucun enregistrement d’utilisation du réseau téléphonique commuté (PSTN) n’est associé, l’utilisateur ne peut pas effectuer d’appels sortants.</span><span class="sxs-lookup"><span data-stu-id="e239b-107">If a user is assigned to a voice policy has no associated public switched telephone network (PSTN) usage records, the user cannot place outbound calls.</span></span> <span data-ttu-id="e239b-108">Pour obtenir la liste de tous les enregistrements d’utilisation RTC disponibles dans votre déploiement voix entreprise et consulter leurs propriétés, voir <A href="lync-server-2013-view-pstn-usage-records.md">afficher les enregistrements d’utilisation PSTN dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e239b-108">For a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-modify-a-voice-policy"></a><span data-ttu-id="e239b-109">Pour modifier une stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="e239b-109">To modify a voice policy</span></span>

1.  <span data-ttu-id="e239b-110">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e239b-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e239b-111">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e239b-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e239b-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e239b-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e239b-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e239b-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e239b-114">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Stratégie de la voix**.</span><span class="sxs-lookup"><span data-stu-id="e239b-114">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="e239b-115">Dans la page **Stratégie de la voix**, double-cliquez sur le nom d’une stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="e239b-115">On the **Voice Policy** page, double-click a voice policy name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e239b-p105">L’étendue et le nom ont été définis lors de la création de la stratégie de voix. Ils ne peuvent pas être modifiés.</span><span class="sxs-lookup"><span data-stu-id="e239b-p105">The scope and name were set when the voice policy was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="e239b-118">(Facultatif) Dans **Modifier la stratégie de voix**, entrez d’autres informations décrivant la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="e239b-118">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

6.  <span data-ttu-id="e239b-119">Activez ou désactivez les cases à cocher suivantes, afin d’activer ou de désactiver chacune des **Fonctionnalités d’appel** :</span><span class="sxs-lookup"><span data-stu-id="e239b-119">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>
    
      - <span data-ttu-id="e239b-120">**Échappement de la messagerie vocale** empêche les appels d’être immédiatement acheminés au système de messagerie vocale du téléphone mobile de l’utilisateur lorsque la sonnerie simultanée est configurée et que le téléphone est éteint, en panne de batterie ou hors de portée.</span><span class="sxs-lookup"><span data-stu-id="e239b-120">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e239b-121">Cette fonctionnalité est configurable uniquement par le biais de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="e239b-121">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="e239b-122">**Transfert d’appel** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients.</span><span class="sxs-lookup"><span data-stu-id="e239b-122">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="e239b-123">Lync Server 2013 offre un large éventail d’options de configuration pour le transfert d’appel.</span><span class="sxs-lookup"><span data-stu-id="e239b-123">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="e239b-124">Par exemple, si une organisation ne souhaite pas autoriser le transfert des appels entrants à l’extérieur vers le réseau téléphonique commuté (PSTN), un administrateur peut appliquer une stratégie de voix spéciale pour déployer cette restriction.</span><span class="sxs-lookup"><span data-stu-id="e239b-124">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="e239b-125">Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="e239b-125">Enabled by default.</span></span>
    
      - <span data-ttu-id="e239b-126">**Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place.</span><span class="sxs-lookup"><span data-stu-id="e239b-126">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="e239b-127">Dans Lync Server 2013, un délégué peut configurer la sonnerie simultanée qui permet aux appels entrants vers son responsable de sonner dans toutes les cibles de sonnerie simultanées du délégué.</span><span class="sxs-lookup"><span data-stu-id="e239b-127">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="e239b-128">Le délégué peut ainsi répondre avec une plus grande souplesse aux appels destinés au responsable.</span><span class="sxs-lookup"><span data-stu-id="e239b-128">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="e239b-129">Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="e239b-129">Enabled by default.</span></span>
    
      - <span data-ttu-id="e239b-p108">**Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="e239b-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="e239b-p109">**Parcage d’appel** permet aux utilisateurs de parquer des appels en attente, puis de les reprendre depuis un autre téléphone ou client. Désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="e239b-p109">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="e239b-134">**Sonnerie simultanée** permet aux appels entrants de sonner sur des téléphones supplémentaires (par exemple, un téléphone mobile) ou d’autres périphériques de système d’extrémité.</span><span class="sxs-lookup"><span data-stu-id="e239b-134">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="e239b-135">Lync Server 2013 offre un large éventail d’options de configuration pour la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="e239b-135">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="e239b-136">Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="e239b-136">Enabled by default.</span></span>
    
      - <span data-ttu-id="e239b-p111">**Appel d’équipe** permet aux utilisateurs d’une équipe définie de répondre aux appels destinés à d’autres membres de l’équipe. Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="e239b-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>
    
      - <span data-ttu-id="e239b-p112">**Réacheminement PSTN** permet aux appels des utilisateurs (auxquels cette stratégie est affectée) destinés à d’autres utilisateurs de l’entreprise d’être réacheminés sur le réseau téléphonique commuté (PSTN) si le réseau étendu (WAN) est saturé ou indisponible. Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="e239b-p112">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>
    
      - <span data-ttu-id="e239b-p113">**Remplacement de stratégie de bande** permet aux administrateurs de remplacer les décisions de stratégie de contrôle d’admission des appels (CAC) pour un utilisateur particulier. Désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="e239b-p113">**Bandwidth policy override** enables administrators to override call admission control (CAC) policy decisions for a particular user. Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e239b-p114">La stratégie est uniquement remplacée pour les appels entrants vers l’utilisateur et non pour les appels sortants qui sont passés par l’utilisateur. Une fois la session établie, la consommation de bande passante est précisément enregistrée. Ce paramètre doit être utilisé avec modération.</span><span class="sxs-lookup"><span data-stu-id="e239b-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly.</span></span>

        
        </div>
    
      - <span data-ttu-id="e239b-p115">**Suivi des appels malveillants** permet aux utilisateurs de consigner des appels malveillants (comme une alerte à la bombe) à l’aide de l’interface utilisateur du client, qui signale ensuite ces appels dans les enregistrements des détails des appels (CDR). Désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="e239b-p115">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) using the client UI, which in turn flags the calls in the call detail records (CDRs). Disabled by default.</span></span>

7.  <span data-ttu-id="e239b-148">Afin d’associer et de configurer des enregistrements d’utilisation PSTN pour cette stratégie de voix, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e239b-148">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="e239b-p116">Pour choisir un ou plusieurs enregistrements dans une liste de tous les enregistrements d’utilisation PSTN disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette stratégie de voix, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e239b-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="e239b-151">Pour supprimer un enregistrement d’utilisation PSTN de cette stratégie de voix, sélectionnez l’enregistrement et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e239b-151">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="e239b-152">Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette stratégie de voix, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e239b-152">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="e239b-153">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e239b-153">Click **New**.</span></span>
        
        2.  <span data-ttu-id="e239b-p117">Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement. Par exemple, vous pouvez créer un enregistrement d’utilisation PSTN appelé **Redmond** pour les employés qui travaillent à plein temps situés à Redmond et un autre enregistrement appelé **RedmondTemps** pour les employés qui travaillent à temps partiel.</span><span class="sxs-lookup"><span data-stu-id="e239b-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another record named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="e239b-p118">Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ <STRONG>Nom</STRONG> ne peut plus être modifié.</span><span class="sxs-lookup"><span data-stu-id="e239b-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="e239b-158">Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :</span><span class="sxs-lookup"><span data-stu-id="e239b-158">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="e239b-159">Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e239b-159">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="e239b-160">Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e239b-160">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="e239b-161">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e239b-161">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="e239b-162">Pour plus d’informations, consultez [la rubrique créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="e239b-162">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="e239b-163">Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="e239b-163">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="e239b-164">Pour plus d’informations, consultez [la rubrique modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="e239b-164">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="e239b-165">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e239b-165">Click **OK**.</span></span>
    
      - <span data-ttu-id="e239b-166">Pour modifier un enregistrement d’utilisation PSTN qui est déjà associé à cette stratégie de voix, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e239b-166">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="e239b-167">Sélectionnez l’enregistrement d’utilisation PSTN à modifier, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="e239b-167">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="e239b-168">Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :</span><span class="sxs-lookup"><span data-stu-id="e239b-168">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="e239b-169">Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e239b-169">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="e239b-170">Pour supprimer un itinéraire de cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e239b-170">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="e239b-171">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e239b-171">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="e239b-172">Pour plus d’informations, consultez [la rubrique créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="e239b-172">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="e239b-173">Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="e239b-173">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="e239b-174">Pour plus d’informations, consultez [la rubrique modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="e239b-174">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="e239b-175">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e239b-175">Click **OK**.</span></span>

8.  <span data-ttu-id="e239b-p123">Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez le nom de l’enregistrement, puis cliquez sur la flèche vers le haut ou vers le bas.</span><span class="sxs-lookup"><span data-stu-id="e239b-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e239b-178">L’ordre dans lequel les enregistrements d’utilisation apparaissent dans la stratégie de voix est essentiel.</span><span class="sxs-lookup"><span data-stu-id="e239b-178">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="e239b-179">Lync Server parcourt la liste du haut vers le bas.</span><span class="sxs-lookup"><span data-stu-id="e239b-179">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="e239b-180">Nous vous conseillons d’organiser la liste par fréquence d’utilisation ; par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="e239b-180">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

9.  <span data-ttu-id="e239b-181">Afin d’associer et de configurer des enregistrements d’utilisation PSTN pour le transfert d’appel et la sonnerie simultanée dans cette stratégie de voix, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e239b-181">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="e239b-182">Pour utiliser les mêmes enregistrements d’utilisation PSTN pour le transfert d’appel et la sonnerie simultanée que cette stratégie de voix, sélectionnez l’option **Routage avec les utilisations PSTN d’appel** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="e239b-182">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="e239b-183">Pour autoriser le transfert d’appel et la sonnerie simultanée aux utilisateurs de Lync internes uniquement, sélectionnez **routage vers les utilisateurs de Lync internes uniquement** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="e239b-183">To allow call forwarding and simultaneous ringing to internal Lync users only, select **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="e239b-184">Les appels ne seront pas transférés à des numéros PSTN externes.</span><span class="sxs-lookup"><span data-stu-id="e239b-184">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="e239b-p126">Pour spécifier des enregistrements d’utilisation PSTN pour le transfert d’appel et la sonnerie simultanée différents de ceux utilisés pour cette stratégie de voix, sélectionnez l’option **Routage avec des utilisations PSTN personnalisées** dans le menu déroulant. Cette option affiche un contrôle pour sélectionner les enregistrements d’utilisation PSTN existants ou créer de nouveaux enregistrements d’utilisation PSTN spécifiquement pour le transfert d’appel et la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="e239b-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="e239b-p127">Pour choisir un ou plusieurs enregistrements dans une liste d’enregistrements d’utilisation PSTN pour le transfert d’appel et la sonnerie simultanée, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette stratégie de transfert d’appel et de sonnerie simultanée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e239b-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="e239b-189">Pour supprimer un enregistrement d’utilisation PSTN de cette stratégie de transfert d’appel et de sonnerie simultanée, sélectionnez l’enregistrement et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e239b-189">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="e239b-190">Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette stratégie de transfert d’appel et de sonnerie simultanée, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e239b-190">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="e239b-191">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e239b-191">Click **New**.</span></span>
            
            2.  <span data-ttu-id="e239b-192">Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="e239b-192">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="e239b-p128">Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ <STRONG>Nom</STRONG> ne peut plus être modifié.</span><span class="sxs-lookup"><span data-stu-id="e239b-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="e239b-195">Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :</span><span class="sxs-lookup"><span data-stu-id="e239b-195">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="e239b-196">Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e239b-196">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="e239b-197">Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e239b-197">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="e239b-198">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e239b-198">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="e239b-199">Pour plus d’informations, consultez [la rubrique créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="e239b-199">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="e239b-200">Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="e239b-200">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="e239b-201">Pour plus d’informations, consultez [la rubrique modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="e239b-201">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="e239b-202">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e239b-202">Click **OK**.</span></span>
        
          - <span data-ttu-id="e239b-203">Pour modifier un enregistrement d’utilisation PSTN qui est déjà associé à cette stratégie de voix, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e239b-203">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="e239b-204">Sélectionnez l’enregistrement d’utilisation PSTN à modifier, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="e239b-204">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="e239b-205">Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :</span><span class="sxs-lookup"><span data-stu-id="e239b-205">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="e239b-206">Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e239b-206">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="e239b-207">Pour supprimer un itinéraire de cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e239b-207">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="e239b-208">Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e239b-208">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="e239b-209">Pour plus d’informations, consultez [la rubrique créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="e239b-209">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="e239b-210">Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="e239b-210">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="e239b-211">Pour plus d’informations, consultez [la rubrique modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="e239b-211">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="e239b-212">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e239b-212">Click **OK**.</span></span>

10. <span data-ttu-id="e239b-p133">(Facultatif) Entrez un numéro pour tester la stratégie de voix, puis cliquez sur **OK**. Les résultats du test apparaissent sous **Numéro traduit à tester**.</span><span class="sxs-lookup"><span data-stu-id="e239b-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e239b-215">Vous pouvez enregistrer une stratégie de voix qui ne réussit pour l’instant pas le test, puis la reconfigurer ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="e239b-215">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="e239b-216">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-test-voice-routing.md">test de routage des communications vocales dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e239b-216">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="e239b-217">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e239b-217">Click **OK**.</span></span>

12. <span data-ttu-id="e239b-218">Dans la page **Stratégie de la voix**, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="e239b-218">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e239b-219">Chaque fois que vous créez ou modifiez une stratégie de voix, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="e239b-219">Whenever you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="e239b-220">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="e239b-220">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

13. <span data-ttu-id="e239b-221">(Facultatif) L’échappement de la messagerie vocale détecte qu’un appel a été immédiatement pris en charge par la messagerie vocale du téléphone mobile de l’utilisateur et déconnecte l’appel vers la messagerie vocale du téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="e239b-221">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="e239b-222">Cela permet à l’appel de continuer de sonner sur les autres systèmes d’extrémité de l’utilisateur, donnant ainsi à l’utilisateur la possibilité de répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="e239b-222">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="e239b-223">Pour plus d’informations sur la configuration d’une stratégie de messagerie vocale, reportez-vous à la rubrique [configuration de l’échappement de la messagerie vocale dans Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span><span class="sxs-lookup"><span data-stu-id="e239b-223">For details about how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e239b-224">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e239b-224">See Also</span></span>


[<span data-ttu-id="e239b-225">Création d’une stratégie de voix et configuration des enregistrements d’utilisation PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e239b-225">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="e239b-226">Afficher les enregistrements d’utilisation RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e239b-226">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="e239b-227">Créer un itinéraire des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e239b-227">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="e239b-228">Modifier un itinéraire des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e239b-228">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="e239b-229">Publier les modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e239b-229">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="e239b-230">Configuration de l’échappement de la messagerie vocale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e239b-230">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="e239b-231">Tester le routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e239b-231">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

