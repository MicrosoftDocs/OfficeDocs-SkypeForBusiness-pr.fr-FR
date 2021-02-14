---
title: Configuration des stratégies pour l’outil Stress and Performance de Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configuration de la stratégie pour l’outil Stress and Performance de Skype Entreprise Server 2015.
ms.openlocfilehash: bb049d5740d74e5ebeacd8a21d00e2644da61a7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815034"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="b5a05-103">Configuration des stratégies pour l’outil Stress and Performance de Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b5a05-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="b5a05-104">Configuration de la stratégie pour l’outil Stress and Performance de Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b5a05-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="b5a05-105">Vous pouvez configurer plusieurs stratégies et autres domaines dans Skype Entreprise Server 2015 avant d’utiliser l’outil Stress and Performance :</span><span class="sxs-lookup"><span data-stu-id="b5a05-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="b5a05-106">Stratégie d’archivage</span><span class="sxs-lookup"><span data-stu-id="b5a05-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="b5a05-107">Stratégie de conférence</span><span class="sxs-lookup"><span data-stu-id="b5a05-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="b5a05-108">Stratégie de contacts</span><span class="sxs-lookup"><span data-stu-id="b5a05-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="b5a05-109">Stratégie de fédération</span><span class="sxs-lookup"><span data-stu-id="b5a05-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="b5a05-110">Stratégie de contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="b5a05-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="b5a05-111">Règles de routage des voix</span><span class="sxs-lookup"><span data-stu-id="b5a05-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="b5a05-112">Application Conference Attendant</span><span class="sxs-lookup"><span data-stu-id="b5a05-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="b5a05-113">Service de parc d’appel serveur</span><span class="sxs-lookup"><span data-stu-id="b5a05-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="b5a05-114">Appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="b5a05-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="b5a05-115">Configuration de l’application Response Group</span><span class="sxs-lookup"><span data-stu-id="b5a05-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="b5a05-116">Stratégie d’archivage</span><span class="sxs-lookup"><span data-stu-id="b5a05-116">Archiving policy</span></span>
<span data-ttu-id="b5a05-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="b5a05-117"><a name="ArchivingPolicy"> </a></span></span>

<span data-ttu-id="b5a05-118">Si vous avez un serveur d’archivage déployé dans votre topologie Skype Entreprise Server, vous pouvez examiner ArchivingPolicy.ps1 script.</span><span class="sxs-lookup"><span data-stu-id="b5a05-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="b5a05-119">Si vous avez besoin d’une assistance supplémentaire, consultez les cmdlets d’archivage et de conférence Web.</span><span class="sxs-lookup"><span data-stu-id="b5a05-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="b5a05-120">Stratégie de conférence</span><span class="sxs-lookup"><span data-stu-id="b5a05-120">Conferencing policy</span></span>
<span data-ttu-id="b5a05-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="b5a05-121"><a name="ConferencingPolicy"> </a></span></span>

<span data-ttu-id="b5a05-122">Pour les conférences, nous avons le script MeetingPolicy.ps1 de conférence.</span><span class="sxs-lookup"><span data-stu-id="b5a05-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="b5a05-123">Si vous avez besoin d’une assistance supplémentaire, consultez les cmdlets de conférence web.</span><span class="sxs-lookup"><span data-stu-id="b5a05-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="b5a05-124">Stratégie de contacts</span><span class="sxs-lookup"><span data-stu-id="b5a05-124">Contacts policy</span></span>
<span data-ttu-id="b5a05-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="b5a05-125"><a name="ContactsPolicy"> </a></span></span>

<span data-ttu-id="b5a05-126">ContactsPolicy.ps1 script sera l’exemple que vous devrez examiner.</span><span class="sxs-lookup"><span data-stu-id="b5a05-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="b5a05-127">Les cmdlets de messagerie instantanée et de présence vous aideront si vous avez besoin de références supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="b5a05-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="b5a05-128">Stratégie de fédération</span><span class="sxs-lookup"><span data-stu-id="b5a05-128">Federation policy</span></span>
<span data-ttu-id="b5a05-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="b5a05-129"><a name="FederationPolicy"> </a></span></span>

