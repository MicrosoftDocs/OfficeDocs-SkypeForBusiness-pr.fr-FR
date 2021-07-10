---
title: Options de connectivité PSTN
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 07/08/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: En savoir plus sur les options Teams d’appel (connectivité PSTN) et les décisions que vous prendrez pour votre organisation.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b1b06178b269529b1d0227ff02d529c91ba1480
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354516"
---
# <a name="pstn-connectivity-options"></a><span data-ttu-id="224f6-103">Options de connectivité PSTN</span><span class="sxs-lookup"><span data-stu-id="224f6-103">PSTN connectivity options</span></span>

<span data-ttu-id="224f6-104">Microsoft fournit des fonctionnalités complètes de Exchange de branche privée (PBX) pour votre organisation via Système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="224f6-104">Microsoft provides complete Private Branch Exchange (PBX) capabilities for your organization through Phone System.</span></span> <span data-ttu-id="224f6-105">Toutefois, pour permettre aux utilisateurs de passer des appels en dehors de votre organisation, vous devez vous Système téléphonique au réseau téléphonique public commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="224f6-105">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="224f6-106">Cet article se concentre sur les options de connectivité PSTN.</span><span class="sxs-lookup"><span data-stu-id="224f6-106">This article focuses on PSTN connectivity options.</span></span> <span data-ttu-id="224f6-107">Pour plus d’informations sur les solutions vocales Microsoft et les détails sur Système téléphonique fonctionnalités, voir [Planifier Teams solution vocale proposée.](cloud-voice-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="224f6-107">For more information about Microsoft voice solutions, incuding details about Phone System features, see [Plan your Teams voice solution](cloud-voice-landing-page.md).</span></span>

<span data-ttu-id="224f6-108">Pour vous Système téléphonique au réseau PSTN, vous avez le choix entre les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="224f6-108">To connect Phone System to the PSTN, you can choose from the following options:</span></span>

- <span data-ttu-id="224f6-109">[**Forfait d’appels.**](#phone-system-with-calling-plan)</span><span class="sxs-lookup"><span data-stu-id="224f6-109">[**Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="224f6-110">Une solution all-in-the-cloud avec Microsoft comme opérateur PSTN.</span><span class="sxs-lookup"><span data-stu-id="224f6-110">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="224f6-111">[**Routage direct,**](#phone-system-with-direct-routing)qui vous permet d’utiliser votre propre opérateur PSTN en connectant votre ou vos contrôleurs de session (SBC) à Système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="224f6-111">[**Direct Routing**](#phone-system-with-direct-routing), which enables you to use your own PSTN carrier by connecting your Session Border Controller(s) (SBC) to Phone System.</span></span>

- <span data-ttu-id="224f6-112">[**L’Connecter**](#phone-system-with-operator-connect),qui est actuellement disponible uniquement en **prévisualisation publique.**</span><span class="sxs-lookup"><span data-stu-id="224f6-112">[**Operator Connect**](#phone-system-with-operator-connect), which is currently available only in **public preview.**</span></span>  <span data-ttu-id="224f6-113">Grâce aux Connecter opérateurs, si votre opérateur existant participe au programme Microsoft Operator Connecter ( Opérateur Microsoft), il peut gérer les contrôleurs de session et d’appel RTC.</span><span class="sxs-lookup"><span data-stu-id="224f6-113">With Operator Connect, if your existing carrier is a participant in the Microsoft Operator Connect program, they can manage PSTN calling and Session Border Controllers (SBCs).</span></span> 

<span data-ttu-id="224f6-114">Vous pouvez également choisir une combinaison d’options qui vous permet de concevoir une solution pour un environnement complexe ou de gérer une migration en plusieurs étapes.</span><span class="sxs-lookup"><span data-stu-id="224f6-114">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration.</span></span>

<span data-ttu-id="224f6-115">N’ignorez pas que les options que vous choisissez affectent la manière dont Système téléphonique fonctionnalités sont configurées.</span><span class="sxs-lookup"><span data-stu-id="224f6-115">Be aware that the option or options you choose affect how some Phone System features are configured.</span></span> <span data-ttu-id="224f6-116">Pour plus d’informations, voir [les considérations concernant la configuration](#configuration-considerations) plus loin dans cet article.</span><span class="sxs-lookup"><span data-stu-id="224f6-116">For more information, see [Configuration considerations](#configuration-considerations) later in this article.</span></span>


## <a name="phone-system-with-calling-plan"></a><span data-ttu-id="224f6-117">Système téléphonique forfait d’appels</span><span class="sxs-lookup"><span data-stu-id="224f6-117">Phone System with Calling Plan</span></span> 

<span data-ttu-id="224f6-118">Système téléphonique’aide du forfait d’appels est la solution vocale tout-en-cloud de Microsoft pour les Teams cloud.</span><span class="sxs-lookup"><span data-stu-id="224f6-118">Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="224f6-119">Il s’agit de l’option la plus simple qui Système téléphonique au réseau PSTN.</span><span class="sxs-lookup"><span data-stu-id="224f6-119">This is the simplest option that connects Phone System to the PSTN.</span></span> <span data-ttu-id="224f6-120">Avec cette option, Microsoft agit en tant qu’opérateur PSTN, comme illustré dans le diagramme suivant :</span><span class="sxs-lookup"><span data-stu-id="224f6-120">With this option, Microsoft acts as your PSTN carrier, as shown in the following diagram:</span></span>

![Le diagramme 1 montre les Système téléphonique’aide de Forfait d’appels](media/voice-solutions-simple.png)

<span data-ttu-id="224f6-122">Si vous répondez oui aux questions suivantes, alors Système téléphonique’aide du plan d’appels est la solution adaptée à vos questions :</span><span class="sxs-lookup"><span data-stu-id="224f6-122">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="224f6-123">Le forfait d’appels est disponible dans votre région.</span><span class="sxs-lookup"><span data-stu-id="224f6-123">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="224f6-124">Vous n’avez pas besoin de conserver votre opérateur PSTN actuel.</span><span class="sxs-lookup"><span data-stu-id="224f6-124">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="224f6-125">Vous voulez utiliser l’accès géré par Microsoft au réseau PSTN.</span><span class="sxs-lookup"><span data-stu-id="224f6-125">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="224f6-126">Avec cette option :</span><span class="sxs-lookup"><span data-stu-id="224f6-126">With this option:</span></span> 

- <span data-ttu-id="224f6-127">Vous recevez Téléphone Microsoft avec des plans d’appels nationaux ou internationaux ajoutés qui permettent d’appeler vers des téléphones dans le monde entier (selon le niveau de service sous licence).</span><span class="sxs-lookup"><span data-stu-id="224f6-127">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="224f6-128">Le déploiement ou la maintenance d’un déploiement local n’est pas nécessaire, car le plan d’appel &mdash; fonctionne Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="224f6-128">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365.</span></span>

- <span data-ttu-id="224f6-129">Remarque : si nécessaire, vous pouvez choisir de connecter un contrôleur de session border (SBC) pris en charge via un routage direct pour l’interopérabilité avec des PBX tiers, des appareils analogiques et d’autres équipements téléphoniques tiers pris en charge par le SBC.</span><span class="sxs-lookup"><span data-stu-id="224f6-129">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="224f6-130">Cette option nécessite une connexion ininterrompue à Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="224f6-130">This option requires uninterrupted connection to Microsoft 365.</span></span>

<span data-ttu-id="224f6-131">Pour plus d’informations sur le plan d’appels, consultez les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="224f6-131">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="224f6-132">Quelle forfait d’appels vous convient le mieux ?</span><span class="sxs-lookup"><span data-stu-id="224f6-132">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="224f6-133">Comment acheter un forfait d’appels</span><span class="sxs-lookup"><span data-stu-id="224f6-133">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="224f6-134">Disponibilité des forfaits d’appels par pays et par région</span><span class="sxs-lookup"><span data-stu-id="224f6-134">Country and region availability for Calling Plan</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [<span data-ttu-id="224f6-135">Configurer le forfait d’appels</span><span class="sxs-lookup"><span data-stu-id="224f6-135">Set up Calling Plan</span></span>](set-up-calling-plans.md)


## <a name="phone-system-with-direct-routing"></a><span data-ttu-id="224f6-136">Système téléphonique le routage direct</span><span class="sxs-lookup"><span data-stu-id="224f6-136">Phone System with Direct Routing</span></span>

<span data-ttu-id="224f6-137">Cette option connecte Système téléphonique réseau téléphonique à l’aide du routage direct, comme illustré dans le diagramme suivant :</span><span class="sxs-lookup"><span data-stu-id="224f6-137">This option connects Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![Le diagramme 5 montre les Système téléphonique routage direct](media/voice-solution-with-direct-routing.png)

<span data-ttu-id="224f6-139">Si vous répondez oui aux questions suivantes, Système téléphonique le routage direct est la solution adaptée à vos questions :</span><span class="sxs-lookup"><span data-stu-id="224f6-139">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="224f6-140">Vous voulez utiliser Teams’Système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="224f6-140">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="224f6-141">Vous devez conserver votre opérateur PSTN actuel.</span><span class="sxs-lookup"><span data-stu-id="224f6-141">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="224f6-142">Vous voulez mélanger le routage, certains appels passant par le plan d’appels, d’autres par l’intermédiaire de votre opérateur.</span><span class="sxs-lookup"><span data-stu-id="224f6-142">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="224f6-143">Vous devez interopérateur avec des SYSTÈMES PBX tiers et/ou des équipements tels que des pageurs de surcharge, des dispositifs analogiques, etc.</span><span class="sxs-lookup"><span data-stu-id="224f6-143">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="224f6-144">Avec cette option :</span><span class="sxs-lookup"><span data-stu-id="224f6-144">With this option:</span></span>

- <span data-ttu-id="224f6-145">Vous connectez votre propre contrôleur de session en bordure de session (SBC) à un Système téléphonique sans resserr un logiciel local supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="224f6-145">You connect your own supported Session Border Controller (SBC) to Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="224f6-146">Vous pouvez utiliser pratiquement n’importe quel opérateur téléphonique Système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="224f6-146">You can use virtually any telephony carrier with Phone System.</span></span>

- <span data-ttu-id="224f6-147">Vous pouvez choisir de configurer et de gérer cette option, ou elle peut être configurée et gérée par votre opérateur ou partenaire (demandez-lui si votre opérateur ou partenaire propose cette option).</span><span class="sxs-lookup"><span data-stu-id="224f6-147">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="224f6-148">Vous pouvez configurer l’interopérabilité entre votre équipement téléphonique, tel qu’un PBX tiers et des appareils &mdash; &mdash; analogiques, et Système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="224f6-148">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Phone System.</span></span>

<span data-ttu-id="224f6-149">Cette option nécessite les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="224f6-149">This option requires the following:</span></span>

- <span data-ttu-id="224f6-150">Connexion ininterrompue à Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="224f6-150">Uninterrupted connection to Microsoft 365.</span></span>

- <span data-ttu-id="224f6-151">Déploiement et maintenance d’un SBC pris en charge.</span><span class="sxs-lookup"><span data-stu-id="224f6-151">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="224f6-152">Contrat avec un opérateur tiers.</span><span class="sxs-lookup"><span data-stu-id="224f6-152">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="224f6-153">(Sauf dans le cadre du déploiement en tant qu’option de connexion au PBX tiers, aux périphériques analogiques ou à d’autres équipements téléphoniques pour les utilisateurs qui utilisent le Système téléphonique avec le plan d’appel.)</span><span class="sxs-lookup"><span data-stu-id="224f6-153">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="224f6-154">Pour plus d’informations sur le routage direct, voir les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="224f6-154">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="224f6-155">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="224f6-155">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="224f6-156">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="224f6-156">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="224f6-157">Gérer les stratégies de routage vocal pour les utiliser avec le routage direct</span><span class="sxs-lookup"><span data-stu-id="224f6-157">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="224f6-158">Planifier le routage géodépendant pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="224f6-158">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="224f6-159">Liste des contrôleurs de frontière de session certifiés pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="224f6-159">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)


## <a name="phone-system-with-operator-connect"></a><span data-ttu-id="224f6-160">Système téléphonique’opérateur Connecter</span><span class="sxs-lookup"><span data-stu-id="224f6-160">Phone System with Operator Connect</span></span>

<span data-ttu-id="224f6-161">Avec l’Connecter d’opérateur actuellement en prévisualisation publique, si votre opérateur existant participe au programme Connecter d’opérateur Microsoft, il peut gérer le service afin de mettre en place les appels R TEAMS.</span><span class="sxs-lookup"><span data-stu-id="224f6-161">With Operator Connect, currently in public preview, if your existing carrier is a participant in the Microsoft Operator Connect program, they can manage the service for bringing PSTN calling to Teams.</span></span> <span data-ttu-id="224f6-162">Votre opérateur gère les services d’appel PSTN et les contrôleurs de session en bordure, ce qui vous permet d’économiser sur l’achat et la gestion du matériel.</span><span class="sxs-lookup"><span data-stu-id="224f6-162">Your carrier manages the PSTN calling services and Session Border Controllers (SBCs), allowing you to save on hardware purchase and management.</span></span>

<span data-ttu-id="224f6-163">L’Connecter peut être la solution appropriée pour votre organisation si :</span><span class="sxs-lookup"><span data-stu-id="224f6-163">Operator Connect might be the right solution for your organization if:</span></span>

- <span data-ttu-id="224f6-164">Le plan d’appels Microsoft n’est pas disponible dans votre emplacement géographique.</span><span class="sxs-lookup"><span data-stu-id="224f6-164">Microsoft Calling Plan isn't available in your geographic location.</span></span>
- <span data-ttu-id="224f6-165">Votre opérateur préféré est un participant au programme d’Connecter Microsoft.</span><span class="sxs-lookup"><span data-stu-id="224f6-165">Your preferred carrier is a participant in the Microsoft Operator Connect program.</span></span>
- <span data-ttu-id="224f6-166">Vous souhaitez rechercher un nouvel opérateur pour activer les appels Teams.</span><span class="sxs-lookup"><span data-stu-id="224f6-166">You want to find a new carrier to enable calling in Teams.</span></span>

<span data-ttu-id="224f6-167">Pour plus d’informations sur les avantages et les conditions requises de la Connecter opérateur, et pour obtenir la liste des opérateurs participant à ce programme, consultez la liste des opérateurs [Connecter.](operator-connect-plan.md)</span><span class="sxs-lookup"><span data-stu-id="224f6-167">For information on the benefits and requirements of Operator Connect, and for a list of carriers participating in this program, see [Plan Operator Connect](operator-connect-plan.md).</span></span> <span data-ttu-id="224f6-168">Pour plus d’informations sur la configuration des opérateurs Connecter, voir [Configurer l’Connecter.](operator-connect-configure.md)</span><span class="sxs-lookup"><span data-stu-id="224f6-168">For information on how to configure Operator Connect, see [Configure Operator Connect](operator-connect-configure.md).</span></span>

## <a name="configuration-considerations"></a><span data-ttu-id="224f6-169">Considérations en cas de configuration</span><span class="sxs-lookup"><span data-stu-id="224f6-169">Configuration considerations</span></span>

<span data-ttu-id="224f6-170">La plupart Système téléphonique fonctionnalités sont identiques quelle que soit l’option de connectivité PSTN que vous choisissez.</span><span class="sxs-lookup"><span data-stu-id="224f6-170">Most Phone System features are the same regardless of the PSTN connectivity option you choose.</span></span> <span data-ttu-id="224f6-171">Par exemple, les paramètres Sans réponse et transfert d’appel, le transfert d’appel, la musique personnalisée mise en attente, le parcage d’appel, la ligne partagée et les applications vocales sont tous disponibles.</span><span class="sxs-lookup"><span data-stu-id="224f6-171">For example, call unanswered and forwarding settings, call transfer, custom music on hold, call park, shared line, and voice apps are all available.</span></span> <span data-ttu-id="224f6-172">Pour obtenir la liste complète des Système téléphonique fonctionnalités, consultez les fonctionnalités de la liste des [Système téléphonique.](here-s-what-you-get-with-phone-system.md)</span><span class="sxs-lookup"><span data-stu-id="224f6-172">For a complete list of Phone System features, see [Here's what you get with Phone System](here-s-what-you-get-with-phone-system.md).</span></span>

<span data-ttu-id="224f6-173">Il existe toutefois certaines différences de fonctionnalités qui affectent la façon dont vous configurez Système téléphonique fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="224f6-173">There are some differences in functionality, however, that affect how you configure certain Phone System features.</span></span> <span data-ttu-id="224f6-174">Par exemple, le routage direct nécessite des étapes supplémentaires pour configurer le routage des appels.</span><span class="sxs-lookup"><span data-stu-id="224f6-174">For example, Direct Routing requires additional steps to configure call routing.</span></span> <span data-ttu-id="224f6-175">Autre exemple : le routage direct fournit un routage basé sur l’emplacement (LBR) pour vous permettre de restreindre la dérivation contre les frais dans certains emplacements géographiques où il n’est pas autorisé.</span><span class="sxs-lookup"><span data-stu-id="224f6-175">As another example, Direct Routing provides Location-Based-Routing (LBR)--so that you can restrict toll bypass in certain geographic locations where it is not allowed.</span></span> 


### <a name="phone-number-management"></a><span data-ttu-id="224f6-176">Téléphone gestion des nombres</span><span class="sxs-lookup"><span data-stu-id="224f6-176">Phone number management</span></span>

<span data-ttu-id="224f6-177">Microsoft propose deux types de numéros de téléphone : les numéros d’abonnés (utilisateurs) qui peuvent être attribués à des utilisateurs de votre organisation et les numéros de service disponibles sous forme de numéros de service gratuits et gratuits.</span><span class="sxs-lookup"><span data-stu-id="224f6-177">Microsoft has two types of telephone numbers available: subscriber (user) numbers, which can be assigned to users in your organization, and service numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="224f6-178">Les numéros de service ont une capacité d’appels simultanés supérieure à celle des numéros d’abonné et peuvent être affectés à des services tels que les audioconférences, les attendants automatiques ou les files d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="224f6-178">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="224f6-179">Vous devrez décider des choix ci-après :</span><span class="sxs-lookup"><span data-stu-id="224f6-179">You will need to decide:</span></span>

- <span data-ttu-id="224f6-180">Quels emplacements utilisateur ont besoin de nouveaux numéros de téléphone de Microsoft ?</span><span class="sxs-lookup"><span data-stu-id="224f6-180">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="224f6-181">De quel type de numéro de téléphone (abonné ou service) ai-je besoin ?</span><span class="sxs-lookup"><span data-stu-id="224f6-181">Which type of telephone number (subscriber or service) do I need?</span></span>
- <span data-ttu-id="224f6-182">Comment puis-je porter des numéros de téléphone existants vers Teams ?</span><span class="sxs-lookup"><span data-stu-id="224f6-182">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="224f6-183">La façon dont vous acquérir et gérer les numéros de téléphone diffère selon votre option de connectivité PSTN.</span><span class="sxs-lookup"><span data-stu-id="224f6-183">How you acquire and manage phone numbers differs depending on your PSTN connectivity option.</span></span>

- <span data-ttu-id="224f6-184">Pour plus d’informations sur la gestion des numéros de téléphone pour le plan d’appels, voir [Gérer les numéros de téléphone pour votre organisation.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="224f6-184">For information about managing phone numbers for Calling Plan, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

- <span data-ttu-id="224f6-185">Pour plus d’informations sur la gestion des numéros de téléphone pour le routage direct, voir Configurer le numéro de téléphone et activer la messagerie vocale et la voix [d’entreprise.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)</span><span class="sxs-lookup"><span data-stu-id="224f6-185">For information about managing phone numbers for Direct Routing, see [Configure the phone number and enable enterprise voice and voicemail](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online).</span></span>

- <span data-ttu-id="224f6-186">Pour plus d’informations sur la gestion des numéros de téléphone avec la Connecter opérateur, voir Configurer des numéros de [téléphone avec l’opérateur Connecter.](operator-connect-configure.md#set-up-phone-numbers)</span><span class="sxs-lookup"><span data-stu-id="224f6-186">For information about managing phone numbers with Operator Connect, see [Set up phone numbers with Operator Connect](operator-connect-configure.md#set-up-phone-numbers).</span></span>


### <a name="call-routing-and-dial-plans"></a><span data-ttu-id="224f6-187">Routage des appels et plans de numérotation</span><span class="sxs-lookup"><span data-stu-id="224f6-187">Call routing and dial plans</span></span>

<span data-ttu-id="224f6-188">La manière dont vous configurez le routage des appels diffère selon l’option de connectivité RSTN.</span><span class="sxs-lookup"><span data-stu-id="224f6-188">How you configure call routing differs depending on your PSTN connectivity option.</span></span>  

- <span data-ttu-id="224f6-189">Pour les forfaits d’appels, la plupart du routage des appels est géré par l’infrastructure du plan d’appels Microsoft.</span><span class="sxs-lookup"><span data-stu-id="224f6-189">For Calling Plans, most of call routing is handled by the Microsoft Calling Plan infrastructure.</span></span> <span data-ttu-id="224f6-190">Vous configurez les plans de numérotation utilisateur en vue de la traduction des numéros à des fins d’autorisation et de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="224f6-190">You configure user dial plans for purposes of number translation for call authorization and call routing.</span></span> <span data-ttu-id="224f6-191">Pour plus d’informations, voir [Les plans de numérotation.](what-are-dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="224f6-191">For more information, see [What are dial plans?](what-are-dial-plans.md).</span></span>

- <span data-ttu-id="224f6-192">Pour le routage direct, vous devez configurer le routage des appels en spécifiant les itinéraires vocaux et en attribuant des stratégies de routage vocal aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="224f6-192">For Direct Routing, you must configure call routing by specifying the voice routes and assigning voice routing policies to users.</span></span> <span data-ttu-id="224f6-193">Vous pouvez configurer des plans de numérotation pour la traduction des numéros sur le niveau de ligne afin de garantir l’interopérabilité avec les contrôleurs de session en bordure (SBCs).</span><span class="sxs-lookup"><span data-stu-id="224f6-193">You can configure dial plans for number translation at the trunk level to ensure interoperability with Session Border Controllers (SBCs).</span></span> <span data-ttu-id="224f6-194">Pour plus d’informations, voir Configurer le routage vocal pour le [routage](direct-routing-voice-routing.md)direct, Gérer les stratégies de [routage](manage-voice-routing-policies.md) vocal et [Traduire les numéros de téléphone.](direct-routing-translate-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="224f6-194">For more information, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md), [Manage voice routing policies](manage-voice-routing-policies.md) and [Translate phone numbers](direct-routing-translate-numbers.md).</span></span> 

- <span data-ttu-id="224f6-195">Pour l’Connecter, la plupart du routage des appels est géré par l’opérateur.</span><span class="sxs-lookup"><span data-stu-id="224f6-195">For Operator Connect, most of call routing is managed by the carrier.</span></span>  <span data-ttu-id="224f6-196">Vous configurez les plans de numérotation utilisateur en vue de la traduction des numéros à des fins d’autorisation et de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="224f6-196">You configure user dial plans for purposes of number translation for call authorization and call routing.</span></span> <span data-ttu-id="224f6-197">Pour plus d’informations, voir [Les plans de numérotation.](what-are-dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="224f6-197">For more information, see [What are dial plans?](what-are-dial-plans.md).</span></span>


### <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="224f6-198">Location-Based routage pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="224f6-198">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="224f6-199">Dans certains pays et certaines régions, il n’est pas illégal de contourner l’opérateur PSTN afin de diminuer les coûts des appels longue distance.</span><span class="sxs-lookup"><span data-stu-id="224f6-199">In some countries and regions, it's illegal to bypass the PSTN carrier to decrease long-distance calling costs.</span></span> <span data-ttu-id="224f6-200">Location-Based (LBR) pour le routage direct vous permet de restreindre la dérivation contre les Teams en fonction de leur emplacement géographique.</span><span class="sxs-lookup"><span data-stu-id="224f6-200">Location-Based Routing (LBR) for Direct Routing enables you to restrict toll bypass for Teams users based on their geographic location.</span></span> <span data-ttu-id="224f6-201">Pour plus d’informations sur la façon de planifier et de configurer LBR, voir les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="224f6-201">For more information about how to plan and configure LBR, see the following articles:</span></span>

- [<span data-ttu-id="224f6-202">Planifier le routage géodépendant pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="224f6-202">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="224f6-203">Configurer les paramètres de réseau pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="224f6-203">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="224f6-204">Activer le routage géodépendant pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="224f6-204">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="224f6-205">Étude de cas Contoso : Location-Based routage</span><span class="sxs-lookup"><span data-stu-id="224f6-205">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="224f6-206">Décrit la façon dont Contoso, une entreprise multinationale fictive, a implémenté un Location-Based routage pour leur organisation.</span><span class="sxs-lookup"><span data-stu-id="224f6-206">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>


### <a name="emergency-calling"></a><span data-ttu-id="224f6-207">Appel d’urgence</span><span class="sxs-lookup"><span data-stu-id="224f6-207">Emergency calling</span></span>

<span data-ttu-id="224f6-208">La configuration des appels d’urgence diffère en fonction de l’option de connectivité PSTN.</span><span class="sxs-lookup"><span data-stu-id="224f6-208">How you configure emergency calling differs depending on your PSTN connectivity option.</span></span>

- <span data-ttu-id="224f6-209">Pour le plan d’appels, chaque utilisateur est automatiquement activé pour les appels d’urgence et une adresse d’urgence enregistrée doit être associée à son numéro de téléphone affecté.</span><span class="sxs-lookup"><span data-stu-id="224f6-209">For Calling Plan, each user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number.</span></span> <span data-ttu-id="224f6-210">Les appels d’urgence dynamiques (en fonction de l’emplacement Teams client) sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="224f6-210">Dynamic emergency calling (based on the location of the Teams client) is supported.</span></span>  

- <span data-ttu-id="224f6-211">Pour le routage direct, vous devez définir des stratégies d’appel d’urgence pour les utilisateurs à l’aide d’une stratégie de routage d’appel d’urgence Teams (TeamsEmergencyCallRoutingPolicy) pour définir les numéros d’urgence et leur destination de routage associée.</span><span class="sxs-lookup"><span data-stu-id="224f6-211">For Direct Routing, you must define emergency calling policies for users by using a Teams emergency call routing policy (TeamsEmergencyCallRoutingPolicy) to define emergency numbers and their associated routing destination.</span></span> <span data-ttu-id="224f6-212">Les emplacements d’urgence enregistrés ne sont pas pris en charge pour les utilisateurs du routage direct.</span><span class="sxs-lookup"><span data-stu-id="224f6-212">Registered emergency locations are not supported for Direct Routing users.</span></span> <span data-ttu-id="224f6-213">Pour les appels d’urgence dynamiques, une configuration supplémentaire est requise pour router les appels d’urgence et éventuellement pour la connectivité partenaire.</span><span class="sxs-lookup"><span data-stu-id="224f6-213">For dynamic emergency calling, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span>

- <span data-ttu-id="224f6-214">Pour l’Connecter opérateur, chaque utilisateur est automatiquement activé pour les appels d’urgence et une adresse d’urgence enregistrée doit être associée à son numéro de téléphone affecté, mais ne peut être définie que par le partenaire de l’opérateur.</span><span class="sxs-lookup"><span data-stu-id="224f6-214">For Operator Connect, each user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number but can only be set by the carrier partner.</span></span> <span data-ttu-id="224f6-215">Les appels d’urgence dynamiques (en fonction de l’emplacement Teams client) sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="224f6-215">Dynamic emergency calling (based on the location of the Teams client) is supported.</span></span>

<span data-ttu-id="224f6-216">Pour plus d’informations sur les concepts d’appel d’urgence et la terminologie, ainsi que sur la configuration des appels d’urgence et des appels d’urgence dynamiques, consultez les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="224f6-216">For more information about emergency calling concepts and terminology, and how to configure emergency calling and dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="224f6-217">Gestion des appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="224f6-217">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="224f6-218">Planifier et configurer un appel d’urgence dynamique</span><span class="sxs-lookup"><span data-stu-id="224f6-218">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="224f6-219">Gérer les stratégies d’appel d’urgence</span><span class="sxs-lookup"><span data-stu-id="224f6-219">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="224f6-220">Gérer les stratégies de routage d’appel d’urgence pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="224f6-220">Manage emergency call routing policies for Direct Routing</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="224f6-221">Étude de cas Contoso : appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="224f6-221">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="224f6-222">Décrit comment une entreprise multinationale fictive, Contoso, a implémenté des appels d’urgence pour leur organisation.</span><span class="sxs-lookup"><span data-stu-id="224f6-222">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>


### <a name="network-topology-for-voice-features"></a><span data-ttu-id="224f6-223">Topologie de réseau pour les fonctionnalités vocales</span><span class="sxs-lookup"><span data-stu-id="224f6-223">Network topology for voice features</span></span>

<span data-ttu-id="224f6-224">Si vous déployez des appels d’urgence dynamiques ou un Location-Based de routage direct, vous devez configurer les paramètres réseau pour les utiliser avec ces fonctionnalités dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="224f6-224">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="224f6-225">Pour découvrir comment configurer les paramètres réseau pour les régions réseau, les sites réseau, les sous-réseaux et les adresses IP de confiance, consultez les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="224f6-225">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="224f6-226">Paramètres réseau pour les fonctionnalités vocales cloud dans Microsoft Teams - Concepts et terminologie</span><span class="sxs-lookup"><span data-stu-id="224f6-226">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="224f6-227">Gérer votre topologie de réseau pour les fonctionnalités vocales cloud dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="224f6-227">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)



