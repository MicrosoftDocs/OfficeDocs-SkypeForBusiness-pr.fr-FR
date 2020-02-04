---
title: 'Lync Server 2013 : configuration de la messagerie unifiée sur Microsoft Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edac9ff9b72c00e7520d80c376e49b03a9e35bab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="c5990-102">Configurer la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5990-102">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5990-103">_**Dernière modification de la rubrique :** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="c5990-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="c5990-104">Cette rubrique décrit comment configurer la messagerie unifiée Exchange sur un serveur Microsoft Exchange pour une utilisation avec la voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="c5990-104">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c5990-105">Les exemples de cette rubrique fournissent une syntaxe pour la version 2007 d’Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c5990-105">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="c5990-106">Si vous exécutez Exchange 2010 ou Exchange 2013, voir la documentation appropriée telle qu’elle est référencée.</span><span class="sxs-lookup"><span data-stu-id="c5990-106">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="c5990-107">Pour configurer un serveur exécutant la messagerie unifiée Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c5990-107">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="c5990-108">Créez un plan de numérotation d’URI (Uniform Resource Identifier) SIP) pour chacun de vos profils d’emplacements vocaux d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="c5990-108">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles.</span></span> <span data-ttu-id="c5990-109">Si vous choisissez d’utiliser la console de gestion Exchange, créez un nouveau plan de numérotation avec le paramètre de sécurité **sécurisé (par défaut)**.</span><span class="sxs-lookup"><span data-stu-id="c5990-109">If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c5990-110">Si vous avez défini votre paramètre de sécurité sur <STRONG>sécurisé par SIP</STRONG> pour exiger le chiffrement pour le trafic SIP uniquement, comme précédemment recommandé, Notez que ce paramètre de sécurité sur un plan de numérotation est insuffisant si le pool frontal est configuré pour exiger le chiffrement, ce qui signifie que le pool nécessite un chiffrement pour le trafic SIP et RTP.</span><span class="sxs-lookup"><span data-stu-id="c5990-110">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="c5990-111">Lorsque les paramètres de sécurité du plan de numérotation et du pool ne sont pas compatibles, tous les appels à la messagerie unifiée Exchange à partir du pool frontal échouent, ce qui génère une erreur indiquant que vous avez un paramètre de sécurité non compatible.</span><span class="sxs-lookup"><span data-stu-id="c5990-111">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="c5990-112">Si vous utilisez Exchange Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="c5990-112">If you use the Exchange Management Shell, type:</span></span>
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    <span data-ttu-id="c5990-113">Pour plus d’informations, consultez :</span><span class="sxs-lookup"><span data-stu-id="c5990-113">For details, see:</span></span>
    
      - <span data-ttu-id="c5990-114">Pour Office Communications Server 2007, voir la section « création d’un plan de numérotation URI SIP de [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) messagerie unifiée » dans et « nouvelle-UMDialplan : [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666)aide d’Exchange 2007 ».</span><span class="sxs-lookup"><span data-stu-id="c5990-114">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="c5990-115">Pour Exchange 2010, voir « créer un plan de numérotation de [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) messagerie unifiée » à et « nouvelle-UMDialplan : [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)aide d’Exchange 2010 » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c5990-115">For Exchange 2010, see "Create a UM Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="c5990-116">Pour Exchange 2013, voir « messagerie unifiée » [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c5990-116">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5990-117">Le fait de sélectionner un niveau de sécurité <STRONG>SIPSecured</STRONG> ou <STRONG>sécurisé</STRONG> dépend du mode d’activation ou de désactivation du protocole SRTP (Secure Real-Time Transport Protocol) pour le chiffrement multimédia.</span><span class="sxs-lookup"><span data-stu-id="c5990-117">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="c5990-118">Pour l’intégration de Lync Server 2010 à la messagerie unifiée Exchange, cela doit correspondre au niveau de chiffrement dans la configuration multimédia du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="c5990-118">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="c5990-119">La configuration de média de Lync Server peut être affichée en exécutant l’applet de passe <STRONG>Get-CsMediaConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c5990-119">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="c5990-120">Pour plus d’informations, consultez la rubrique Get-CsMediaConfiguration dans la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c5990-120">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="c5990-121">Pour plus d’informations sur la sélection du paramètre de sécurité VoIP approprié, voir <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processus de déploiement pour l’intégration de la messagerie unifiée locale et de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c5990-121">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="c5990-122">Exécutez l’applet de commande suivante pour obtenir le nom de domaine complet (FQDN) de chaque plan de numérotation de messagerie unifiée :</span><span class="sxs-lookup"><span data-stu-id="c5990-122">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="c5990-123">Pour plus d’informations, consultez :</span><span class="sxs-lookup"><span data-stu-id="c5990-123">For details, see:</span></span>
    
      - <span data-ttu-id="c5990-124">Pour Exchange 2007, voir « Get-UMDialplan : aide Exchange 2007 » à [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678)l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c5990-124">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="c5990-125">Pour Exchange 2010, voir « Get-UMDialplan : aide Exchange 2010 » à [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679)l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c5990-125">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="c5990-126">Pour Exchange 2013, voir « messagerie unifiée » [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c5990-126">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="c5990-127">Enregistrez le nom du plan de numérotation de chaque plan de numérotation de messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="c5990-127">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="c5990-128">En fonction de votre version d’Exchange Server, il est possible que vous deviez utiliser le nom de domaine complet (FQDN) de chaque nom de plan de numérotation ultérieurement pour le nom du plan de numérotation de votre plan de numérotation de messagerie unifiée correspondant aux noms de plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="c5990-128">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5990-129">Les noms de plan de numérotation de Lync Server doivent correspondre aux noms du plan de numérotation de messagerie unifiée uniquement si le plan de numérotation de messagerie unifié s’exécute sur une version d’Exchange <EM>antérieure</EM> à Exchange 2010 SP1.</span><span class="sxs-lookup"><span data-stu-id="c5990-129">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="c5990-130">Ajoutez le plan de numérotation au serveur exécutant la messagerie unifiée Exchange en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="c5990-130">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="c5990-131">Si vous choisissez d’utiliser la console de gestion Exchange, vous pouvez ajouter le plan de numérotation à partir de la feuille de propriétés du serveur.</span><span class="sxs-lookup"><span data-stu-id="c5990-131">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server.</span></span> <span data-ttu-id="c5990-132">Pour obtenir des instructions spécifiques, consultez la documentation du produit Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="c5990-132">For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="c5990-133">Pour Exchange 2007, voir la section « Comment ajouter un serveur de messagerie unifiée à un [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681)plan de numérotation » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c5990-133">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="c5990-134">Pour Exchange 2010, voir « afficher ou configurer les propriétés d’un serveur de messagerie unifiée » [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682).</span><span class="sxs-lookup"><span data-stu-id="c5990-134">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="c5990-135">Pour Exchange 2013, voir « messagerie unifiée » [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c5990-135">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="c5990-136">Si vous utilisez Exchange Management Shell, exécutez la commande suivante pour chaque serveur Exchange UM :</span><span class="sxs-lookup"><span data-stu-id="c5990-136">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5990-137">Avant de procéder à l’étape suivante, assurez-vous que tous les utilisateurs d’Enterprise Voice ont été configurés avec une boîte aux lettres Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="c5990-137">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="c5990-138">Pour Exchange 2007, voir la bibliothèque TechNet Exchange Server 2007 à <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c5990-138">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="c5990-139">Pour Exchange 2010, voir la bibliothèque TechNet Exchange Server 2010 à <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c5990-139">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="c5990-140">Lorsque vous spécifiez une stratégie de boîte aux lettres pour chaque plan de numérotation que vous avez créé à l’étape 1, sélectionnez la stratégie par défaut ou celle que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="c5990-140">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="c5990-141">Naviguez \<jusqu’à scripts\>\\d’annuaire d’installation Exchange, puis, si Exchange est déployé dans une seule forêt, tapez :</span><span class="sxs-lookup"><span data-stu-id="c5990-141">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    ```console
    exchucutil.ps1
    ```
    <span data-ttu-id="c5990-142">Ou, si Exchange est déployé dans plusieurs forêts, tapez :</span><span class="sxs-lookup"><span data-stu-id="c5990-142">Or, if Exchange is deployed in multiple forests, type:</span></span>
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    <span data-ttu-id="c5990-143">où FQDN de forêt spécifie la forêt dans laquelle le serveur Lync est déployé.</span><span class="sxs-lookup"><span data-stu-id="c5990-143">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="c5990-144">Si vous avez un ou plusieurs plans de numérotation de messagerie unifiée associés à plusieurs passerelles IP, passez à l’étape 6.</span><span class="sxs-lookup"><span data-stu-id="c5990-144">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6.</span></span> <span data-ttu-id="c5990-145">Si vos plans de numérotation sont associés à une seule passerelle IP, ignorez l’étape 6.</span><span class="sxs-lookup"><span data-stu-id="c5990-145">If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c5990-146">Assurez-vous de redémarrer le service <STRONG>frontal de Lync Server</STRONG> (rtcsrv. exe) <EM>après avoir</EM> exécuté exchucutil. ps1.</span><span class="sxs-lookup"><span data-stu-id="c5990-146">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="c5990-147">Dans le cas contraire, Lync Server ne détectera pas la messagerie unifiée dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="c5990-147">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="c5990-148">À l’aide d’Exchange Management Shell ou de la console de gestion Exchange, désactivez les appels sortants pour toutes les passerelles IP associées à chacun de vos plans de numérotation.</span><span class="sxs-lookup"><span data-stu-id="c5990-148">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5990-149">Cette étape est nécessaire pour veiller à ce que les appels sortants par le serveur qui exécute la messagerie unifiée Exchange Server vers des utilisateurs externes (par exemple, comme le cas des scénarios de lecture sur le téléphone) passent de manière fiable au pare-feu d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="c5990-149">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c5990-150">Lors de la sélection de la passerelle IP de MU pour autoriser les appels sortants, choisissez celle qui est susceptible de gérer le plus de trafic.</span><span class="sxs-lookup"><span data-stu-id="c5990-150">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="c5990-151">N’autorisez pas le trafic sortant par le biais d’une passerelle IP qui se connecte à un pool de directeurs serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="c5990-151">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="c5990-152">Evitez également les pools dans un autre site central ou un site de succursale.</span><span class="sxs-lookup"><span data-stu-id="c5990-152">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="c5990-153">Vous pouvez utiliser l’une des méthodes suivantes pour empêcher les appels sortants de traverser une passerelle IP :</span><span class="sxs-lookup"><span data-stu-id="c5990-153">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="c5990-154">Si vous utilisez Exchange Management Shell, désactivez chaque passerelle IP en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c5990-154">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        <span data-ttu-id="c5990-155">Pour Exchange 2007, voir « Set-UMIPGateway : aide d’Exchange 2007 » [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c5990-155">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="c5990-156">Pour Exchange 2010, voir « Set-UMIPGateway : aide d’Exchange 2010 » [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c5990-156">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="c5990-157">Si vous utilisez la console de gestion Exchange, désactivez la case à cocher **autoriser les appels sortants via cette passerelle IP** .</span><span class="sxs-lookup"><span data-stu-id="c5990-157">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c5990-158">Si votre plan de numérotation d’URI SIP de MU est associé à une seule passerelle IP, n’autorisez pas les appels sortants par le biais de cette passerelle.</span><span class="sxs-lookup"><span data-stu-id="c5990-158">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="c5990-159">Créer un standard automatique de messagerie unifiée pour chaque plan de numérotation Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c5990-159">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c5990-160">N’incluez pas d’espace dans le nom du standard automatique.</span><span class="sxs-lookup"><span data-stu-id="c5990-160">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    <span data-ttu-id="c5990-161">Pour plus d’informations, consultez :</span><span class="sxs-lookup"><span data-stu-id="c5990-161">For details, see:</span></span>
    
      - <span data-ttu-id="c5990-162">Pour Exchange 2007, voir "nouvelle-UMAutoAttendant : aide d’Exchange 2007" [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689)à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c5990-162">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="c5990-163">Pour Exchange 2010, voir "nouvelle-UMAutoAttendant : aide d’Exchange 2010" [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690)à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c5990-163">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="c5990-164">Pour chaque utilisateur, l’étape suivante doit être effectuée lorsque vous avez activé les utilisateurs de Lync Server pour voix entreprise et que vous connaissez leurs URI SIP.</span><span class="sxs-lookup"><span data-stu-id="c5990-164">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="c5990-165">Associez les utilisateurs Exchange UM (qui doivent être configurés avec une boîte aux lettres Exchange) avec le plan de numérotation de messagerie unifiée et créez un URI SIP pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c5990-165">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5990-166">Dans l’exemple suivant, le <STRONG>SIPResourceIdentifier</STRONG> doit être l’adresse SIP de l’utilisateur de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c5990-166">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    <span data-ttu-id="c5990-167">Pour plus d’informations, consultez :</span><span class="sxs-lookup"><span data-stu-id="c5990-167">For details, see:</span></span>
    
      - <span data-ttu-id="c5990-168">Pour Exchange 2007, voir la section « Activer-UMMailbox : aide Exchange 2007 [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)» à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c5990-168">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="c5990-169">Pour Exchange 2010, voir la section « Activer-UMMailbox : aide Exchange 2010 [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)» à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c5990-169">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