<span data-ttu-id="b5a05-130">L’exemple de script pour la fédération est FederationPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="b5a05-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="b5a05-131">Les cmdlets à examiner, si vous avez besoin d’informations supplémentaires, seront le serveur Edge, la fédération et l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="b5a05-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="b5a05-132">Stratégie de contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="b5a05-132">Call Admission Control policy</span></span>
<span data-ttu-id="b5a05-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="b5a05-133"><a name="CACPolicy"> </a></span></span>

<span data-ttu-id="b5a05-134">Vous pouvez référencer BandwidthPolicy.ps1 pour cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="b5a05-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="b5a05-135">Les cmdlets du contrôle d’admission des appels auront également des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="b5a05-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="b5a05-136">Règles de routage des voix</span><span class="sxs-lookup"><span data-stu-id="b5a05-136">Voice Routing rules</span></span>
<span data-ttu-id="b5a05-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="b5a05-137"><a name="VoiceRoutingRules"> </a></span></span>

<span data-ttu-id="b5a05-138">Vous aurez besoin de l’exemple RoutingRules.ps1 script pour le routage des voix.</span><span class="sxs-lookup"><span data-stu-id="b5a05-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="b5a05-139">Lorsque vous configurez ces règles, prenez note du contexte téléphonique (c’est-à-dire, /Location Profile ou /SimpleName) et des codes de zone interne/externe, afin de pouvoir les spécifier lors de la création d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b5a05-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="b5a05-140">Vous en aurez également besoin lors de la configuration de LyncPerfTool (spécifiquement pour PSTN-UC et UC-PSTN).</span><span class="sxs-lookup"><span data-stu-id="b5a05-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="b5a05-141">Par exemple, le paramètre SimpleName dans l’appel à l’cmdlet **New-CsDialPlan** dans l’exemple RoutingRules.ps1 doit être utilisé pour la valeur LocationProfile dans la figure suivante de UserProfileGenerator.exe :</span><span class="sxs-lookup"><span data-stu-id="b5a05-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Outil de configuration de charge Skype Entreprise, onglet Scénarios vocaux, Paramètres avancés des conversations.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="b5a05-143">Pour plus d’informations, vous pouvez consulter les Voix Entreprise cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b5a05-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="b5a05-144">Application Conference Attendant</span><span class="sxs-lookup"><span data-stu-id="b5a05-144">Conference Attendant application</span></span>
<span data-ttu-id="b5a05-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="b5a05-145"><a name="ConfAttendantApp"> </a></span></span>

