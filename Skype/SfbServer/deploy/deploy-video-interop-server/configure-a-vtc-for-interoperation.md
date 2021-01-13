---
title: Configurer un VTC pour l’interopération avec Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Résumé : Configurez les périphériques VTC pour qu’ils fonctionnent avec Skype Entreprise Server.'
ms.openlocfilehash: 7697fd9f33a4fece4871b056a05264ece888d357
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802074"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="8b8b6-103">Configurer un VTC pour l’interopération avec Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8b8b6-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="8b8b6-104">**Résumé :** Configurez les périphériques VTC pour qu’ils fonctionnent avec Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="8b8b6-105">Vous devez effectuer les procédures de personnalisation de configuration suivantes pour chaque VTC qui se connectera au serveur VIS Skype Entreprise via une connexion SIP et une passerelle vidéo Cisco Unified Communications Manager (CallManager, ou CUCM).</span><span class="sxs-lookup"><span data-stu-id="8b8b6-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="8b8b6-106">Les paramètres décrits ici ne sont destinés qu’à des exemples de la façon dont CUCM peut être configuré pour fonctionner avec un VIS.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="8b8b6-107">D’autres paramètres et/ou utilisations d’autres fonctionnalités CUCM peuvent également être utilisés pour obtenir le même résultat.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="8b8b6-108">Aucune recommandation n’est implicite quant à la configuration optimale pour un scénario particulier.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="8b8b6-109">Configurer un VTC enregistré avec CUCM</span><span class="sxs-lookup"><span data-stu-id="8b8b6-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="8b8b6-110">Connectez-vous à l’appareil Cisco VTC et accédez à Configuration - Configuration du système \> - \> Approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="8b8b6-111">Vérifiez les paramètres suivants, en corrigeant selon vos besoins :</span><span class="sxs-lookup"><span data-stu-id="8b8b6-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="8b8b6-112">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="8b8b6-112">**Parameter**</span></span>|<span data-ttu-id="8b8b6-113">**Valeur recommandée**</span><span class="sxs-lookup"><span data-stu-id="8b8b6-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="8b8b6-114">Mode d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="8b8b6-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="8b8b6-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="8b8b6-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="8b8b6-116">Adresse externalmanager</span><span class="sxs-lookup"><span data-stu-id="8b8b6-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="8b8b6-117">FQDN de CUCM</span><span class="sxs-lookup"><span data-stu-id="8b8b6-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="8b8b6-118">Domaine ExternalManager</span><span class="sxs-lookup"><span data-stu-id="8b8b6-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="8b8b6-119">Domaine CUCM</span><span class="sxs-lookup"><span data-stu-id="8b8b6-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="8b8b6-120">Accédez à Configuration - \> Configuration du système - \> Réseau.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="8b8b6-121">Vérifiez les paramètres suivants, en corrigeant selon vos besoins :</span><span class="sxs-lookup"><span data-stu-id="8b8b6-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="8b8b6-122">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="8b8b6-122">**Parameter**</span></span>|<span data-ttu-id="8b8b6-123">**Valeur recommandée**</span><span class="sxs-lookup"><span data-stu-id="8b8b6-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="8b8b6-124">Nom de domaine DNS</span><span class="sxs-lookup"><span data-stu-id="8b8b6-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="8b8b6-125">Nom de domaine CUCM</span><span class="sxs-lookup"><span data-stu-id="8b8b6-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="8b8b6-126">Adresse du serveur DNS 1</span><span class="sxs-lookup"><span data-stu-id="8b8b6-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="8b8b6-127">votre adresse de serveur DNS souhaitée</span><span class="sxs-lookup"><span data-stu-id="8b8b6-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="8b8b6-128">Accédez à Configuration - \> Configuration du système - Services \> réseau.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="8b8b6-129">Assurez-vous que le mode H.323 est désactivé et que le mode SIP est allumé.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="8b8b6-130">Ces options sont définies automatiquement lorsque le point de terminaison est enregistré avec CUCM.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-130">These options are set automatically when the endpoint is registered with CUCM.</span></span> <span data-ttu-id="8b8b6-131">Vérifiez les paramètres suivants, en corrigeant selon vos besoins :</span><span class="sxs-lookup"><span data-stu-id="8b8b6-131">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="8b8b6-132">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="8b8b6-132">**Parameter**</span></span>|<span data-ttu-id="8b8b6-133">**Valeur recommandée**</span><span class="sxs-lookup"><span data-stu-id="8b8b6-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="8b8b6-134">H.323 Mode</span><span class="sxs-lookup"><span data-stu-id="8b8b6-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="8b8b6-135">Désactivé</span><span class="sxs-lookup"><span data-stu-id="8b8b6-135">Off</span></span> <br/> |
   |<span data-ttu-id="8b8b6-136">HTTP Mode</span><span class="sxs-lookup"><span data-stu-id="8b8b6-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="8b8b6-137">Activé</span><span class="sxs-lookup"><span data-stu-id="8b8b6-137">On</span></span> <br/> |
   | <span data-ttu-id="8b8b6-138">SIP Mode</span><span class="sxs-lookup"><span data-stu-id="8b8b6-138">SIP Mode</span></span> <br/> | <span data-ttu-id="8b8b6-139">Activé</span><span class="sxs-lookup"><span data-stu-id="8b8b6-139">On</span></span> <br/> |
   |<span data-ttu-id="8b8b6-140">Telnet Mode</span><span class="sxs-lookup"><span data-stu-id="8b8b6-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="8b8b6-141">Activé</span><span class="sxs-lookup"><span data-stu-id="8b8b6-141">On</span></span> <br/> |
   |<span data-ttu-id="8b8b6-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="8b8b6-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="8b8b6-143">Activé</span><span class="sxs-lookup"><span data-stu-id="8b8b6-143">On</span></span> <br/> |
   |<span data-ttu-id="8b8b6-144">XMLAPI Mode</span><span class="sxs-lookup"><span data-stu-id="8b8b6-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="8b8b6-145">Activé</span><span class="sxs-lookup"><span data-stu-id="8b8b6-145">On</span></span> <br/> |
   
