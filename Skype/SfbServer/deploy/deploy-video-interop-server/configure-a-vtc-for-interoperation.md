---
title: Configuration d’un système de vidéoconférence (VTC) pour l’interopération avec Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Résumé : Configurer les périphériques VTC pour fonctionner avec Skype pour Business Server 2015.'
ms.openlocfilehash: a88f34866a2a2147be0f30488e961552c6f19350
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server-2015"></a><span data-ttu-id="ecda0-103">Configuration d’un système de vidéoconférence (VTC) pour l’interopération avec Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="ecda0-103">Configure a VTC for Interoperation with Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ecda0-104">**Résumé :** Configurer les périphériques VTC pour fonctionner avec Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ecda0-104">**Summary:** Configure the VTC devices to work with Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ecda0-105">Vous devrez suivre les procédures de personnalisation de la configuration suivantes pour chaque périphérique de vidéoconférence (VTC) qui sera connecté au serveur VIS Skype Entreprise via une jonction SIP et une passerelle vidéo CUCM (Cisco Unified Communications Manager).</span><span class="sxs-lookup"><span data-stu-id="ecda0-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and CUCM video gateway.</span></span>
  
<span data-ttu-id="ecda0-106">Les paramètres décrits ici constituent uniquement des exemples de la CUCM peut être configuré pour fonctionner avec une vis</span><span class="sxs-lookup"><span data-stu-id="ecda0-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="ecda0-107">Il est possible d’utiliser d’autres paramètres et/ou de prévoir d’autres utilisations de la fonctionnalité CUCM pour obtenir le même résultat.</span><span class="sxs-lookup"><span data-stu-id="ecda0-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="ecda0-108">Nous ne faisons aucune recommandation quant à la meilleure configuration possible pour un scénario en particulier.</span><span class="sxs-lookup"><span data-stu-id="ecda0-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="ecda0-109">Configurer un périphérique de vidéoconférence (VTC) enregistré avec le CUCM</span><span class="sxs-lookup"><span data-stu-id="ecda0-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="ecda0-110">Se connecter au périphérique Cisco VTC et accédez à Configuration -\>Configuration du système -\>le provisionnement.</span><span class="sxs-lookup"><span data-stu-id="ecda0-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="ecda0-111">Vérifiez les paramètres suivants (et corrigez-les si nécessaire) :</span><span class="sxs-lookup"><span data-stu-id="ecda0-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="ecda0-112">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="ecda0-112">**Parameter**</span></span>|<span data-ttu-id="ecda0-113">**Paramètre recommandé**</span><span class="sxs-lookup"><span data-stu-id="ecda0-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="ecda0-114">Mode de mise en service</span><span class="sxs-lookup"><span data-stu-id="ecda0-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="ecda0-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="ecda0-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="ecda0-116">Adresse de l’ExternalManager</span><span class="sxs-lookup"><span data-stu-id="ecda0-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="ecda0-117">Nom de domaine complet du CUCM</span><span class="sxs-lookup"><span data-stu-id="ecda0-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="ecda0-118">Domaine de ExternalManager</span><span class="sxs-lookup"><span data-stu-id="ecda0-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="ecda0-119">Domaine du CUCM</span><span class="sxs-lookup"><span data-stu-id="ecda0-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="ecda0-120">Naviguez jusqu'à Configuration -\>Configuration du système -\>réseau.</span><span class="sxs-lookup"><span data-stu-id="ecda0-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="ecda0-121">Vérifiez les paramètres suivants (et corrigez-les si nécessaire) :</span><span class="sxs-lookup"><span data-stu-id="ecda0-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="ecda0-122">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="ecda0-122">**Parameter**</span></span>|<span data-ttu-id="ecda0-123">**Paramètre recommandé**</span><span class="sxs-lookup"><span data-stu-id="ecda0-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="ecda0-124">Nom du domaine DNS</span><span class="sxs-lookup"><span data-stu-id="ecda0-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="ecda0-125">Nom du domaine du CUCM</span><span class="sxs-lookup"><span data-stu-id="ecda0-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="ecda0-126">Adresse du serveur DNS 1</span><span class="sxs-lookup"><span data-stu-id="ecda0-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="ecda0-127">Votre adresse de serveur DNS souhaitée</span><span class="sxs-lookup"><span data-stu-id="ecda0-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="ecda0-128">Naviguez jusqu'à Configuration -\>Configuration du système -\>des Services réseau.</span><span class="sxs-lookup"><span data-stu-id="ecda0-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="ecda0-129">Assurez-vous que le mode H.323 est désactivé et que le mode SIP est activé.</span><span class="sxs-lookup"><span data-stu-id="ecda0-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="ecda0-p103">Ces options sont activées automatiquement lorsque le point de terminaison est enregistré avec le CUCM. Vérifiez les paramètres suivants (et corrigez-les si nécessaire) :</span><span class="sxs-lookup"><span data-stu-id="ecda0-p103">These options are set automatically when the endpoint is registered with CUCM. Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="ecda0-132">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="ecda0-132">**Parameter**</span></span>|<span data-ttu-id="ecda0-133">**Paramètre recommandé**</span><span class="sxs-lookup"><span data-stu-id="ecda0-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="ecda0-134">Mode H.323</span><span class="sxs-lookup"><span data-stu-id="ecda0-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="ecda0-135">Désactivé</span><span class="sxs-lookup"><span data-stu-id="ecda0-135">Off</span></span> <br/> |
   |<span data-ttu-id="ecda0-136">Mode HTTP</span><span class="sxs-lookup"><span data-stu-id="ecda0-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="ecda0-137">Activé</span><span class="sxs-lookup"><span data-stu-id="ecda0-137">On</span></span> <br/> |
   | <span data-ttu-id="ecda0-138">Mode SIP</span><span class="sxs-lookup"><span data-stu-id="ecda0-138">SIP Mode</span></span> <br/> | <span data-ttu-id="ecda0-139">Activé</span><span class="sxs-lookup"><span data-stu-id="ecda0-139">On</span></span> <br/> |
   |<span data-ttu-id="ecda0-140">Mode Telnet</span><span class="sxs-lookup"><span data-stu-id="ecda0-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="ecda0-141">Activé</span><span class="sxs-lookup"><span data-stu-id="ecda0-141">On</span></span> <br/> |
   |<span data-ttu-id="ecda0-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="ecda0-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="ecda0-143">Activé</span><span class="sxs-lookup"><span data-stu-id="ecda0-143">On</span></span> <br/> |
   |<span data-ttu-id="ecda0-144">Mode XMLAPI</span><span class="sxs-lookup"><span data-stu-id="ecda0-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="ecda0-145">Activé</span><span class="sxs-lookup"><span data-stu-id="ecda0-145">On</span></span> <br/> |
   
