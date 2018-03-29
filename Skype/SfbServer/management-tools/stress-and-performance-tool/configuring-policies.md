---
title: Configuration des stratégies pour le Skype pour Business Server 2015 Stress et l’outil performances
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configuration de la stratégie de Skype pour Business Server 2015 Stress et l’outil performances.
ms.openlocfilehash: 5bdeb4c65b3649e7d417550578e277e01e55fcc3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="fb12a-103">Configuration des stratégies pour le Skype pour Business Server 2015 Stress et l’outil performances</span><span class="sxs-lookup"><span data-stu-id="fb12a-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="fb12a-104">Configuration de la stratégie de Skype pour Business Server 2015 Stress et l’outil performances.</span><span class="sxs-lookup"><span data-stu-id="fb12a-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="fb12a-105">Il existe plusieurs stratégies et autres zones que vous pouvez configurer dans Skype pour 2015 de serveur d’entreprise, avant d’exécuter l’outil de performances et le Stress :</span><span class="sxs-lookup"><span data-stu-id="fb12a-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="fb12a-106">Stratégie d’archivage</span><span class="sxs-lookup"><span data-stu-id="fb12a-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="fb12a-107">Stratégie de conférence</span><span class="sxs-lookup"><span data-stu-id="fb12a-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="fb12a-108">Stratégie des contacts</span><span class="sxs-lookup"><span data-stu-id="fb12a-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="fb12a-109">Stratégie de fédération</span><span class="sxs-lookup"><span data-stu-id="fb12a-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="fb12a-110">Politique de contrôle d’Admission des appels</span><span class="sxs-lookup"><span data-stu-id="fb12a-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="fb12a-111">Règles de routage de voix</span><span class="sxs-lookup"><span data-stu-id="fb12a-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="fb12a-112">Application de surveillance du conférence</span><span class="sxs-lookup"><span data-stu-id="fb12a-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="fb12a-113">Service de serveur appel Park</span><span class="sxs-lookup"><span data-stu-id="fb12a-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="fb12a-114">Appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="fb12a-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="fb12a-115">Application de la configuration de groupe de réponse</span><span class="sxs-lookup"><span data-stu-id="fb12a-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="fb12a-116">Stratégie d’archivage</span><span class="sxs-lookup"><span data-stu-id="fb12a-116">Archiving policy</span></span>
<span data-ttu-id="fb12a-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="fb12a-117"></span></span>

<span data-ttu-id="fb12a-118">Si vous disposez d’un serveur d’archivage déployé dans votre Skype pour la topologie du serveur de l’entreprise, vous pouvez consulter le script ArchivingPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="fb12a-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="fb12a-119">Si vous avez besoin d’une assistance supplémentaire, consultez les applets de commande d’archivage et de conférence Web.</span><span class="sxs-lookup"><span data-stu-id="fb12a-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="fb12a-120">Stratégie de conférence</span><span class="sxs-lookup"><span data-stu-id="fb12a-120">Conferencing policy</span></span>
<span data-ttu-id="fb12a-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="fb12a-121"></span></span>

<span data-ttu-id="fb12a-122">Pour la conférence, nous avons le script MeetingPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="fb12a-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="fb12a-123">Si vous avez besoin d’une assistance supplémentaire, consultez les applets de commande de conférences sur le Web.</span><span class="sxs-lookup"><span data-stu-id="fb12a-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="fb12a-124">Stratégie des contacts</span><span class="sxs-lookup"><span data-stu-id="fb12a-124">Contacts policy</span></span>
<span data-ttu-id="fb12a-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="fb12a-125"></span></span>

<span data-ttu-id="fb12a-126">Script de ContactsPolicy.ps1 est l’exemple que vous devez passer en revue.</span><span class="sxs-lookup"><span data-stu-id="fb12a-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="fb12a-127">Si vous avez besoin plus de références vous aide aux applets de commande de messagerie instantanée et de présence.</span><span class="sxs-lookup"><span data-stu-id="fb12a-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="fb12a-128">Stratégie de fédération</span><span class="sxs-lookup"><span data-stu-id="fb12a-128">Federation policy</span></span>
<span data-ttu-id="fb12a-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="fb12a-129"></span></span>

