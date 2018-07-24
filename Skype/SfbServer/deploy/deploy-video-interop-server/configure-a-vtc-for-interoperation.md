---
title: Configurer un VTC pour l’interopérabilité avec Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Résumé : Configurez les périphériques VTC pour fonctionner avec Skype pour Business Server.'
ms.openlocfilehash: cc6b8d4fb48a0f43d646d204d399c575af503390
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21017906"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="e7981-103">Configurer un VTC pour l’interopérabilité avec Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="e7981-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="e7981-104">**Résumé :** Configurer les périphériques VTC pour fonctionner avec Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="e7981-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="e7981-105">Vous devez effectuer les procédures de personnalisation de configuration suivantes pour chaque VTC qui se connecteront à la Skype pour serveur vis-À-vis de l’entreprise via une jonction SIP et Cisco Unified Communications Manager (CallManager ou CUCM) passerelle vidéo.</span><span class="sxs-lookup"><span data-stu-id="e7981-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="e7981-106">Les paramètres décrits ici sont destinées uniquement des exemples de comment CUCM peut être configuré pour fonctionner avec une vis</span><span class="sxs-lookup"><span data-stu-id="e7981-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="e7981-107">Il est possible d’utiliser d’autres paramètres et/ou de prévoir d’autres utilisations de la fonctionnalité CUCM pour obtenir le même résultat.</span><span class="sxs-lookup"><span data-stu-id="e7981-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="e7981-108">Nous ne faisons aucune recommandation quant à la meilleure configuration possible pour un scénario en particulier.</span><span class="sxs-lookup"><span data-stu-id="e7981-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="e7981-109">Configurer un périphérique de vidéoconférence (VTC) enregistré avec le CUCM</span><span class="sxs-lookup"><span data-stu-id="e7981-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="e7981-110">Connectez-vous à l’appareil VTC Cisco et accédez à Configuration -\>Configuration système -\>mise en service.</span><span class="sxs-lookup"><span data-stu-id="e7981-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="e7981-111">Vérifiez les paramètres suivants (et corrigez-les si nécessaire) :</span><span class="sxs-lookup"><span data-stu-id="e7981-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="e7981-112">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="e7981-112">**Parameter**</span></span>|<span data-ttu-id="e7981-113">**Paramètre recommandé**</span><span class="sxs-lookup"><span data-stu-id="e7981-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e7981-114">Mode de mise en service</span><span class="sxs-lookup"><span data-stu-id="e7981-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="e7981-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="e7981-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="e7981-116">Adresse de l’ExternalManager</span><span class="sxs-lookup"><span data-stu-id="e7981-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="e7981-117">Nom de domaine complet du CUCM</span><span class="sxs-lookup"><span data-stu-id="e7981-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="e7981-118">Domaine ExternalManager</span><span class="sxs-lookup"><span data-stu-id="e7981-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="e7981-119">Domaine de CUCM</span><span class="sxs-lookup"><span data-stu-id="e7981-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="e7981-120">Accédez à Configuration -\>Configuration système -\>réseau.</span><span class="sxs-lookup"><span data-stu-id="e7981-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="e7981-121">Vérifiez les paramètres suivants (et corrigez-les si nécessaire) :</span><span class="sxs-lookup"><span data-stu-id="e7981-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="e7981-122">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="e7981-122">**Parameter**</span></span>|<span data-ttu-id="e7981-123">**Paramètre recommandé**</span><span class="sxs-lookup"><span data-stu-id="e7981-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e7981-124">Nom du domaine DNS</span><span class="sxs-lookup"><span data-stu-id="e7981-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="e7981-125">Nom du domaine du CUCM</span><span class="sxs-lookup"><span data-stu-id="e7981-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="e7981-126">Adresse du serveur DNS 1</span><span class="sxs-lookup"><span data-stu-id="e7981-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="e7981-127">Votre adresse de serveur DNS souhaitée</span><span class="sxs-lookup"><span data-stu-id="e7981-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="e7981-128">Accédez à Configuration -\>Configuration système -\>Services réseau.</span><span class="sxs-lookup"><span data-stu-id="e7981-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="e7981-129">Assurez-vous que le mode H.323 est désactivé et que le mode SIP est activé.</span><span class="sxs-lookup"><span data-stu-id="e7981-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="e7981-p103">Ces options sont activées automatiquement lorsque le point de terminaison est enregistré avec le CUCM. Vérifiez les paramètres suivants (et corrigez-les si nécessaire) :</span><span class="sxs-lookup"><span data-stu-id="e7981-p103">These options are set automatically when the endpoint is registered with CUCM. Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="e7981-132">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="e7981-132">**Parameter**</span></span>|<span data-ttu-id="e7981-133">**Paramètre recommandé**</span><span class="sxs-lookup"><span data-stu-id="e7981-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e7981-134">Mode H.323</span><span class="sxs-lookup"><span data-stu-id="e7981-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="e7981-135">Désactivé</span><span class="sxs-lookup"><span data-stu-id="e7981-135">Off</span></span> <br/> |
   |<span data-ttu-id="e7981-136">Mode HTTP</span><span class="sxs-lookup"><span data-stu-id="e7981-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="e7981-137">Activé</span><span class="sxs-lookup"><span data-stu-id="e7981-137">On</span></span> <br/> |
   | <span data-ttu-id="e7981-138">Mode SIP</span><span class="sxs-lookup"><span data-stu-id="e7981-138">SIP Mode</span></span> <br/> | <span data-ttu-id="e7981-139">Activé</span><span class="sxs-lookup"><span data-stu-id="e7981-139">On</span></span> <br/> |
   |<span data-ttu-id="e7981-140">Mode Telnet</span><span class="sxs-lookup"><span data-stu-id="e7981-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="e7981-141">Activé</span><span class="sxs-lookup"><span data-stu-id="e7981-141">On</span></span> <br/> |
   |<span data-ttu-id="e7981-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="e7981-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="e7981-143">Activé</span><span class="sxs-lookup"><span data-stu-id="e7981-143">On</span></span> <br/> |
   |<span data-ttu-id="e7981-144">Mode XMLAPI</span><span class="sxs-lookup"><span data-stu-id="e7981-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="e7981-145">Activé</span><span class="sxs-lookup"><span data-stu-id="e7981-145">On</span></span> <br/> |
   
