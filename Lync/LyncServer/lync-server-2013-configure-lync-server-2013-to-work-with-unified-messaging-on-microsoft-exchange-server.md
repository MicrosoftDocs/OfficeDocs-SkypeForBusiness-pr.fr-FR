---
title: 'Lync Server 2013 : Configuration de Lync Server 2013 pour qu’il fonctionne avec la messagerie unifiée sur Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27909f4ae6231b1452cbfefdd82e0a0eb107c6fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="341f2-102">Configuration de Lync Server 2013 pour qu’il fonctionne avec la messagerie unifiée sur Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="341f2-102">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="341f2-103">_**Dernière modification de la rubrique:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="341f2-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="341f2-104">Cette étape nécessite l’utilitaire d’intégration de la messagerie unifiée Exchange (OcsUmUtil. exe).</span><span class="sxs-lookup"><span data-stu-id="341f2-104">This step requires the Exchange UM Integration Utility (OcsUmUtil.exe).</span></span> <span data-ttu-id="341f2-105">Cet outil se trouve sur le serveur 2013 du serveur Lync dans le. \\Fichiers programme\\fichiers communs\\Microsoft Lync Server 2013\\support.</span><span class="sxs-lookup"><span data-stu-id="341f2-105">This tool is located on the Lync Server 2013 server in the ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support folder.</span></span>

<div>

## <a name="running-the-exchange-um-integration-utility"></a><span data-ttu-id="341f2-106">Exécution de l’utilitaire d’intégration de la messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="341f2-106">Running the Exchange UM Integration Utility</span></span>

<span data-ttu-id="341f2-107">L’utilitaire d’intégration de la messagerie unifiée Exchange doit être exécuté à partir d’un compte d’utilisateur présentant les caractéristiques suivantes:</span><span class="sxs-lookup"><span data-stu-id="341f2-107">The Exchange UM Integration Utility must be run from a user account with the following characteristics:</span></span>

  - <span data-ttu-id="341f2-108">L’appartenance aux groupes RTCUniversalServerAdmins et RtcUniversalUserAdmins (qui inclut l’autorisation de lecture des paramètres de messagerie unifiée Exchange Server);</span><span class="sxs-lookup"><span data-stu-id="341f2-108">Membership in the RTCUniversalServerAdmins and RtcUniversalUserAdmins groups (which includes permission to read Exchange Server Unified Messaging settings).</span></span>

  - <span data-ttu-id="341f2-109">Droits d’utilisateur au sein du domaine pour créer des objets de contact dans le conteneur d’unité d’organisation (UO) spécifié.</span><span class="sxs-lookup"><span data-stu-id="341f2-109">User rights within the domain to create contact objects in the specified organizational unit (OU) container.</span></span>

<span data-ttu-id="341f2-110">Lorsque vous exécutez l’utilitaire d’intégration de MU Exchange, il effectue les tâches suivantes:</span><span class="sxs-lookup"><span data-stu-id="341f2-110">When you run the Exchange UM Integration Utility, it performs the following tasks:</span></span>

  - <span data-ttu-id="341f2-111">Permet de créer des objets de contact pour chaque standard automatique et numéro d’accès d’abonné qui doivent être utilisés par les utilisateurs d’Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="341f2-111">Creates contact objects for each auto-attendant and subscriber access number to be used by Enterprise Voice users.</span></span>

  - <span data-ttu-id="341f2-112">Vérifie que le nom de chaque plan de numérotation vocale d’entreprise correspond à son contexte téléphonique de messagerie unifiée (MU) correspondant.</span><span class="sxs-lookup"><span data-stu-id="341f2-112">Verifies that the name of each Enterprise Voice dial plan matches its corresponding unified messaging (UM) dial plan phone context.</span></span> <span data-ttu-id="341f2-113">Cette correspondance est nécessaire uniquement si le plan de numérotation de messagerie unifiée s’exécute sur une version d’Exchange *antérieure* à Exchange 2010 Service Pack 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="341f2-113">This matching is necessary only if the UM dial plan is running on a version of Exchange *earlier* than Exchange 2010 Service Pack 1 (SP1).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="341f2-114">Avant d’exécuter l’utilitaire d’intégration de la messagerie unifiée Exchange, assurez-vous que vous avez réalisé les opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="341f2-114">Before running the Exchange UM Integration Utility, be sure that you have done the following:</span></span>
