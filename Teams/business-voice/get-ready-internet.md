---
title: Vérifier la vitesse de votre connexion Internet pour Business Voice
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17eca42d01bcfb8a6b440c16408f31f6301b0338
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2020
ms.locfileid: "41268710"
---
# <a name="check-your-internet-connection-for-business-voice"></a><span data-ttu-id="74082-102">Vérifier la vitesse de votre connexion Internet pour Business Voice</span><span class="sxs-lookup"><span data-stu-id="74082-102">Check your Internet connection for Business Voice</span></span>

<span data-ttu-id="74082-103">Business Voice réside dans le cloud avec Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74082-103">Business Voice is located in the cloud with Microsoft 365.</span></span> <span data-ttu-id="74082-104">Tous les appareils utilisant Microsoft Teams et Business Voice ont besoin d’une connexion Internet.</span><span class="sxs-lookup"><span data-stu-id="74082-104">Every computer and device that uses Microsoft Teams and Business Voice needs a connection to the Internet.</span></span>

<span data-ttu-id="74082-105">Pour tirer le meilleur parti de Business Voice, une connexion Internet haut débit capable de prendre en charge le nombre d’appels téléphoniques maximum que votre organisation à tout moment est recommandée.</span><span class="sxs-lookup"><span data-stu-id="74082-105">To get the best experience with Business Voice, you need a broadband Internet connection that can support the expected number of phone calls that will be made at any one time.</span></span> <span data-ttu-id="74082-106">Vous devez également vous assurer que les ordinateurs de votre réseau peuvent accéder aux serveurs Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74082-106">You also need to make sure that computers on your network can reach Microsoft 365 servers.</span></span>

<span data-ttu-id="74082-107">Pour appliquer cette procédure, vous devez disposer d’un client avec l’un des abonnements suivants :</span><span class="sxs-lookup"><span data-stu-id="74082-107">To follow these steps, you need to have a tenant with one of the following subscriptions:</span></span>

* <span data-ttu-id="74082-108">Office 365 Business Essentials</span><span class="sxs-lookup"><span data-stu-id="74082-108">Office 365 Business Essentials</span></span>
* <span data-ttu-id="74082-109">Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="74082-109">Office 365 Business Premium</span></span>
* <span data-ttu-id="74082-110">Office 365 E1</span><span class="sxs-lookup"><span data-stu-id="74082-110">Office 365 E1</span></span>
* <span data-ttu-id="74082-111">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="74082-111">Office 365 E3</span></span>
* <span data-ttu-id="74082-112">Office 365 F1</span><span class="sxs-lookup"><span data-stu-id="74082-112">Office 365 F1</span></span>
* <span data-ttu-id="74082-113">Microsoft 365 A1</span><span class="sxs-lookup"><span data-stu-id="74082-113">Microsoft 365 A1</span></span>
* <span data-ttu-id="74082-114">Microsoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="74082-114">Microsoft 365 A3</span></span>
* <span data-ttu-id="74082-115">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="74082-115">Microsoft 365 E3</span></span>
* <span data-ttu-id="74082-116">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="74082-116">Microsoft 365 Business</span></span>

<span data-ttu-id="74082-117">Vous n’avez pas besoin d’une licence Business Voice pour suivre cette procédure.</span><span class="sxs-lookup"><span data-stu-id="74082-117">You don't need a Business Voice license to follow these steps.</span></span>

## <a name="check-your-internet-connection-speed"></a><span data-ttu-id="74082-118">Vérifier la vitesse de votre connexion Internet</span><span class="sxs-lookup"><span data-stu-id="74082-118">Check your Internet connection speed</span></span>

<span data-ttu-id="74082-119">Cet article aide à déterminer si votre connexion Internet est suffisamment rapide pour le nombre de personnes qui ont à effectuer des appels téléphoniques et à héberger des vidéoconférences.</span><span class="sxs-lookup"><span data-stu-id="74082-119">This article helps you determine whether your Internet connection is fast enough for the number of people who need to make phone calls, host video conferences, and so on.</span></span> <span data-ttu-id="74082-120">Vous allez fournir des informations sur votre organisation et obtenir un rapport indiquant dans quelle mesure votre connexion Internet sera utilisée par Teams et Business Voice.</span><span class="sxs-lookup"><span data-stu-id="74082-120">You'll enter some information about your organization and get back a report with how much of your Internet connection will be used by Teams and Business Voice.</span></span>

### <a name="gather-information-about-your-internet-connection-and-users"></a><span data-ttu-id="74082-121">Collecter des informations sur votre connexion Internet et vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="74082-121">Get information about your Internet connection and users</span></span>

