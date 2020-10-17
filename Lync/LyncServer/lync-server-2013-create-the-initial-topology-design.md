---
title: 'Lync Server 2013 : création de la conception de topologie initiale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbd021a6b3804c369bccea5affcf26558802de2c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504731"
---
# <a name="create-the-initial-topology-design-for-lync-server-2013"></a><span data-ttu-id="50e78-102">Création de la conception de topologie initiale pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50e78-102">Create the initial topology design for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50e78-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="50e78-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="50e78-104">Une fois que vous avez terminé l’installation de l’outil de planification Lync Server 2013, vous êtes prêt à démarrer l’outil de planification et à commencer à concevoir l’infrastructure Lync Server 2013 proposée.</span><span class="sxs-lookup"><span data-stu-id="50e78-104">After you have finished installing the Lync Server 2013, Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Lync Server 2013 infrastructure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="50e78-105">L’outil de planification est un outil piloté par un Assistant, avec des guides détaillés pour vous informer de votre processus de prise de décision lors de la conception de vos sites et de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="50e78-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="50e78-106">Cette rubrique n’est pas un guide exhaustif, mais pour vous aider à commencer à utiliser l’outil de planification dans vos sessions de conception.</span><span class="sxs-lookup"><span data-stu-id="50e78-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="50e78-107">Pour commencer à utiliser l’Outil de planification et à créer la conception initiale</span><span class="sxs-lookup"><span data-stu-id="50e78-107">To get started using the Planning Tool and create the initial design</span></span>

1.  <span data-ttu-id="50e78-108">Démarrez l’outil de planification Lync Server 2013: cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, **Microsoft Lync Server 2013**, puis sur **Outil de planification**.</span><span class="sxs-lookup"><span data-stu-id="50e78-108">Start the Lync Server 2013, Planning Tool: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Planning Tool**.</span></span>

2.  <span data-ttu-id="50e78-109">Une fois que l’outil de planification a démarré, la page **Bienvenue dans l’outil de planification pour Microsoft Lync Server 2013** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="50e78-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Microsoft Lync Server 2013** page appears.</span></span> <span data-ttu-id="50e78-110">Choisissez l’une des options suivantes pour commencer votre conception :</span><span class="sxs-lookup"><span data-stu-id="50e78-110">Choose one of the following options to begin your design:</span></span>
    
      - <span data-ttu-id="50e78-111">**Option 1 : prise en main**     Le fait de cliquer sur **prise en main** fournit une série spécifique de questions d’entretien avec des sélections appropriées pour définir les critères.</span><span class="sxs-lookup"><span data-stu-id="50e78-111">**Option 1: Get Started**   Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="50e78-112">Lorsque vous en avez terminé avec la section **Démarrage** initiale, poursuivez avec **Concevoir des sites** pour définir l’architecture de votre site.</span><span class="sxs-lookup"><span data-stu-id="50e78-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="50e78-113">Pour achever cette option, passez à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="50e78-113">To complete this option, proceed to step 3.</span></span>
    
      - <span data-ttu-id="50e78-114">**Option 2 : concevoir des sites**     En cliquant sur **concevoir des sites** sur la page d’accueil, vous ignorez les questions d’entretien présentées dans la section **prise en main** .</span><span class="sxs-lookup"><span data-stu-id="50e78-114">**Option 2: Design Sites**   Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="50e78-115">Les informations qui auraient été collectées en répondant aux questions de l’entretien dans la section **prise en main** sont définies sur les valeurs par défaut avec cette option.</span><span class="sxs-lookup"><span data-stu-id="50e78-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="50e78-116">En cliquant sur **concevoir des sites**, le concepteur expérimenté peut contourner l’entretien initial et modifier les valeurs par défaut, selon vos besoins, sur la page de démarrage des **sites centraux** .</span><span class="sxs-lookup"><span data-stu-id="50e78-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="50e78-117">Pour achever cette option, ignorez les étapes 3 à 5 et passez directement à l’étape 6.</span><span class="sxs-lookup"><span data-stu-id="50e78-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>
    
      - <span data-ttu-id="50e78-118">**Option 3 : afficher la topologie enregistrée**     Si vous avez déjà terminé et enregistré une topologie à l’aide de l’outil de planification précédemment, vous pouvez ignorer la plupart de ces étapes et commencer par ouvrir et afficher la topologie.</span><span class="sxs-lookup"><span data-stu-id="50e78-118">**Option 3: Display Your Saved Topology**   If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="50e78-119">Vous pouvez également effectuer des modifications et des mises à jour de la topologie, la réenregistrer, puis l’exporter vers Microsoft Excel ou Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="50e78-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="50e78-120">Pour achever cette option, ignorez les étapes 3 à 12 et passez directement à l’étape 13.</span><span class="sxs-lookup"><span data-stu-id="50e78-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3.  <span data-ttu-id="50e78-121">Cliquez sur **prise en main** pour commencer à concevoir votre topologie Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="50e78-121">Click **Get Started** to begin designing your Lync Server 2013 topology.</span></span>

4.  <span data-ttu-id="50e78-122">Répondez à chaque rubrique en sélectionnant les critères appropriés pour votre conception, puis cliquez sur **Suivant** pour passer à la page suivante de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="50e78-122">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page.</span></span> <span data-ttu-id="50e78-123">Cliquez sur **précédent** pour modifier les pages précédentes.</span><span class="sxs-lookup"><span data-stu-id="50e78-123">Click **Back** to make changes on previous pages.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="50e78-124">Chaque page contient une description des critères de sélection et des recommandations basées sur les pratiques préférées et la planification de la capacité.</span><span class="sxs-lookup"><span data-stu-id="50e78-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="50e78-125">Si vous avez besoin de détails supplémentaires, cliquez sur <STRONG>en savoir plus</STRONG> pour consulter des informations détaillées dans la documentation de planification de Lync Server 2013 sur le site Web Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="50e78-125">If you require additional details, click <STRONG>Learn more</STRONG> to read detailed information from the Lync Server 2013 Planning documentation on the Microsoft TechNet website.</span></span> <span data-ttu-id="50e78-126">Vous devez disposer d’une connexion à Internet pour accéder au site Web Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="50e78-126">You must have Internet connectivity to access the Microsoft TechNet website.</span></span>

    
    </div>