<span data-ttu-id="fb12a-130">L’exemple de script pour la fédération est FederationPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="fb12a-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="fb12a-131">Les applets de commande à passer en revue, si vous avez besoin d’insight, sera de serveur de transport Edge, la fédération et l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="fb12a-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="fb12a-132">Politique de contrôle d’Admission des appels</span><span class="sxs-lookup"><span data-stu-id="fb12a-132">Call Admission Control policy</span></span>
<span data-ttu-id="fb12a-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="fb12a-133"></span></span>

<span data-ttu-id="fb12a-134">Vous pouvez faire référence à BandwidthPolicy.ps1 pour cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="fb12a-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="fb12a-135">Les applets de commande de contrôle d’Admission appel aura davantage d’informations ainsi.</span><span class="sxs-lookup"><span data-stu-id="fb12a-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="fb12a-136">Règles de routage de voix</span><span class="sxs-lookup"><span data-stu-id="fb12a-136">Voice Routing rules</span></span>
<span data-ttu-id="fb12a-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="fb12a-137"></span></span>

<span data-ttu-id="fb12a-138">Vous aurez besoin de l’exemple de script RoutingRules.ps1 pour le routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="fb12a-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="fb12a-139">Lorsque vous configurez ces règles, prenez note du contexte téléphonique (c'est-à-dire /Location profil ou /SimpleName) et les Codes de zone interne/externe, afin que vous pouvez les spécifier lors de la création d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fb12a-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="fb12a-140">Vous allez également besoin lors de la configuration de LyncPerfTool (spécifiquement pour RTPC-UC et les communications unifiées-PSTN).</span><span class="sxs-lookup"><span data-stu-id="fb12a-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="fb12a-141">Par exemple, le paramètre SimpleName dans l’appel à l’applet de commande **New-CsDialPlan** dans l’exemple RoutingRules.ps1 doit être utilisé pour la valeur de LocationProfile dans la figure suivante de UserProfileGenerator.exe :</span><span class="sxs-lookup"><span data-stu-id="fb12a-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Chargez l’outil de configuration Skype Entreprise, onglet Scénarios vocaux, paramètres avancés de conversation.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="fb12a-143">Pour plus d’informations, vous pouvez consulter les applets de commande Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="fb12a-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="fb12a-144">Application de surveillance du conférence</span><span class="sxs-lookup"><span data-stu-id="fb12a-144">Conference Attendant application</span></span>
<span data-ttu-id="fb12a-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="fb12a-145"></span></span>