7. <span data-ttu-id="ecda0-146">Naviguez jusqu'à Configuration -\>Configuration du système -\>SIP.</span><span class="sxs-lookup"><span data-stu-id="ecda0-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="ecda0-147">Vérifiez les paramètres suivants (et corrigez-les si nécessaire) :</span><span class="sxs-lookup"><span data-stu-id="ecda0-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="ecda0-148">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="ecda0-148">**Parameter**</span></span>|<span data-ttu-id="ecda0-149">**Paramètre recommandé**</span><span class="sxs-lookup"><span data-stu-id="ecda0-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="ecda0-150">Profile 1 - DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="ecda0-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="ecda0-151">TCP</span><span class="sxs-lookup"><span data-stu-id="ecda0-151">TCP</span></span> <br/> |
   |<span data-ttu-id="ecda0-152">Profile 1 - Outbound</span><span class="sxs-lookup"><span data-stu-id="ecda0-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="ecda0-153">Désactivé</span><span class="sxs-lookup"><span data-stu-id="ecda0-153">Off</span></span> <br/> |
   |<span data-ttu-id="ecda0-154">Profil de 1 - TlsVerify</span><span class="sxs-lookup"><span data-stu-id="ecda0-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="ecda0-155">Activé</span><span class="sxs-lookup"><span data-stu-id="ecda0-155">On</span></span> <br/> |
   |<span data-ttu-id="ecda0-156">Profile 1 - Type</span><span class="sxs-lookup"><span data-stu-id="ecda0-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="ecda0-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="ecda0-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="ecda0-158">Profile 1 - URI</span><span class="sxs-lookup"><span data-stu-id="ecda0-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="ecda0-159">Automatiquement attribué à l’enregistrement du CUCM</span><span class="sxs-lookup"><span data-stu-id="ecda0-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="ecda0-160">Proxy 1 - Adresse</span><span class="sxs-lookup"><span data-stu-id="ecda0-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="ecda0-161">Le nom de l’hôte du CUCM</span><span class="sxs-lookup"><span data-stu-id="ecda0-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="ecda0-p104">Le périphérique de vidéoconférence est désormais configuré pour l’interopérabilité. Avant d’utiliser le service, il vous reste certaines étapes à effectuer au niveau du CUCM.</span><span class="sxs-lookup"><span data-stu-id="ecda0-p104">The VTC is now configured for interoperation. Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="ecda0-164">Configurer les périphériques de vidéoconférence sur le CUCM</span><span class="sxs-lookup"><span data-stu-id="ecda0-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="ecda0-165">Connectez-vous à CUCM et accédez à Cisco Unified CM Administration -\>périphérique -\>téléphone -\>rechercher.</span><span class="sxs-lookup"><span data-stu-id="ecda0-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="ecda0-p105">Sélectionnez le périphérique de vidéoconférence (VTC) à configurer. Vérifiez les paramètres suivants sur l’écran Configuration du téléphone et corrigez-les si nécessaire. Une fois ces paramètres modifiés ou vérifiés, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ecda0-p105">Select the VTC device to be configured. Verify the following settings on the Phone Configuration screen, correcting as needed. Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="ecda0-169">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="ecda0-169">**Parameter**</span></span>|<span data-ttu-id="ecda0-170">**Paramètre recommandé**</span><span class="sxs-lookup"><span data-stu-id="ecda0-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="ecda0-171">Informations sur l’appareil - exemple de bouton de téléphone</span><span class="sxs-lookup"><span data-stu-id="ecda0-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="ecda0-172">C40 de Codec de TÉLÉPRÉSENCE Cisco standard</span><span class="sxs-lookup"><span data-stu-id="ecda0-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="ecda0-173">Informations sur l’appareil - profil commun de téléphone</span><span class="sxs-lookup"><span data-stu-id="ecda0-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="ecda0-174">Profil commun de téléphone standard</span><span class="sxs-lookup"><span data-stu-id="ecda0-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="ecda0-175">Informations sur l’appareil - espace de recherche</span><span class="sxs-lookup"><span data-stu-id="ecda0-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="ecda0-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="ecda0-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="ecda0-177">Informations sur l’appareil - espace de recherche AAR</span><span class="sxs-lookup"><span data-stu-id="ecda0-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="ecda0-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="ecda0-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="ecda0-179">Informations sur l’appareil - liste des groupes de ressources médias</span><span class="sxs-lookup"><span data-stu-id="ecda0-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="ecda0-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="ecda0-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="ecda0-181">Informations spécifiques de protocole - profil de sécurité de l’appareil</span><span class="sxs-lookup"><span data-stu-id="ecda0-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="ecda0-182">C40 de Codec de TÉLÉPRÉSENCE Cisco</span><span class="sxs-lookup"><span data-stu-id="ecda0-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="ecda0-183">Informations spécifiques de protocole - espace de recherche du réacheminement</span><span class="sxs-lookup"><span data-stu-id="ecda0-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="ecda0-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="ecda0-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="ecda0-185">Des informations spécifiques de protocole - s’abonner espace de recherche d’appel</span><span class="sxs-lookup"><span data-stu-id="ecda0-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="ecda0-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="ecda0-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="ecda0-187">Informations spécifiques sur le protocole - profil SIP</span><span class="sxs-lookup"><span data-stu-id="ecda0-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="ecda0-188">Profil SIP standard pour point de terminaison Telepresence</span><span class="sxs-lookup"><span data-stu-id="ecda0-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="ecda0-189">Une fois la configuration de vidéoconférence enregistrée, accédez à l’écran de configuration de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="ecda0-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="ecda0-190">Dans la partie supérieure de l’écran, dans le groupe Association, cliquez sur l’association pour l’interopérabilité vidéo.</span><span class="sxs-lookup"><span data-stu-id="ecda0-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="ecda0-191">Vous accédez à l’écran Configuration des numéros du répertoire.</span><span class="sxs-lookup"><span data-stu-id="ecda0-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="ecda0-192">Vérifiez les paramètres suivants (et corrigez-les si nécessaire) :</span><span class="sxs-lookup"><span data-stu-id="ecda0-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="ecda0-193">Effectuez les changements dans les informations de numéros du répertoire et dans les paramètres de numéros du répertoire.</span><span class="sxs-lookup"><span data-stu-id="ecda0-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="ecda0-194">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="ecda0-194">**Parameter**</span></span>|<span data-ttu-id="ecda0-195">**Paramètre recommandé**</span><span class="sxs-lookup"><span data-stu-id="ecda0-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="ecda0-196">Informations des numéros du répertoire - cloisonnement de l’itinéraire</span><span class="sxs-lookup"><span data-stu-id="ecda0-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="ecda0-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="ecda0-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="ecda0-198">Paramètres des numéros du répertoire - espace de recherche</span><span class="sxs-lookup"><span data-stu-id="ecda0-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="ecda0-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="ecda0-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="ecda0-200">Paramètres de niveau d’accès confidentiel et d’autres parties MLPP - espace de recherche MLPP</span><span class="sxs-lookup"><span data-stu-id="ecda0-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="ecda0-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="ecda0-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="ecda0-202">Ligne 1 sur périphérique - affichage (ID de l’appelant)</span><span class="sxs-lookup"><span data-stu-id="ecda0-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="ecda0-203">Comme souhaité</span><span class="sxs-lookup"><span data-stu-id="ecda0-203">As desired</span></span> <br/> |
   |<span data-ttu-id="ecda0-204">Ligne 1 sur périphérique - ASCII affichage (ID de l’appelant)</span><span class="sxs-lookup"><span data-stu-id="ecda0-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="ecda0-205">Comme souhaité</span><span class="sxs-lookup"><span data-stu-id="ecda0-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="ecda0-206">Lorsque vous avez terminé, remontez en haut de l’écran et sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ecda0-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="ecda0-p107">La configuration est désormais terminée pour ce périphérique de vidéoconférence. Reproduisez ces étapes pour les autres périphériques de vidéoconférence dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="ecda0-p107">Configuration is now complete for this VTC device. You will need to repeat this process for other VTC devices in your enterprise.</span></span>

