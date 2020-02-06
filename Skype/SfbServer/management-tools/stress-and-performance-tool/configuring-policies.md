---
title: Configuration des stratégies de l’outil de stress et de performance de Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Configuration de la stratégie de l’outil de stress et de performance de Skype entreprise Server 2015.
ms.openlocfilehash: bfdf0d9875a37f7f4a1f98aa24cd6fd5c3176a00
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816193"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="57f9f-103">Configuration des stratégies de l’outil de stress et de performance de Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="57f9f-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="57f9f-104">Configuration de la stratégie de l’outil de stress et de performance de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="57f9f-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="57f9f-105">Il existe plusieurs stratégies et autres modules que vous pouvez configurer dans Skype entreprise Server 2015, avant d’exécuter l’outil stress and performance :</span><span class="sxs-lookup"><span data-stu-id="57f9f-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="57f9f-106">Stratégie d’archivage</span><span class="sxs-lookup"><span data-stu-id="57f9f-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="57f9f-107">Stratégie de conférence</span><span class="sxs-lookup"><span data-stu-id="57f9f-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="57f9f-108">Politique de contacts</span><span class="sxs-lookup"><span data-stu-id="57f9f-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="57f9f-109">Stratégie de Fédération</span><span class="sxs-lookup"><span data-stu-id="57f9f-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="57f9f-110">Politique de contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="57f9f-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="57f9f-111">Règles de routage de la voix</span><span class="sxs-lookup"><span data-stu-id="57f9f-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="57f9f-112">Application de surveillance de la Conférence</span><span class="sxs-lookup"><span data-stu-id="57f9f-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="57f9f-113">Service de parc d’appels serveur</span><span class="sxs-lookup"><span data-stu-id="57f9f-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="57f9f-114">Appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="57f9f-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="57f9f-115">Configuration de l’application Response Group</span><span class="sxs-lookup"><span data-stu-id="57f9f-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="57f9f-116">Stratégie d’archivage</span><span class="sxs-lookup"><span data-stu-id="57f9f-116">Archiving policy</span></span>
<span data-ttu-id="57f9f-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="57f9f-117"><a name="ArchivingPolicy"> </a></span></span>

<span data-ttu-id="57f9f-118">Si vous disposez d’un serveur d’archivage déployé dans votre topologie Skype entreprise Server, vous pouvez examiner le script ArchivingPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="57f9f-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="57f9f-119">Si vous avez besoin d’aide, consultez les applets de contrôle d’archivage et de conférence Web.</span><span class="sxs-lookup"><span data-stu-id="57f9f-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="57f9f-120">Stratégie de conférence</span><span class="sxs-lookup"><span data-stu-id="57f9f-120">Conferencing policy</span></span>
<span data-ttu-id="57f9f-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="57f9f-121"><a name="ConferencingPolicy"> </a></span></span>

<span data-ttu-id="57f9f-122">Pour les conférences, nous avons le script MeetingPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="57f9f-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="57f9f-123">Si vous avez besoin d’aide, consultez les applets de contrôle de conférence Web.</span><span class="sxs-lookup"><span data-stu-id="57f9f-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="57f9f-124">Politique de contacts</span><span class="sxs-lookup"><span data-stu-id="57f9f-124">Contacts policy</span></span>
<span data-ttu-id="57f9f-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="57f9f-125"><a name="ContactsPolicy"> </a></span></span>

<span data-ttu-id="57f9f-126">Le script ContactsPolicy. ps1 sera l’exemple que vous devrez revoir.</span><span class="sxs-lookup"><span data-stu-id="57f9f-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="57f9f-127">Les applets de recherche et les applets de présence permettent de fournir des références supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="57f9f-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="57f9f-128">Stratégie de Fédération</span><span class="sxs-lookup"><span data-stu-id="57f9f-128">Federation policy</span></span>
<span data-ttu-id="57f9f-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="57f9f-129"><a name="FederationPolicy"> </a></span></span>