> <ul>
> <li><p><span data-ttu-id="341f2-115">Créez un ou plusieurs plans de numérotation de messagerie unifiée Exchange, comme décrit dans la documentation du produit Exchange.</span><span class="sxs-lookup"><span data-stu-id="341f2-115">Create one or more Exchange UM dial plans, as described in the Exchange product documentation.</span></span></p>
> <p><span data-ttu-id="341f2-116">Pour Microsoft Exchange Server 2010, voir &quot;créer un plan&quot; de numérotation <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>de messagerie unifiée à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="341f2-116">For Microsoft Exchange Server 2010, see &quot;Create a UM Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>.</span></span></p>
> <p><span data-ttu-id="341f2-117">Pour Microsoft Exchange Server 2007 Service Pack 1 (SP1), voir &quot;création d’un plan&quot; de NUMÉROTation d’URI SIP de <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>messagerie unifiée à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="341f2-117">For Microsoft Exchange Server 2007 Service Pack 1 (SP1), see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span></span></p></li>
> <li><p><span data-ttu-id="341f2-118">Créez un ou plusieurs plans de numérotation Lync Server correspondants, comme décrit dans la rubrique <a href="lync-server-2013-create-a-dial-plan.md">créer un plan de numérotation dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="341f2-118">Create one or more corresponding Lync Server dial plans, as described in <a href="lync-server-2013-create-a-dial-plan.md">Create a dial plan in Lync Server 2013</a>.</span></span></p></li>
> <ul><li><span data-ttu-id="341f2-119">Si vous utilisez une version d’Exchange antérieure à Microsoft Exchange Server 2010 SP1, vous devez entrer le nom de domaine complet (FQDN) du plan de numérotation SIP correspondant dans le plan de numérotation de messagerie unifiée Exchange Server 2013. <STRONG> </STRONG>champ.</span><span class="sxs-lookup"><span data-stu-id="341f2-119">If you are using a version of Exchange that is earlier than Microsoft Exchange Server 2010 SP1, you must enter the fully qualified domain name (FQDN) of the corresponding Exchange Unified Messaging (UM) SIP dial plan in the Lync Server 2013 dial plan <STRONG>Simple name</STRONG> field.</span></span> <span data-ttu-id="341f2-120">Si vous utilisez Microsoft Exchange Server 2010 SP1 ou le dernier Service Pack, il n’est pas nécessaire de faire correspondre ce nom de plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="341f2-120">If you are using Microsoft Exchange Server 2010 SP1 or latest service pack, this dial plan name matching is not necessary.</span></span></li></ul>
> <li><span data-ttu-id="341f2-121">Créez un standard automatique et assurez-vous que le numéro d’accès d’abonné et le numéro de standard automatique sont au format E. 164.</span><span class="sxs-lookup"><span data-stu-id="341f2-121">Create an auto-attendant and make sure that both the subscriber access number and auto-attendant number are in E.164 format.</span></span></li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a><span data-ttu-id="341f2-122">Pour exécuter l’utilitaire d’intégration de la messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="341f2-122">To run the Exchange UM Integration Utility</span></span>

1.  <span data-ttu-id="341f2-123">Sur un serveur frontal, ouvrez une invite de commandes et tapez **cd% COMMONPROGRAMFILES%\\Microsoft Lync Server 2013\\support**, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="341f2-123">On a Front End Server, open a command prompt and type **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support**, and then press ENTER.</span></span>

2.  <span data-ttu-id="341f2-124">Tapez **OcsUmUtil. exe**, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="341f2-124">Type **OcsUmUtil.exe**, and then press ENTER.</span></span>

3.  <span data-ttu-id="341f2-125">Cliquez sur **charger les données** pour rechercher toutes les forêts Exchange approuvées.</span><span class="sxs-lookup"><span data-stu-id="341f2-125">Click **Load Data** to find all trusted Exchange forests.</span></span>

4.  <span data-ttu-id="341f2-126">Dans la liste **plans de numérotation SIP** , sélectionnez un plan de numérotation SIP de MU pour lequel vous voulez créer des objets de contact, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="341f2-126">In the **SIP Dial Plans** list, select a UM SIP dial plan for which you want to create contact objects, and then click **Add**.</span></span>

