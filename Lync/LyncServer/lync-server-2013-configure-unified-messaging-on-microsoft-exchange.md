---
title: 'Lync Server 2013 : configuration de la messagerie unifiée sur Microsoft Exchange'
description: 'Lync Server 2013 : configurez la messagerie unifiée sur Microsoft Exchange.'
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
ms.openlocfilehash: 8db43bbe50061a1a044bdd34b637ba86f626ca85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577520"
---
# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="475a7-103">Configuration de la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="475a7-103">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="475a7-104">_**Dernière modification de la rubrique :** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="475a7-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="475a7-105">Cette rubrique décrit comment configurer la messagerie unifiée Exchange (MU) sur un serveur Microsoft Exchange Server pour une utilisation avec voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="475a7-105">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="475a7-106">Les exemples d’applets de commande fournis dans cette rubrique fournissent la syntaxe de la version Exchange 2007 de l’environnement de commande Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="475a7-106">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="475a7-107">Si vous utilisez Exchange 2010 ou Exchange 2013, reportez-vous à la documentation appropriée, telle qu’elle est référencée.</span><span class="sxs-lookup"><span data-stu-id="475a7-107">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="475a7-108">Pour configurer un serveur exécutant la messagerie unifiée Exchange Server</span><span class="sxs-lookup"><span data-stu-id="475a7-108">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="475a7-p102">Créez un plan de numérotation URI (Uniform Resource Identifier) SIP (Session Initiation Protocol) de messagerie unifiée pour chacun des profils d’emplacement Voix Entreprise. Si vous choisissez d’utiliser la console de gestion Exchange, créez un nouveau plan de numérotation avec le paramètre de sécurité **Secured (de préférence)**.</span><span class="sxs-lookup"><span data-stu-id="475a7-p102">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles. If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="475a7-111">Si vous définissez votre valeur de paramètre de sécurité sur <STRONG>sécurisé SIP</STRONG> pour exiger le chiffrement pour le trafic SIP uniquement, comme précédemment recommandé, Notez que ce paramètre de sécurité sur un plan de numérotation est insuffisant si le pool frontal est configuré pour exiger le chiffrement, ce qui signifie que le pool nécessite le chiffrement pour le trafic SIP et RTP.</span><span class="sxs-lookup"><span data-stu-id="475a7-111">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="475a7-112">Lorsque le plan de numérotation et les paramètres de sécurité du pool ne sont pas compatibles, tous les appels à la messagerie unifiée Exchange à partir du pool frontal échouent, ce qui entraîne une erreur indiquant que le paramètre de sécurité est incompatible.</span><span class="sxs-lookup"><span data-stu-id="475a7-112">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="475a7-113">Si vous utilisez l’environnement de ligne de commande Exchange Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="475a7-113">If you use the Exchange Management Shell, type:</span></span>
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    <span data-ttu-id="475a7-114">Pour plus d’informations, voir :</span><span class="sxs-lookup"><span data-stu-id="475a7-114">For details, see:</span></span>
    
      - <span data-ttu-id="475a7-115">Pour Office Communications Server 2007, voir « procédure de création d’un plan de numérotation SIP de messagerie unifiée » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) et « New-UMDialplan : Exchange 2007 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666) .</span><span class="sxs-lookup"><span data-stu-id="475a7-115">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="475a7-116">Pour Exchange 2010, voir « Création d’un plan de numérotation de messagerie unifiée » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) et « New-UMDialplan : Exchange 2010 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680) .</span><span class="sxs-lookup"><span data-stu-id="475a7-116">For Exchange 2010, see "Create a UM Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="475a7-117">Pour Exchange 2013, voir « messagerie unifiée » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .</span><span class="sxs-lookup"><span data-stu-id="475a7-117">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="475a7-118">La sélection du niveau de sécurité <STRONG>SIPSecured</STRONG> ou <STRONG>Secured</STRONG> dépend de l’activation ou de la désactivation du protocole SRTP (Secure Real-time Transport Protocol) pour le chiffrement multimédia.</span><span class="sxs-lookup"><span data-stu-id="475a7-118">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="475a7-119">Pour l’intégration de Lync Server 2010 avec la messagerie unifiée Exchange, cela doit correspondre au niveau de chiffrement dans la configuration multimédia de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="475a7-119">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="475a7-120">La configuration multimédia de Lync Server peut être affichée en exécutant la cmdlet <STRONG>Get-CsMediaConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="475a7-120">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="475a7-121">Pour plus d’informations, reportez-vous à Get-CsMediaConfiguration dans la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="475a7-121">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="475a7-122">Pour plus d’informations sur la sélection du paramètre de sécurité VoIP approprié, voir <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processus de déploiement pour l’intégration de la messagerie unifiée locale et Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="475a7-122">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="475a7-123">Exécutez l’applet de commande suivante pour obtenir le nom de domaine complet (FQDN) pour chaque plan de numérotation de messagerie unifiée :</span><span class="sxs-lookup"><span data-stu-id="475a7-123">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="475a7-124">Pour plus d’informations, voir :</span><span class="sxs-lookup"><span data-stu-id="475a7-124">For details, see:</span></span>
    
      - <span data-ttu-id="475a7-125">Pour Exchange 2007, voir « Get-UMDialplan : Exchange 2007 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678) .</span><span class="sxs-lookup"><span data-stu-id="475a7-125">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="475a7-126">Pour Exchange 2010, voir « Get-UMDialplan : Exchange 2010 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679) .</span><span class="sxs-lookup"><span data-stu-id="475a7-126">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="475a7-127">Pour Exchange 2013, voir « messagerie unifiée » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .</span><span class="sxs-lookup"><span data-stu-id="475a7-127">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="475a7-128">Enregistrez le nom de chaque plan de numérotation de messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="475a7-128">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="475a7-129">En fonction de votre version d’Exchange Server, vous devrez peut-être utiliser le nom de domaine complet (FQDN) de chaque nom de plan de numérotation par la suite, comme le nom du plan de numérotation Lync Server correspondant à chaque plan de numérotation de messagerie unifiée, afin que les noms de plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="475a7-129">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="475a7-130">Les noms de plan de numérotation Lync Server doivent correspondre aux noms de plan de numérotation de messagerie unifiée uniquement si le plan de numérotation de messagerie unifiée est exécuté sur une version d’Exchange <EM>antérieure</EM> à Exchange 2010 SP1.</span><span class="sxs-lookup"><span data-stu-id="475a7-130">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="475a7-131">Ajoutez le plan de numérotation au serveur exécutant la messagerie unifiée Exchange comme suit :</span><span class="sxs-lookup"><span data-stu-id="475a7-131">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="475a7-p106">Si vous choisissez d’utiliser la console de gestion Exchange, vous pouvez ajouter le plan de numérotation à partir de la feuille de propriétés du serveur. Pour des instructions spécifiques, voir la documentation du produit Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="475a7-p106">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server. For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="475a7-134">Pour Exchange 2007, voir « procédure d’ajout d’un serveur de messagerie unifiée à un plan de numérotation » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681) .</span><span class="sxs-lookup"><span data-stu-id="475a7-134">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="475a7-135">Pour Exchange 2010, voir « afficher ou configurer les propriétés d’un serveur de messagerie unifiée » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682) .</span><span class="sxs-lookup"><span data-stu-id="475a7-135">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="475a7-136">Pour Exchange 2013, voir « messagerie unifiée » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .</span><span class="sxs-lookup"><span data-stu-id="475a7-136">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="475a7-137">Si vous utilisez l’environnement de ligne de commande Exchange Management Shell, exécutez ce qui suit pour chaque serveur de messagerie unifiée Exchange :</span><span class="sxs-lookup"><span data-stu-id="475a7-137">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="475a7-138">Avant d’effectuer l’étape suivante, vérifiez que tous les utilisateurs de Voix Entreprise ont été configurés avec une boîte aux lettres Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="475a7-138">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="475a7-139">Pour Exchange 2007, reportez-vous à la bibliothèque TechNet Exchange Server 2007 à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A> .</span><span class="sxs-lookup"><span data-stu-id="475a7-139">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="475a7-140">Pour Exchange 2010, reportez-vous à la bibliothèque TechNet Exchange Server 2010 à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A> .</span><span class="sxs-lookup"><span data-stu-id="475a7-140">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="475a7-141">Lorsque vous spécifiez une stratégie de boîte aux lettres pour chaque plan de numérotation créé à l’étape 1, vous pouvez sélectionner la stratégie par défaut ou une stratégie que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="475a7-141">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="475a7-142">Accédez à \<Exchange installation directory\> \\ scripts, puis, si Exchange est déployé dans une forêt unique, tapez :</span><span class="sxs-lookup"><span data-stu-id="475a7-142">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    ```console
    exchucutil.ps1
    ```
    <span data-ttu-id="475a7-143">Ou, si Exchange est déployé dans plusieurs forêts, tapez ceci :</span><span class="sxs-lookup"><span data-stu-id="475a7-143">Or, if Exchange is deployed in multiple forests, type:</span></span>
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    <span data-ttu-id="475a7-144">où Forest FQDN indique la forêt dans laquelle Lync Server est déployé.</span><span class="sxs-lookup"><span data-stu-id="475a7-144">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="475a7-p107">Si vous avez un ou plusieurs plans de numérotation de messagerie unifiée associés à plusieurs passerelles IP, passez à l’étape 6. Si chaque plan de numérotation est associé à une seule passerelle IP, ignorez l’étape 6.</span><span class="sxs-lookup"><span data-stu-id="475a7-p107">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6. If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="475a7-147">Redémarrez le service <STRONG>frontal Lync Server</STRONG> (rtcsrv.exe) <EM>après</EM> avoir exécuté exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="475a7-147">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="475a7-148">Dans le cas contraire, Lync Server ne détecte pas la messagerie unifiée dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="475a7-148">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="475a7-149">À l’aide de l’environnement de ligne de commande Exchange Management Shell ou de la console de gestion Exchange, désactivez les appels sortants pour toutes les passerelles IP associées à chaque plan de numérotation, à l’exception d’une seule.</span><span class="sxs-lookup"><span data-stu-id="475a7-149">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="475a7-150">Cette étape est nécessaire pour garantir que les appels sortants par le serveur exécutant la messagerie unifiée Exchange Server vers des utilisateurs externes (comme dans le cas des scénarios de lecture sur téléphone) traversent le pare-feu d’entreprise de manière fiable.</span><span class="sxs-lookup"><span data-stu-id="475a7-150">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="475a7-151">Lors de la sélection de la passerelle IP de messagerie unifiée, qui permet d’autoriser les appels sortants, choisissez celle qui est capable de gérer le plus grand volume de trafic.</span><span class="sxs-lookup"><span data-stu-id="475a7-151">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="475a7-152">N’autorisez pas le trafic sortant via une passerelle IP qui se connecte à un pool de directeurs Lync Server.</span><span class="sxs-lookup"><span data-stu-id="475a7-152">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="475a7-153">Évitez également les pools d’un autre site central ou site de succursale.</span><span class="sxs-lookup"><span data-stu-id="475a7-153">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="475a7-154">Vous pouvez utiliser l’une des méthodes suivantes pour empêcher les appels sortants de transiter via une passerelle IP :</span><span class="sxs-lookup"><span data-stu-id="475a7-154">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="475a7-155">Si vous utilisez l’environnement de ligne de commande Exchange Management Shell, désactivez chaque passerelle IP en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="475a7-155">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        <span data-ttu-id="475a7-156">Pour Exchange 2007, voir « Set-UMIPGateway : Exchange 2007 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687) .</span><span class="sxs-lookup"><span data-stu-id="475a7-156">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="475a7-157">Pour Exchange 2010, voir « Set-UMIPGateway : Exchange 2010 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688) .</span><span class="sxs-lookup"><span data-stu-id="475a7-157">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="475a7-158">Si vous utilisez la console de gestion Exchange, désactivez la case à cocher **Autoriser les appels sortants via cette passerelle IP de messagerie unifiée**.</span><span class="sxs-lookup"><span data-stu-id="475a7-158">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="475a7-159">Si votre plan de numérotation URI SIP de messagerie unifiée est associé à une seule passerelle IP, n’interdisez pas les appels sortants via cette passerelle.</span><span class="sxs-lookup"><span data-stu-id="475a7-159">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="475a7-160">Créez un standard automatique de messagerie unifiée pour chaque plan de numérotation Lync Server.</span><span class="sxs-lookup"><span data-stu-id="475a7-160">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="475a7-161">N’incluez pas d’espaces dans le nom du standard automatique.</span><span class="sxs-lookup"><span data-stu-id="475a7-161">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    <span data-ttu-id="475a7-162">Pour plus d’informations, voir :</span><span class="sxs-lookup"><span data-stu-id="475a7-162">For details, see:</span></span>
    
      - <span data-ttu-id="475a7-163">Pour Exchange 2007, voir « New-UMAutoAttendant : Exchange 2007 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689) .</span><span class="sxs-lookup"><span data-stu-id="475a7-163">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="475a7-164">Pour Exchange 2010, voir « New-UMAutoAttendant : Exchange 2010 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690) .</span><span class="sxs-lookup"><span data-stu-id="475a7-164">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="475a7-165">L’étape suivante doit être effectuée pour chaque utilisateur une fois que vous avez activé les utilisateurs de Lync Server pour voix entreprise et que vous connaissiez leurs URI SIP.</span><span class="sxs-lookup"><span data-stu-id="475a7-165">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="475a7-166">Associez les utilisateurs de la messagerie unifiée Exchange (chacun d’eux devant être configuré avec une boîte aux lettres Exchange) au plan de numérotation de messagerie unifiée et créez un URI SIP pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="475a7-166">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="475a7-167">L' <STRONG>SIPResourceIdentifier</STRONG> dans l’exemple suivant doit être l’adresse SIP de l’utilisateur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="475a7-167">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    <span data-ttu-id="475a7-168">Pour obtenir des informations détaillées, voir :</span><span class="sxs-lookup"><span data-stu-id="475a7-168">For details, see:</span></span>
    
      - <span data-ttu-id="475a7-169">Pour Exchange 2007, voir « Enable-UMMailbox : Exchange 2007 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691) .</span><span class="sxs-lookup"><span data-stu-id="475a7-169">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="475a7-170">Pour Exchange 2010, voir « Enable-UMMailbox : Exchange 2010 Help » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692) .</span><span class="sxs-lookup"><span data-stu-id="475a7-170">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