7. <span data-ttu-id="8b8b6-146">Accédez à Configuration - \> Configuration système \> - SIP.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="8b8b6-147">Vérifiez les paramètres suivants, en corrigeant selon vos besoins :</span><span class="sxs-lookup"><span data-stu-id="8b8b6-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="8b8b6-148">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="8b8b6-148">**Parameter**</span></span>|<span data-ttu-id="8b8b6-149">**Valeur recommandée**</span><span class="sxs-lookup"><span data-stu-id="8b8b6-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="8b8b6-150">Profil 1 - DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="8b8b6-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="8b8b6-151">TCP</span><span class="sxs-lookup"><span data-stu-id="8b8b6-151">TCP</span></span> <br/> |
   |<span data-ttu-id="8b8b6-152">Profil 1 - Sortant</span><span class="sxs-lookup"><span data-stu-id="8b8b6-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="8b8b6-153">Désactivé</span><span class="sxs-lookup"><span data-stu-id="8b8b6-153">Off</span></span> <br/> |
   |<span data-ttu-id="8b8b6-154">Profil 1 - TlsVerify</span><span class="sxs-lookup"><span data-stu-id="8b8b6-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="8b8b6-155">Activé</span><span class="sxs-lookup"><span data-stu-id="8b8b6-155">On</span></span> <br/> |
   |<span data-ttu-id="8b8b6-156">Profil 1 - Type</span><span class="sxs-lookup"><span data-stu-id="8b8b6-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="8b8b6-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="8b8b6-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="8b8b6-158">Profil 1 - URI</span><span class="sxs-lookup"><span data-stu-id="8b8b6-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="8b8b6-159">Affecté automatiquement lors de l’inscription CUCM</span><span class="sxs-lookup"><span data-stu-id="8b8b6-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="8b8b6-160">Proxy 1 - Adresse</span><span class="sxs-lookup"><span data-stu-id="8b8b6-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="8b8b6-161">Nom d’hôte du CUCM</span><span class="sxs-lookup"><span data-stu-id="8b8b6-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="8b8b6-162">Le VTC est maintenant configuré pour l’interopération.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-162">The VTC is now configured for interoperation.</span></span> <span data-ttu-id="8b8b6-163">Avant que le service puisse commencer, il existe des étapes finales à effectuer côté CUCM.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-163">Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="8b8b6-164">Configurer des périphériques VTC sur CUCM</span><span class="sxs-lookup"><span data-stu-id="8b8b6-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="8b8b6-165">Connectez-vous au CUCM et accédez à Administration CM unifiée Cisco \> - Appareil - Téléphone - \> \> Rechercher.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="8b8b6-166">Sélectionnez l’appareil VTC à configurer.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-166">Select the VTC device to be configured.</span></span> <span data-ttu-id="8b8b6-167">Vérifiez les paramètres suivants sur l’écran Configuration du téléphone, en corrigeant selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-167">Verify the following settings on the Phone Configuration screen, correcting as needed.</span></span> <span data-ttu-id="8b8b6-168">Une fois ces paramètres modifiés ou vérifiés, cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="8b8b6-168">Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="8b8b6-169">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="8b8b6-169">**Parameter**</span></span>|<span data-ttu-id="8b8b6-170">**Valeur recommandée**</span><span class="sxs-lookup"><span data-stu-id="8b8b6-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="8b8b6-171">Informations sur l’appareil - Modèle de bouton de téléphone</span><span class="sxs-lookup"><span data-stu-id="8b8b6-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="8b8b6-172">Standard Cisco Telepresence Codec C40</span><span class="sxs-lookup"><span data-stu-id="8b8b6-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="8b8b6-173">Informations sur l’appareil - Profil téléphonique courant</span><span class="sxs-lookup"><span data-stu-id="8b8b6-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="8b8b6-174">Profil de téléphone commun standard</span><span class="sxs-lookup"><span data-stu-id="8b8b6-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="8b8b6-175">Informations sur l’appareil : espace de recherche d’appel</span><span class="sxs-lookup"><span data-stu-id="8b8b6-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="8b8b6-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="8b8b6-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="8b8b6-177">Informations sur l’appareil : espace de recherche d’appel AAR</span><span class="sxs-lookup"><span data-stu-id="8b8b6-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="8b8b6-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="8b8b6-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="8b8b6-179">Informations sur l’appareil - Liste des groupes de ressources multimédias</span><span class="sxs-lookup"><span data-stu-id="8b8b6-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="8b8b6-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="8b8b6-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="8b8b6-181">Informations spécifiques au protocole : profil de sécurité de l’appareil</span><span class="sxs-lookup"><span data-stu-id="8b8b6-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="8b8b6-182">Cisco Telepresence Codec C40</span><span class="sxs-lookup"><span data-stu-id="8b8b6-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="8b8b6-183">Informations spécifiques au protocole : réroutage de l’espace de recherche d’appel</span><span class="sxs-lookup"><span data-stu-id="8b8b6-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="8b8b6-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="8b8b6-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="8b8b6-185">Informations spécifiques au protocole : espace de recherche d’appel SUBSCRIBE</span><span class="sxs-lookup"><span data-stu-id="8b8b6-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="8b8b6-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="8b8b6-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="8b8b6-187">Informations spécifiques au protocole - Profil SIP</span><span class="sxs-lookup"><span data-stu-id="8b8b6-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="8b8b6-188">Profil SIP standard pour le point de terminaison de téléprésence</span><span class="sxs-lookup"><span data-stu-id="8b8b6-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="8b8b6-189">Une fois la configuration VTC enregistrée, re-accédez à l’écran Configuration du téléphone de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="8b8b6-190">En haut de l’écran du groupe Association, cliquez sur l’association pour l’interop vidéo.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="8b8b6-191">L’écran Configuration du numéro d’annuaire s’affiche.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="8b8b6-192">Vérifiez les paramètres suivants, en corrigeant selon vos besoins :</span><span class="sxs-lookup"><span data-stu-id="8b8b6-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="8b8b6-193">A effectuer les modifications appropriées comme indiqué aux informations de numéro de répertoire et aux paramètres de numéro de répertoire.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="8b8b6-194">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="8b8b6-194">**Parameter**</span></span>|<span data-ttu-id="8b8b6-195">**Valeur recommandée**</span><span class="sxs-lookup"><span data-stu-id="8b8b6-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="8b8b6-196">Informations sur le numéro de répertoire - Partition de l’itinéraire</span><span class="sxs-lookup"><span data-stu-id="8b8b6-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="8b8b6-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="8b8b6-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="8b8b6-198">Paramètres du numéro d’annuaire - Espace de recherche d’appel</span><span class="sxs-lookup"><span data-stu-id="8b8b6-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="8b8b6-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="8b8b6-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="8b8b6-200">Paramètres de niveau d’accès confidentiel et de partie alternative MLPP - Espace de recherche d’appel MLPP</span><span class="sxs-lookup"><span data-stu-id="8b8b6-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="8b8b6-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="8b8b6-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="8b8b6-202">Ligne 1 sur l’appareil - Affichage (ID de l’appelant)</span><span class="sxs-lookup"><span data-stu-id="8b8b6-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="8b8b6-203">Comme vous le souhaitez</span><span class="sxs-lookup"><span data-stu-id="8b8b6-203">As desired</span></span> <br/> |
   |<span data-ttu-id="8b8b6-204">Ligne 1 sur l’appareil - Affichage ASCII (ID de l’appelant)</span><span class="sxs-lookup"><span data-stu-id="8b8b6-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="8b8b6-205">Comme vous le souhaitez</span><span class="sxs-lookup"><span data-stu-id="8b8b6-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="8b8b6-206">Lorsque vous avez terminé, faites défiler vers le haut de l’écran et appuyez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="8b8b6-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="8b8b6-207">La configuration est maintenant terminée pour cet appareil VTC.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-207">Configuration is now complete for this VTC device.</span></span> <span data-ttu-id="8b8b6-208">Vous devrez répéter ce processus pour les autres périphériques VTC de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="8b8b6-208">You will need to repeat this process for other VTC devices in your enterprise.</span></span>