<span data-ttu-id="74082-122">Avant de commencer, vous avez besoin des informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="74082-122">Before you start, you need to know the following information:</span></span>

* <span data-ttu-id="74082-123">La vitesse de votre connexion Internet</span><span class="sxs-lookup"><span data-stu-id="74082-123">The speed of your Internet connection.</span></span>
* <span data-ttu-id="74082-124">Le nombre de personnes qui utiliseront Business Voice principalement à partir de vos bureaux</span><span class="sxs-lookup"><span data-stu-id="74082-124">How many people will use Business Voice mainly from your office.</span></span>
* <span data-ttu-id="74082-125">Le nombre de personnes qui utiliseront Business Voice principalement à partir d’un emplacement distant, par exemple en télétravail</span><span class="sxs-lookup"><span data-stu-id="74082-125">How many people will use Business Voice mainly from a remote location, such as a home office.</span></span>

### <a name="enter-your-information-into-the-network-planner"></a><span data-ttu-id="74082-126">Entrer vos informations dans le Planificateur de réseau</span><span class="sxs-lookup"><span data-stu-id="74082-126">Enter your information into the network planner</span></span>

<span data-ttu-id="74082-127">Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="74082-127">Follow these steps:</span></span>

1. <span data-ttu-id="74082-128">Dans un navigateur, accédez à https://admin.teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="74082-128">In a browser, go to https://admin.teams.microsoft.com.</span></span> <span data-ttu-id="74082-129">Connectez-vous à l’aide d’un compte disposant des autorisations d’administrateur général.</span><span class="sxs-lookup"><span data-stu-id="74082-129">Sign in by using an account that has Global Administrator permissions.</span></span> <span data-ttu-id="74082-130">Le compte que vous avez utilisé pour vous inscrire à Office 365 dispose de ces autorisations.</span><span class="sxs-lookup"><span data-stu-id="74082-130">The account you used to sign up for Office 365 has these permissions.</span></span>
2. <span data-ttu-id="74082-131">Ouvrez **Planification**, puis sélectionnez **Planificateur de réseau**.</span><span class="sxs-lookup"><span data-stu-id="74082-131">Open **Planning** and then select **Network planner**.</span></span>
3. <span data-ttu-id="74082-132">Sous **Plans réseau**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="74082-132">Under **Network plans**, select **Add**.</span></span> <span data-ttu-id="74082-133">Entrez un nom à votre plan, puis sélectionnez **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="74082-133">Enter a name for your plan, and then select **Apply**.</span></span> <span data-ttu-id="74082-134">Votre plan réseau doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="74082-134">Your network plan should look like this:</span></span>

    ![Écran principal du Planificateur de réseau](../media/network-planner-main.png)
1. <span data-ttu-id="74082-136">Sélectionnez le nom de votre plan de réseau.</span><span class="sxs-lookup"><span data-stu-id="74082-136">Select the name of your network plan.</span></span> <span data-ttu-id="74082-137">(C'est le **bureau principale** dans l’image précédente.)</span><span class="sxs-lookup"><span data-stu-id="74082-137">(It's **Main office** in the preceding picture.)</span></span>
2. <span data-ttu-id="74082-138">Sur la page suivante, sélectionnez **Ajouter un site réseau** dans l’onglet **Sites réseau**.</span><span class="sxs-lookup"><span data-stu-id="74082-138">On the next page, select **Add a network site** under the **Network sites** tab.</span></span>
3. <span data-ttu-id="74082-139">Renseignez uniquement les champs indiqués dans la capture d’écran suivante, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="74082-139">Fill in only the fields indicated in the screenshot below and then select **Save**.</span></span> <span data-ttu-id="74082-140">Laissez les autres champs vides dans cet écran, et ne sélectionnez pas les options **ExpressRoute** ou **connecté au réseau étendu**.</span><span class="sxs-lookup"><span data-stu-id="74082-140">Leave the other fields on this screen blank, and don't select either the **ExpressRoute** or **Connected to WAN** options.</span></span>

    ![Informations sur le site du Planificateur de réseau](../media/network-planner-site-info.png)