7. <span data-ttu-id="e7981-146">Accédez à Configuration -\>Configuration système -\>SIP.</span><span class="sxs-lookup"><span data-stu-id="e7981-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="e7981-147">Vérifiez les paramètres suivants (et corrigez-les si nécessaire) :</span><span class="sxs-lookup"><span data-stu-id="e7981-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="e7981-148">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="e7981-148">**Parameter**</span></span>|<span data-ttu-id="e7981-149">**Paramètre recommandé**</span><span class="sxs-lookup"><span data-stu-id="e7981-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e7981-150">Profile 1 - DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="e7981-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="e7981-151">TCP</span><span class="sxs-lookup"><span data-stu-id="e7981-151">TCP</span></span> <br/> |
   |<span data-ttu-id="e7981-152">Profile 1 - Outbound</span><span class="sxs-lookup"><span data-stu-id="e7981-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="e7981-153">Désactivé</span><span class="sxs-lookup"><span data-stu-id="e7981-153">Off</span></span> <br/> |
   |<span data-ttu-id="e7981-154">Profil 1 - TlsVerify</span><span class="sxs-lookup"><span data-stu-id="e7981-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="e7981-155">Activé</span><span class="sxs-lookup"><span data-stu-id="e7981-155">On</span></span> <br/> |
   |<span data-ttu-id="e7981-156">Profile 1 - Type</span><span class="sxs-lookup"><span data-stu-id="e7981-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="e7981-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="e7981-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="e7981-158">Profile 1 - URI</span><span class="sxs-lookup"><span data-stu-id="e7981-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="e7981-159">Automatiquement attribué à l’enregistrement du CUCM</span><span class="sxs-lookup"><span data-stu-id="e7981-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="e7981-160">Proxy 1 - Adresse</span><span class="sxs-lookup"><span data-stu-id="e7981-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="e7981-161">Le nom de l’hôte du CUCM</span><span class="sxs-lookup"><span data-stu-id="e7981-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="e7981-p104">Le périphérique de vidéoconférence est désormais configuré pour l’interopérabilité. Avant d’utiliser le service, il vous reste certaines étapes à effectuer au niveau du CUCM.</span><span class="sxs-lookup"><span data-stu-id="e7981-p104">The VTC is now configured for interoperation. Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="e7981-164">Configurer les périphériques de vidéoconférence sur le CUCM</span><span class="sxs-lookup"><span data-stu-id="e7981-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="e7981-165">Connectez-vous à CUCM et accédez à Cisco Unified CM Administration -\>périphérique -\>téléphone -\>rechercher.</span><span class="sxs-lookup"><span data-stu-id="e7981-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="e7981-p105">Sélectionnez le périphérique de vidéoconférence (VTC) à configurer. Vérifiez les paramètres suivants sur l’écran Configuration du téléphone et corrigez-les si nécessaire. Une fois ces paramètres modifiés ou vérifiés, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7981-p105">Select the VTC device to be configured. Verify the following settings on the Phone Configuration screen, correcting as needed. Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="e7981-169">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="e7981-169">**Parameter**</span></span>|<span data-ttu-id="e7981-170">**Paramètre recommandé**</span><span class="sxs-lookup"><span data-stu-id="e7981-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e7981-171">Informations sur l’appareil - exemple de bouton de téléphone</span><span class="sxs-lookup"><span data-stu-id="e7981-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="e7981-172">C40 de TÉLÉPRÉSENCE Codec Cisco standard</span><span class="sxs-lookup"><span data-stu-id="e7981-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="e7981-173">Informations sur l’appareil - profil commun de téléphone</span><span class="sxs-lookup"><span data-stu-id="e7981-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="e7981-174">Profil commun de téléphone standard</span><span class="sxs-lookup"><span data-stu-id="e7981-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="e7981-175">Informations sur l’appareil - espace de recherche</span><span class="sxs-lookup"><span data-stu-id="e7981-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="e7981-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e7981-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e7981-177">Informations sur l’appareil - espace de recherche AAR</span><span class="sxs-lookup"><span data-stu-id="e7981-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="e7981-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e7981-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e7981-179">Informations sur l’appareil - liste des groupes de ressources médias</span><span class="sxs-lookup"><span data-stu-id="e7981-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="e7981-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e7981-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e7981-181">Informations spécifiques de protocole - profil de sécurité de l’appareil</span><span class="sxs-lookup"><span data-stu-id="e7981-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="e7981-182">Cisco TÉLÉPRÉSENCE Codec C40</span><span class="sxs-lookup"><span data-stu-id="e7981-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="e7981-183">Informations spécifiques de protocole - espace de recherche du réacheminement</span><span class="sxs-lookup"><span data-stu-id="e7981-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="e7981-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e7981-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e7981-185">Des informations spécifiques de protocole - s’abonner appelant espace de recherche</span><span class="sxs-lookup"><span data-stu-id="e7981-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="e7981-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e7981-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e7981-187">Informations spécifiques sur le protocole - profil SIP</span><span class="sxs-lookup"><span data-stu-id="e7981-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="e7981-188">Profil SIP standard pour point de terminaison Telepresence</span><span class="sxs-lookup"><span data-stu-id="e7981-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="e7981-189">Une fois la configuration de vidéoconférence enregistrée, accédez à l’écran de configuration de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e7981-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="e7981-190">Dans la partie supérieure de l’écran, dans le groupe Association, cliquez sur l’association pour l’interopérabilité vidéo.</span><span class="sxs-lookup"><span data-stu-id="e7981-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="e7981-191">Vous accédez à l’écran Configuration des numéros du répertoire.</span><span class="sxs-lookup"><span data-stu-id="e7981-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="e7981-192">Vérifiez les paramètres suivants (et corrigez-les si nécessaire) :</span><span class="sxs-lookup"><span data-stu-id="e7981-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="e7981-193">Effectuez les changements dans les informations de numéros du répertoire et dans les paramètres de numéros du répertoire.</span><span class="sxs-lookup"><span data-stu-id="e7981-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="e7981-194">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="e7981-194">**Parameter**</span></span>|<span data-ttu-id="e7981-195">**Paramètre recommandé**</span><span class="sxs-lookup"><span data-stu-id="e7981-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="e7981-196">Informations des numéros du répertoire - cloisonnement de l’itinéraire</span><span class="sxs-lookup"><span data-stu-id="e7981-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="e7981-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="e7981-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="e7981-198">Paramètres des numéros du répertoire - espace de recherche</span><span class="sxs-lookup"><span data-stu-id="e7981-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="e7981-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e7981-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e7981-200">Paramètres de niveau d’accès confidentiel et d’autres parties MLPP - espace de recherche MLPP</span><span class="sxs-lookup"><span data-stu-id="e7981-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="e7981-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e7981-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e7981-202">Ligne 1 sur le dispositif - affichage (ID de l’appelant)</span><span class="sxs-lookup"><span data-stu-id="e7981-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="e7981-203">Comme souhaité</span><span class="sxs-lookup"><span data-stu-id="e7981-203">As desired</span></span> <br/> |
   |<span data-ttu-id="e7981-204">Ligne 1 sur le dispositif - affichage ASCII (ID de l’appelant)</span><span class="sxs-lookup"><span data-stu-id="e7981-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="e7981-205">Comme souhaité</span><span class="sxs-lookup"><span data-stu-id="e7981-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="e7981-206">Lorsque vous avez terminé, remontez en haut de l’écran et sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7981-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="e7981-p107">La configuration est désormais terminée pour ce périphérique de vidéoconférence. Reproduisez ces étapes pour les autres périphériques de vidéoconférence dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="e7981-p107">Configuration is now complete for this VTC device. You will need to repeat this process for other VTC devices in your enterprise.</span></span>