<span data-ttu-id="57f9f-130">L’exemple de script pour la Fédération est FederationPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="57f9f-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="57f9f-131">Les applets de contrôle, si vous avez besoin d’une analyse plus approfondie, seront serveur Edge, Fédération et accès externe.</span><span class="sxs-lookup"><span data-stu-id="57f9f-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="57f9f-132">Politique de contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="57f9f-132">Call Admission Control policy</span></span>
<span data-ttu-id="57f9f-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="57f9f-133"><a name="CACPolicy"> </a></span></span>

<span data-ttu-id="57f9f-134">Vous pouvez faire référence à BandwidthPolicy. ps1 pour cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="57f9f-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="57f9f-135">Les applets de commande de contrôle d’admission des appels comportent également des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="57f9f-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="57f9f-136">Règles de routage de la voix</span><span class="sxs-lookup"><span data-stu-id="57f9f-136">Voice Routing rules</span></span>
<span data-ttu-id="57f9f-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="57f9f-137"><a name="VoiceRoutingRules"> </a></span></span>

<span data-ttu-id="57f9f-138">Vous aurez besoin de l’exemple de script RoutingRules. ps1 pour le routage de la voix.</span><span class="sxs-lookup"><span data-stu-id="57f9f-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="57f9f-139">Lorsque vous configurez ces règles, prenez note du contexte du téléphone (c’est-à-dire le profil/location ou/SimpleName) et des codes de zone interne/externe, afin de pouvoir les spécifier lors de la création d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="57f9f-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="57f9f-140">Vous en aurez également besoin dans le cadre de la configuration de LyncPerfTool (en particulier pour PSTN-Cu et UC-RTC).</span><span class="sxs-lookup"><span data-stu-id="57f9f-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="57f9f-141">Par exemple, le paramètre SimpleName dans l’appel à l’applet de commande **New-CsDialPlan** dans l’exemple RoutingRules. ps1 doit être utilisé pour la valeur LocationProfile dans l’illustration suivante de UserProfileGenerator. exe :</span><span class="sxs-lookup"><span data-stu-id="57f9f-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Chargez l’outil de configuration Skype Entreprise, onglet Scénarios vocaux, paramètres avancés de conversation.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="57f9f-143">Pour plus d’informations, vous pouvez passer en revue les applets de contrôle vocales d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="57f9f-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="57f9f-144">Application de surveillance de la Conférence</span><span class="sxs-lookup"><span data-stu-id="57f9f-144">Conference Attendant application</span></span>
<span data-ttu-id="57f9f-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="57f9f-145"><a name="ConfAttendantApp"> </a></span></span>