<span data-ttu-id="fb12a-146">Tout d’abord, examinez le script ConferenceAutoAttendantConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="fb12a-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="fb12a-147">Vous allez, si vous le souhaitez, notez le numéro de téléphone de ConferencingAutoAttendant (1121111111 par défaut), afin que vous pouvez l’entrer dans l’outil de configuration de LyncPerfTool pour la génération de la configuration, comme indiqué ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="fb12a-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![Onglet Scénarios vocaux affichant le niveau de charge de la conférence et le numéro de téléphone.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="fb12a-149">Vous trouverez plus de détails de la conférence et les conférences à distance applets de commande.</span><span class="sxs-lookup"><span data-stu-id="fb12a-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="fb12a-150">Service de serveur appel Park</span><span class="sxs-lookup"><span data-stu-id="fb12a-150">Server Call Park service</span></span>
<span data-ttu-id="fb12a-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="fb12a-151"></span></span>

<span data-ttu-id="fb12a-152">En fait, il est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="fb12a-152">This is actually disabled by default.</span></span> <span data-ttu-id="fb12a-153">Vous pouvez consulter l’exemple de script CallParkConfiguration.ps1 si vous avez besoin effectuer ce test.</span><span class="sxs-lookup"><span data-stu-id="fb12a-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="fb12a-154">En outre, Découvrez les applets de commande d’appeler une Application de parc selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="fb12a-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="fb12a-155">Appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="fb12a-155">Emergency calls</span></span>
<span data-ttu-id="fb12a-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="fb12a-156"></span></span>

<span data-ttu-id="fb12a-157">Vous devez effectuer les étapes suivantes pour configurer le stress et le test de performance pour les appels d’urgence :</span><span class="sxs-lookup"><span data-stu-id="fb12a-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="fb12a-158">Configurer un itinéraire de voix pour les appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="fb12a-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="fb12a-159">Vous pouvez utiliser le script RoutingRules.ps1 et vérifiez sous le commentaire « **E911 itinéraire vers RTPC** » pour obtenir un exemple de la façon de configurer cet itinéraire de voix.</span><span class="sxs-lookup"><span data-stu-id="fb12a-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="fb12a-160">L’exemple de commande de RoutingRules.ps1 a un modèle de numéro qui inclut le numéro 119 plutôt que 911.</span><span class="sxs-lookup"><span data-stu-id="fb12a-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="fb12a-161">Vous devez éviter d’utiliser le 911 (ou votre numéro d’urgence local réel) afin d’éviter des appels accidentelles à vos opérateurs d’urgence locales pendant votre test de charge.</span><span class="sxs-lookup"><span data-stu-id="fb12a-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="fb12a-162">N’oubliez pas que cette configuration est uniquement à des fins de simulation !</span><span class="sxs-lookup"><span data-stu-id="fb12a-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="fb12a-163">Configurer les adresses en renseignant les valeurs dans l’onglet **Configuration du Service Info emplacement** dans la UserProvisioningTool, comme illustré dans la figure suivante :</span><span class="sxs-lookup"><span data-stu-id="fb12a-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![Outil d’affectation d’utilisateurs affichant le nombre d’adresses, de sous-réseaux, de commutateurs et de ports.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="fb12a-165">Lorsque vous avez saisi tous les éléments dans le UserProvisioningTool, cliquez sur le bouton de **Génération de fichiers Config de LIS** .</span><span class="sxs-lookup"><span data-stu-id="fb12a-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="fb12a-166">Désormais les fichiers CSV pour les ports, les sous-réseaux, les commutateurs et les points d’accès sans fil (WAP), ainsi que d’un fichier XML pour l’outil de Stress and Performance sera généré.</span><span class="sxs-lookup"><span data-stu-id="fb12a-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="fb12a-167">Vous pouvez utiliser les fichiers CSV des entrées lors de la configuration du service d’informations d’emplacement (LIS) avec le script LisConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="fb12a-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="fb12a-168">Pour ce faire, vous devez déplacer le fichier Locations0.xml dans le même dossier que le Stress et les performances, outil exécutable (LyncPerfTool.exe).</span><span class="sxs-lookup"><span data-stu-id="fb12a-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="fb12a-169">Cela vous permettra d’exécuter des scénarios de profil (plan de numérotation) emplacement.</span><span class="sxs-lookup"><span data-stu-id="fb12a-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="fb12a-170">Application de la configuration de groupe de réponse</span><span class="sxs-lookup"><span data-stu-id="fb12a-170">Configuring Response Group application</span></span>
<span data-ttu-id="fb12a-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="fb12a-171"></span></span>

<span data-ttu-id="fb12a-172">L’exemple de script est ResponseGroupConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="fb12a-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="fb12a-173">Il existe également des applets de commande groupe réponse application à consulter pour obtenir les détails de configuration.</span><span class="sxs-lookup"><span data-stu-id="fb12a-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="fb12a-174">Le diagramme suivant affiche certains détails de la configuration :</span><span class="sxs-lookup"><span data-stu-id="fb12a-174">The following diagram will show some of the configuration details:</span></span>
  
![Outil de configuration de groupe de réponse affichant les flux de travail existants pour les tests.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