1. <span data-ttu-id="74082-142">Dans l’onglet **Rapport**, sélectionnez **Démarrer un rapport**.</span><span class="sxs-lookup"><span data-stu-id="74082-142">Under the **Report** tab, select **Start a report**.</span></span>
1. <span data-ttu-id="74082-143">Entrez les informations suivantes, puis sélectionnez **Générer un rapport** pour créer un rapport qui indique les exigences en matière de bande passante pour Teams.</span><span class="sxs-lookup"><span data-stu-id="74082-143">Fill out the following information and then select **Generate report** to create a report showing the bandwidth requirements for Teams.</span></span> <span data-ttu-id="74082-144">Nous allons vous montrer comment lire le rapport dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="74082-144">We'll show you how to read the report in the next section.</span></span>

    ![Informations sur le rapport du Planificateur de réseau](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a><span data-ttu-id="74082-146">Identifier votre vitesse de connexion Internet minimale</span><span class="sxs-lookup"><span data-stu-id="74082-146">Find your minimum Internet connection speed</span></span>

<span data-ttu-id="74082-147">Lorsque vous sélectionnez **Générer un rapport**, Office 365 crée un rapport semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="74082-147">When you select **Generate report**, Office 365 creates a report that looks like this:</span></span>

![Détails du rapport du Planificateur de réseau](../media/network-planner-report.png)

<span data-ttu-id="74082-149">Le chiffre mis en surbrillance indique la part de votre connexion Internet utilisée par Teams et Business Voice.</span><span class="sxs-lookup"><span data-stu-id="74082-149">The highlighted number shows how much of your Internet connection Teams and Business Voice will use.</span></span> <span data-ttu-id="74082-150">Nous vous recommandons de faire en sorte que ce chiffre ne dépasse pas 30 % de la vitesse totale de votre connexion Internet.</span><span class="sxs-lookup"><span data-stu-id="74082-150">We recommend that this number be no more than 30% of your total Internet connection speed.</span></span> <span data-ttu-id="74082-151">Par exemple, si votre connexion Internet est de 60 Mbits/s, Teams et Business Voice ne doivent pas utiliser plus de 18 Mbits/s.</span><span class="sxs-lookup"><span data-stu-id="74082-151">For example, if your Internet connection is 60Mbps, Teams and Business Voice should take up no more than 18Mbps.</span></span>

<span data-ttu-id="74082-152">Utilisez les équations suivantes pour déterminer votre vitesse de connexion Internet minimum : *\<nombre mis en surbrillance> / 0,3*.</span><span class="sxs-lookup"><span data-stu-id="74082-152">Use this equation to determine your minimum Internet connection speed: *\<highlighted number> / 0.3*.</span></span> <span data-ttu-id="74082-153">Avec le nombre mis en surbrillance dans l’image précédente, le calcul est *4,6875 / 0,3 = 15,6*.</span><span class="sxs-lookup"><span data-stu-id="74082-153">With the number that's highlighted in the preceding image, the calculation is *4.6875 / 0.3 = 15.6*.</span></span> <span data-ttu-id="74082-154">Dans ce cas, la vitesse de connexion Internet doit être d’au moins 15,6 Mbps.</span><span class="sxs-lookup"><span data-stu-id="74082-154">In this case, the Internet connection speed should be at least 15.6 Mbps.</span></span>

<span data-ttu-id="74082-155">Si Teams et Business Voice utilisent plus de 30 % de la vitesse de connexion Internet totale, le chiffre mis en surbrillance s’affiche en rouge.</span><span class="sxs-lookup"><span data-stu-id="74082-155">If Teams and Business Voice will use more than 30% of your total Internet connection speed, the highlighted number will show up as red.</span></span> <span data-ttu-id="74082-156">Dans ce cas, vous devrez peut-être mettre à niveau votre connexion Internet.</span><span class="sxs-lookup"><span data-stu-id="74082-156">In that case, you may need to upgrade your Internet connection.</span></span>

![Avertissement de vitesse de connexion](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a><span data-ttu-id="74082-158">S’assurer que les ordinateurs et les appareils de votre réseau peuvent accéder à Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="74082-158">Make sure computers and devices on your network can reach Microsoft 365</span></span>

<span data-ttu-id="74082-159">Les ordinateurs et appareils qui utilisent Business Voice doivent utiliser des ports réseau spécifiques pour communiquer avec les serveurs Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74082-159">Computers and devices that use Business Voice must use specific network ports to communicate with Microsoft 365 servers.</span></span> <span data-ttu-id="74082-160">Ces ports fonctionnent comme des portes via lesquelles les appareils communiquent entre eux sur un réseau ou sur Internet.</span><span class="sxs-lookup"><span data-stu-id="74082-160">Network ports are essentially doors through which computers and devices can talk to each other over a network or the Internet.</span></span> <span data-ttu-id="74082-161">Votre pare-feu doit autoriser les appareils de votre réseau à accéder à Microsoft 365 sur les ports réseau *sortants* suivants :</span><span class="sxs-lookup"><span data-stu-id="74082-161">Your firewall needs to allow computers and devices on your network to reach Microsoft 365 using the following outbound network ports:</span></span>

* <span data-ttu-id="74082-162">**Ports TCP** 80 et 443</span><span class="sxs-lookup"><span data-stu-id="74082-162">**TCP ports** 80 and 443</span></span>
* <span data-ttu-id="74082-163">**Ports UDP** 3478, 3479, 3480 et 3481</span><span class="sxs-lookup"><span data-stu-id="74082-163">**UDP ports** 3478, 3479, 3480, and 3481</span></span>

<span data-ttu-id="74082-164">Le moyen le plus simple de vérifier si votre pare-feu autorise la communication sur ces ports réseau consiste à effectuer un appel de test dans Teams :</span><span class="sxs-lookup"><span data-stu-id="74082-164">The easiest way to check whether your firewall allows communication on these network ports is to make a test call using Teams.</span></span>

1. <span data-ttu-id="74082-165">Accédez à https://aka.ms/getteams sur un ordinateur de votre réseau et installez Teams.</span><span class="sxs-lookup"><span data-stu-id="74082-165">Go to https://aka.ms/getteams on a computer on your network to install Teams.</span></span> <span data-ttu-id="74082-166">Assurez-vous que l’ordinateur possède des haut-parleurs et un microphone.</span><span class="sxs-lookup"><span data-stu-id="74082-166">Make sure that the computer has speakers and a microphone.</span></span>
2. <span data-ttu-id="74082-167">Ouvrez Teams et connectez-vous à l’aide d’un compte Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74082-167">Open Teams and sign in using a Microsoft 365 account</span></span>
3. <span data-ttu-id="74082-168">Dans Teams, sélectionnez votre image de profil, puis accédez à **Paramètres** > **Périphériques**.</span><span class="sxs-lookup"><span data-stu-id="74082-168">In Teams, select your profile picture, then **Settings** > **Devices**</span></span>
4. <span data-ttu-id="74082-169">Sous **Périphériques audio**, sélectionnez **Passer un appel de test**.</span><span class="sxs-lookup"><span data-stu-id="74082-169">Under **Audio devices**, select **Make a test call**.</span></span>
5. <span data-ttu-id="74082-170">Suivez les tapes pour laisser un message et l’écouter ensuite.</span><span class="sxs-lookup"><span data-stu-id="74082-170">Follow the prompts to leave a message and have it played back to you</span></span>

   * <span data-ttu-id="74082-171">Si l’appel aboutit et que vous entendez votre message, votre pare-feu est correctement configuré.</span><span class="sxs-lookup"><span data-stu-id="74082-171">If the call connects and you can hear your message played back to you, your firewall is set up correctly.</span></span>
   * <span data-ttu-id="74082-172">Si l’appel aboutit mais que vous ne parvenez pas à entendre les instructions ou votre message, assurez-vous que vos haut-parleurs et votre microphone sont correctement configurés, puis réessayez.</span><span class="sxs-lookup"><span data-stu-id="74082-172">If the call connects but you can't hear the prompts or your message played back to you, make sure your speakers and microphone are set up correctly and detected by the computer.</span></span>
   * <span data-ttu-id="74082-173">Si l’appel n’aboutit pas, ou s’il aboutit mais que vous ne pouvez pas écouter votre message, vous devrez peut-être mettre à jour votre pare-feu afin d’autoriser pour autoriser l’accès aux ports réseau nécessaires.</span><span class="sxs-lookup"><span data-stu-id="74082-173">If the call doesn't connect or if it does but you can't hear your message played back to you, you might need to update your firewall to allow the network ports listed above.</span></span> <span data-ttu-id="74082-174">Consultez la documentation de votre pare-feu ou contactez un spécialiste informatique pour obtenir de l’aide.</span><span class="sxs-lookup"><span data-stu-id="74082-174">Check your firewall's documentation, or contact an IT specialist for help.</span></span>

 <span data-ttu-id="74082-175">Si vous êtes un professionnel de l’informatique et que vous avez besoin d’informations supplémentaires sur la préparation de réseaux plus vastes ou plus complexes afin de prendre en charge Business Voice, consultez l’article [Évaluer mon environnement](../3-envision-evaluate-my-environment.md).</span><span class="sxs-lookup"><span data-stu-id="74082-175">If you're an IT professional and want more information about how to prepare larger or more complex networks to support Business Voice, take a look at [Evaluate my environment](../3-envision-evaluate-my-environment.md).</span></span> <span data-ttu-id="74082-176">Cet article fournit des informations sur les exigences en matière de bande passante, de proxy et de pare-feu, et l’utilisation de l’[Outil d’évaluation du réseau](../3-envision-evaluate-my-environment.md#test-the-network) pour tester votre réseau.</span><span class="sxs-lookup"><span data-stu-id="74082-176">This article provides information about bandwidth, proxy and firewall requirements, and how to use the [Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network) to test your network.</span></span>