<span data-ttu-id="57f9f-146">Commencez par revoir le script ConferenceAutoAttendantConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="57f9f-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="57f9f-147">Vous devez noter le numéro de téléphone ConferencingAutoAttendant (1121111111 par défaut) pour pouvoir l’entrer dans l’outil de configuration LyncPerfTool de la génération de configuration, comme ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="57f9f-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![Onglet Scénarios vocaux affichant le niveau de charge de la conférence et le numéro de téléphone.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="57f9f-149">Des informations supplémentaires sont disponibles dans les applets de connexion et les applets de service de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="57f9f-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="57f9f-150">Service de parc d’appels serveur</span><span class="sxs-lookup"><span data-stu-id="57f9f-150">Server Call Park service</span></span>
<span data-ttu-id="57f9f-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="57f9f-151"><a name="ServerCallParkServ"> </a></span></span>

<span data-ttu-id="57f9f-152">Ce paramètre est en fait désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="57f9f-152">This is actually disabled by default.</span></span> <span data-ttu-id="57f9f-153">Vous pouvez consulter l’exemple de script CallParkConfiguration. ps1 si vous devez le tester.</span><span class="sxs-lookup"><span data-stu-id="57f9f-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="57f9f-154">De plus, consultez les cmdlets de l’application de parc d’appels selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="57f9f-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="57f9f-155">Appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="57f9f-155">Emergency calls</span></span>
<span data-ttu-id="57f9f-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="57f9f-156"><a name="EmergencyCalls"> </a></span></span>

<span data-ttu-id="57f9f-157">Pour configurer les tests de stress et de performance des appels d’urgence, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="57f9f-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="57f9f-158">Configurez une gamme vocale pour les appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="57f9f-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="57f9f-159">Vous pouvez utiliser le script RoutingRules. ps1, puis vérifier sous le commentaire « **routez le E911 vers PSTN** » pour obtenir un exemple de configuration de cet itinéraire vocal.</span><span class="sxs-lookup"><span data-stu-id="57f9f-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="57f9f-160">La commande d’exemple dans RoutingRules. ps1 possède un modèle de nombre incluant le numéro 119 au lieu de 911.</span><span class="sxs-lookup"><span data-stu-id="57f9f-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="57f9f-161">Vous devez éviter d’utiliser 911 (ou votre numéro de secours local réel) pour éviter les appels accidentels vers vos opérateurs d’urgence locaux pendant votre test de charge.</span><span class="sxs-lookup"><span data-stu-id="57f9f-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="57f9f-162">N’oubliez pas que cette configuration est réservée aux fins de simulation.</span><span class="sxs-lookup"><span data-stu-id="57f9f-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="57f9f-163">Configurez les adresses en remplissant les valeurs sous l’onglet **configuration du service d’informations d’emplacement** dans le UserProvisioningTool, comme illustré dans la figure suivante :</span><span class="sxs-lookup"><span data-stu-id="57f9f-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![Outil d’affectation d’utilisateurs affichant le nombre d’adresses, de sous-réseaux, de commutateurs et de ports.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="57f9f-165">Lorsque vous avez entré tout le contenu dans le UserProvisioningTool, cliquez sur le bouton **générer les fichiers de configuration de lis** .</span><span class="sxs-lookup"><span data-stu-id="57f9f-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="57f9f-166">À présent, les fichiers CSV de ports, de sous-réseaux, de commutateurs et de points d’accès sans fil (WAP), ainsi qu’un fichier XML pour l’outil de stress et de performance sera généré.</span><span class="sxs-lookup"><span data-stu-id="57f9f-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="57f9f-167">Vous pouvez utiliser les fichiers CSV pour les entrées lors de la configuration du service d’information d’emplacement avec le script LisConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="57f9f-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="57f9f-168">Pour ce faire, vous devez déplacer le fichier Locations0. xml dans le même dossier que le fichier exécutable de l’outil de stress et de performance (LyncPerfTool. exe).</span><span class="sxs-lookup"><span data-stu-id="57f9f-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="57f9f-169">Cela vous permet d’exécuter des scénarios de profil d’emplacement (plan de numérotation).</span><span class="sxs-lookup"><span data-stu-id="57f9f-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="57f9f-170">Configuration de l’application Response Group</span><span class="sxs-lookup"><span data-stu-id="57f9f-170">Configuring Response Group application</span></span>
<span data-ttu-id="57f9f-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="57f9f-171"><a name="ConfigResponseGroupApp"> </a></span></span>

<span data-ttu-id="57f9f-172">L’exemple de script est ResponseGroupConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="57f9f-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="57f9f-173">Il existe également des cmdlets application de groupe de réponse à examiner pour plus d’informations sur la configuration.</span><span class="sxs-lookup"><span data-stu-id="57f9f-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="57f9f-174">Le diagramme suivant montre quelques détails de la configuration :</span><span class="sxs-lookup"><span data-stu-id="57f9f-174">The following diagram will show some of the configuration details:</span></span>
  
![Outil de configuration de groupe de réponse affichant les flux de travail existants pour les tests.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