5.  <span data-ttu-id="341f2-127">Dans la zone **contact** , acceptez l’unité d’organisation par défaut ou cliquez sur **Parcourir** pour démarrer le **Sélecteur d’UO**.</span><span class="sxs-lookup"><span data-stu-id="341f2-127">In the **Contact** box, accept the default organizational unit, or click **Browse** to start the **OU Picker**.</span></span> <span data-ttu-id="341f2-128">Dans la boîte de dialogue **Sélecteur d’UO** , vous pouvez sélectionner une unité d’organisation et cliquer sur **OK**, ou bien cliquer sur **créer une nouvelle** unité d’organisation pour créer une nouvelle unité d’organisation sous la racine OU dans une autre unité d’organisation du domaine (par exemple, «UO = RTC spécial, DC = fourthcoffee, DC = com») , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="341f2-128">In the **OU Picker** box, you can select an OU and click **OK**, or you can click **Make New OU** to create a new organizational unit under the root or any other OU in the domain (for example, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="341f2-129">Le nom unique (DN) de l’unité d’organisation que vous avez sélectionnée ou créée est désormais affiché dans la zone <STRONG>unité d’organisation</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="341f2-129">The distinguished name (DN) of the OU that you have selected or created is now displayed in the <STRONG>Organizational Unit</STRONG> box.</span></span>

    
    </div>

6.  <span data-ttu-id="341f2-130">Dans la zone **nom** , acceptez le nom de plan de numérotation par défaut ou tapez un nouveau nom d’affichage pour l’objet de contact que vous êtes en train de créer.</span><span class="sxs-lookup"><span data-stu-id="341f2-130">In the **Name** box, either accept the default dial plan name or type a new display name for the contact object that you are creating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="341f2-131">Par exemple, si vous créez un objet contact d’accès abonné, vous pouvez simplement lui nommer l’accès de l’abonné.</span><span class="sxs-lookup"><span data-stu-id="341f2-131">For example, if you are creating a subscriber access contact object, you might simply name it Subscriber Access.</span></span>

    
    </div>

7.  <span data-ttu-id="341f2-132">Dans la zone **adresse SIP** , acceptez l’adresse SIP par défaut ou tapez une nouvelle adresse SIP.</span><span class="sxs-lookup"><span data-stu-id="341f2-132">In the **SIP Address** box, either accept the default SIP address or type a new SIP address.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="341f2-133">Si vous tapez une nouvelle adresse SIP, celle-ci doit commencer par <STRONG>SIP:</STRONG> (c’est-À-dire «SIP:», y compris le signe deux-points).</span><span class="sxs-lookup"><span data-stu-id="341f2-133">If you type a new SIP address, it must begin with <STRONG>SIP:</STRONG> (that is, "SIP:" including the colon).</span></span>

    
    </div>

8.  <span data-ttu-id="341f2-134">Dans la liste **serveur ou pool** , sélectionnez le serveur Standard Edition ou le pool frontal sur lequel l’objet de contact doit être activé.</span><span class="sxs-lookup"><span data-stu-id="341f2-134">In the **Server or Pool** list, select the Standard Edition server or Front End pool in which the contact object is to be enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="341f2-135">De préférence, le pool que vous sélectionnez est le même que celui dans lequel les utilisateurs sont activés pour voix entreprise et Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="341f2-135">Preferably, the pool you select is the same one pool where users enabled for Enterprise Voice and Exchange UM are deployed.</span></span>

    
    </div>

9.  <span data-ttu-id="341f2-136">Dans la liste **numéro de téléphone** , sélectionnez **saisir le numéro de téléphone** ou **utiliser ce pilote à partir d’Exchange um** , puis entrez un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="341f2-136">In the **Phone Number** list, select either **Enter phone number** or **Use this pilot number from Exchange UM** and then enter a phone number.</span></span>

10. <span data-ttu-id="341f2-137">Dans la liste **type de contact** , sélectionnez le type de contact que vous voulez créer, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="341f2-137">In the **Contact Type** list, select the contact type that you want to create, and then click **OK**.</span></span>

11. <span data-ttu-id="341f2-138">Répétez les étapes 1 à 10 pour les autres objets de contact que vous voulez créer.</span><span class="sxs-lookup"><span data-stu-id="341f2-138">Repeat steps 1 through 10 for additional contact objects that you want to create.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="341f2-139">Vous devez créer au moins un contact pour chaque standard automatique.</span><span class="sxs-lookup"><span data-stu-id="341f2-139">You should create at least one contact for each auto attendant.</span></span> <span data-ttu-id="341f2-140">Si vous voulez disposer d’un accès externe, vous devez également disposer d’un contact d’accès d’abonné et spécifier des numéros directs de composition à l’intérieur.</span><span class="sxs-lookup"><span data-stu-id="341f2-140">If you want external access, you also need a Subscriber Access contact and to specify Direct Inward Dial (DID) numbers.</span></span>

    
    </div>

</div>

<span data-ttu-id="341f2-141">Pour vérifier que les objets de contact ont été créés, ouvrez utilisateurs et ordinateurs Active Directory, puis sélectionnez l’unité d’organisation dans laquelle les objets ont été créés.</span><span class="sxs-lookup"><span data-stu-id="341f2-141">To verify that the contact objects have been created, open Active Directory Users and Computers and select the OU in which the objects were created.</span></span> <span data-ttu-id="341f2-142">Les objets de contact doivent s’afficher dans le volet Détails.</span><span class="sxs-lookup"><span data-stu-id="341f2-142">The contact objects should appear in the details pane.</span></span>

<span data-ttu-id="341f2-143"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="341f2-143"></span></span></div>