<span data-ttu-id="b5a05-146">Tout d’abord, examinez ConferenceAutoAttendantConfiguration.ps1 script.</span><span class="sxs-lookup"><span data-stu-id="b5a05-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="b5a05-147">Vous devez prendre note du numéro de téléphone ConferencingAutoAttendant (11211111111 par défaut), afin de pouvoir l’entrer dans l’outil de configuration LyncPerfTool pour la génération de configuration, comme ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="b5a05-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![Onglet Scénarios vocaux affichant le niveau de charge de conférence et le numéro de téléphone.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="b5a05-149">Vous trouverez plus d’informations dans les cmdlets conférence et conférences téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="b5a05-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="b5a05-150">Service de parc d’appel serveur</span><span class="sxs-lookup"><span data-stu-id="b5a05-150">Server Call Park service</span></span>
<span data-ttu-id="b5a05-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="b5a05-151"><a name="ServerCallParkServ"> </a></span></span>

<span data-ttu-id="b5a05-152">Cette option est en fait désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="b5a05-152">This is actually disabled by default.</span></span> <span data-ttu-id="b5a05-153">Vous pouvez consulter l'CallParkConfiguration.ps1 exemple de script si vous devez le tester.</span><span class="sxs-lookup"><span data-stu-id="b5a05-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="b5a05-154">En outre, consultez les cmdlets d’application de parcage d’appel si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="b5a05-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="b5a05-155">Appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="b5a05-155">Emergency calls</span></span>
<span data-ttu-id="b5a05-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="b5a05-156"><a name="EmergencyCalls"> </a></span></span>

<span data-ttu-id="b5a05-157">Vous devez effectuer les étapes suivantes pour configurer le test de contrainte et de performances pour les appels d’urgence :</span><span class="sxs-lookup"><span data-stu-id="b5a05-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="b5a05-158">Configurer un itinéraire de voix pour les appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="b5a05-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="b5a05-159">Vous pouvez utiliser le script RoutingRules.ps1 et vérifier sous le commentaire « **Router E911 vers PSTN** » pour obtenir un exemple de la façon de configurer cet itinéraire de voix.</span><span class="sxs-lookup"><span data-stu-id="b5a05-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="b5a05-160">L’exemple de commande RoutingRules.ps1 a un modèle de numéro qui inclut le numéro 119 au lieu de 911.</span><span class="sxs-lookup"><span data-stu-id="b5a05-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="b5a05-161">Vous devez éviter d’utiliser le 911 (ou votre numéro d’urgence local réel) pour éviter les appels accidentels à vos opérateurs d’urgence locaux lors de vos tests de charge.</span><span class="sxs-lookup"><span data-stu-id="b5a05-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="b5a05-162">N’oubliez pas que cette configuration est uniquement à des fins de simulation !</span><span class="sxs-lookup"><span data-stu-id="b5a05-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="b5a05-163">Configurez les adresses en remplissant les valeurs sous l’onglet Configuration du **service** d’informations d’emplacement dans UserProvisioningTool, comme illustré dans la figure suivante :</span><span class="sxs-lookup"><span data-stu-id="b5a05-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![Outil d’approvisionnement utilisateur affichant le nombre d’adresses, de sous-réseaux, de commutateurs et de ports.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="b5a05-165">Une fois que vous avez entré tous les fichiers dans UserProvisioningTool, cliquez sur le bouton Générer des fichiers de **config LIS.**</span><span class="sxs-lookup"><span data-stu-id="b5a05-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="b5a05-166">Désormais, des fichiers CSV pour les ports, sous-réseaux, commutateurs et points d’accès sans fil, ainsi qu’un fichier XML pour l’outil Stress and Performance seront générés.</span><span class="sxs-lookup"><span data-stu-id="b5a05-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="b5a05-167">Vous pouvez utiliser les fichiers CSV pour les entrées lors de la configuration du service LIS (Location Information Service) avec LisConfiguration.ps1 script.</span><span class="sxs-lookup"><span data-stu-id="b5a05-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="b5a05-168">Pour ce faire, vous devez déplacer le fichier Locations0.xml vers le même dossier que le fichier exécutable de l’outil Stress and Performance (LyncPerfTool.exe).</span><span class="sxs-lookup"><span data-stu-id="b5a05-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="b5a05-169">Cela vous permettra d’exécuter des scénarios de profil d’emplacement (plan de numérotation).</span><span class="sxs-lookup"><span data-stu-id="b5a05-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="b5a05-170">Configuration de l’application Response Group</span><span class="sxs-lookup"><span data-stu-id="b5a05-170">Configuring Response Group application</span></span>
<span data-ttu-id="b5a05-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="b5a05-171"><a name="ConfigResponseGroupApp"> </a></span></span>

<span data-ttu-id="b5a05-172">L’exemple de script est ResponseGroupConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="b5a05-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="b5a05-173">Il existe également des cmdlets d’application Response Group à examiner pour obtenir des détails supplémentaires sur la configuration.</span><span class="sxs-lookup"><span data-stu-id="b5a05-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="b5a05-174">Le diagramme suivant présente certains détails de configuration :</span><span class="sxs-lookup"><span data-stu-id="b5a05-174">The following diagram will show some of the configuration details:</span></span>
  
![Outil de config Response Group montrant les flux de travail existants à tester.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