5.  <span data-ttu-id="50e78-127">Sélectionnez les options appropriées pour votre conception.</span><span class="sxs-lookup"><span data-stu-id="50e78-127">Select the appropriate options for your design.</span></span> <span data-ttu-id="50e78-128">Une fois les critères initiaux définis, une page viendra confirmer que votre vue d’ensemble des fonctionnalités est complète.</span><span class="sxs-lookup"><span data-stu-id="50e78-128">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6.  <span data-ttu-id="50e78-129">Cliquez sur **concevoir des sites** pour définir votre site central.</span><span class="sxs-lookup"><span data-stu-id="50e78-129">Click **Design Sites** to define your central site.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="50e78-130">Chaque topologie Lync Server 2013 aura au moins un site central.</span><span class="sxs-lookup"><span data-stu-id="50e78-130">Each Lync Server 2013 topology will have at least one central site.</span></span> <span data-ttu-id="50e78-131">Votre conception peut avoir un seul site central, un site central avec un certain nombre de sites de succursale, un certain nombre de sites centraux ou un certain nombre de sites centraux avec des sites de succursale associés à chaque site central.</span><span class="sxs-lookup"><span data-stu-id="50e78-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

    
    </div>

7.  <span data-ttu-id="50e78-132">Dans **nom du site**, tapez le nom qui identifiera ce site central.</span><span class="sxs-lookup"><span data-stu-id="50e78-132">In **Site Name**, type the name that will identify this central site.</span></span>

8.  <span data-ttu-id="50e78-133">Dans **utilisateurs hébergés**sur le site, tapez le nombre d’utilisateurs simultanés locaux attendus qui seront hébergés dans ce site central.</span><span class="sxs-lookup"><span data-stu-id="50e78-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9.  <span data-ttu-id="50e78-134">Dans **utilisateurs hébergés**dans le Cloud, tapez le nombre d’utilisateurs simultanés en ligne attendus qui seront hébergés dans ce site central.</span><span class="sxs-lookup"><span data-stu-id="50e78-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="50e78-135">Modifiez les sélections pour la collaboration en ligne, les utilisateurs, la voix, les options de déploiement supplémentaires ou les applications serveur, selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="50e78-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="50e78-136">À ce stade de la conception, vous pouvez uniquement sélectionner ou effacer les options de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="50e78-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="50e78-137">Toutefois, vous pouvez configurer d’autres options dans une phase ultérieure de l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="50e78-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="50e78-138">Certaines options sont également indisponibles et ne peuvent pas être désactivées.</span><span class="sxs-lookup"><span data-stu-id="50e78-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="50e78-139">En outre, vous pouvez être amené à désactiver une option pour en désactiver une autre.</span><span class="sxs-lookup"><span data-stu-id="50e78-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="50e78-140">Par exemple, si vous désactivez l’option <STRONG>voix entreprise</STRONG> sous voix, les options <STRONG>Response Group</STRONG>, <STRONG>announcer</STRONG>et <STRONG>parcage d’appel</STRONG> sous applications serveur (toutes les fonctionnalités de voix entreprise) sont également désactivées.</span><span class="sxs-lookup"><span data-stu-id="50e78-140">For example, if you clear the <STRONG>Enterprise Voice</STRONG> option under Voice, then the <STRONG>Response Group</STRONG>, <STRONG>Announcement</STRONG>, and <STRONG>Call Park</STRONG> options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

    
    </div>

11. <span data-ttu-id="50e78-141">Après avoir défini le nom du site et le nombre d’utilisateurs, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="50e78-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="50e78-142">Les pages suivantes demandent des informations sur les domaines SIP, les paramètres de conférence, les paramètres vocaux et l’infrastructure, la messagerie unifiée Exchange, l’accès des utilisateurs externes, les paramètres de conversation permanente, les paramètres du client, les options de colocalisation et les sites de succursale.</span><span class="sxs-lookup"><span data-stu-id="50e78-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="50e78-143">Répondez à toutes ces questions selon le cas.</span><span class="sxs-lookup"><span data-stu-id="50e78-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="50e78-144">La dernière question demande si vous souhaitez créer un autre site central.</span><span class="sxs-lookup"><span data-stu-id="50e78-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="50e78-145">Si vous sélectionnez **Oui**, l’outil de planification revient à la page sites centraux.</span><span class="sxs-lookup"><span data-stu-id="50e78-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="50e78-146">Si vous sélectionnez **non**, cliquez sur **suivant**, puis sur **dessiner** pour afficher la vue topologique globale de haut niveau.</span><span class="sxs-lookup"><span data-stu-id="50e78-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="50e78-147">Pour afficher une topologie existante, cliquez sur **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="50e78-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="50e78-148">Cliquez sur le fichier .xml qui représente la topologie précédemment enregistrée, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="50e78-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="50e78-149">L’outil de planification affiche la page topologie globale.</span><span class="sxs-lookup"><span data-stu-id="50e78-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="50e78-150">Vous pouvez maintenant commencer à modifier, mettre à jour ou modifier la topologie à l’aide des outils disponibles dans l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="50e78-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50e78-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="50e78-151">See Also</span></span>


[<span data-ttu-id="50e78-152">Modification de la conception dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50e78-152">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

