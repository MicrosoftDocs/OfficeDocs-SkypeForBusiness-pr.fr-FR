---
title: Serveurs proxy pour Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Cet article vous orientera dans l'utilisation d'un serveur proxy avec Skype ºEntreprise.
ms.openlocfilehash: a4369208ab277e0eb5490a637421de605235a0cd
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="3eb6d-103">Serveurs proxy pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="3eb6d-103">Proxy Servers for Skype for Business Online</span></span>

<span data-ttu-id="3eb6d-104">Cet article vous orientera dans l'utilisation d'un serveur proxy avec Skype ºEntreprise.</span><span class="sxs-lookup"><span data-stu-id="3eb6d-104">This article will help you with guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="3eb6d-105">Il est déconseillé d'utiliser un serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="3eb6d-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="3eb6d-p101">En ce qui concerne le trafic Skype Entreprise, Microsoft recommande d'éviter d'utiliser un serveur proxy. En effet, cela ne permettra pas de sécuriser davantage Skype Entreprise, car son trafic est déjà chiffré.</span><span class="sxs-lookup"><span data-stu-id="3eb6d-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because its traffic is already encrypted.</span></span>
  
<span data-ttu-id="3eb6d-p102">De plus, un serveur proxy peut entraîner des complications. Des problèmes de performances peuvent s'introduire dans l'environnement par le biais de la latence et la perte de paquets. De tels difficultés altèreront l'expérience tant dans les scénarios Skype Entreprise audio que vidéo, pour lesquels les transmissions en continu en temps réel sont essentielles..</span><span class="sxs-lookup"><span data-stu-id="3eb6d-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="3eb6d-111">SI vous devez utiliser un serveur proxy</span><span class="sxs-lookup"><span data-stu-id="3eb6d-111">If you need to use a proxy server</span></span>

<span data-ttu-id="3eb6d-p103">Certaines organisations n'ont pas d'autres choix que d'utiliser un serveur proxy pour le trafic Skype Entreprise. Si cela est votre cas, rappelez-vous des problèmes mentionnés plus haut.</span><span class="sxs-lookup"><span data-stu-id="3eb6d-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="3eb6d-114">Microsoft recommande également :</span><span class="sxs-lookup"><span data-stu-id="3eb6d-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="3eb6d-115">L'utilisation de la résolution DNS externe</span><span class="sxs-lookup"><span data-stu-id="3eb6d-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="3eb6d-116">L'utilisation du routage UDP direct</span><span class="sxs-lookup"><span data-stu-id="3eb6d-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="3eb6d-117">L'autorisation du trafic UDP</span><span class="sxs-lookup"><span data-stu-id="3eb6d-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="3eb6d-118">L'application des autres recommandations de nos directives relatives à la mise en réseau :</span><span class="sxs-lookup"><span data-stu-id="3eb6d-118">Following the other recommendations in our Networking guidelines:</span></span>
    
  - [<span data-ttu-id="3eb6d-119">Qualité multimédia et performances de connectivité réseau dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="3eb6d-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="3eb6d-120">Optimisation de votre réseau pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="3eb6d-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="3eb6d-121">Ces conseils devraient limiter l'apparition de problèmes.</span><span class="sxs-lookup"><span data-stu-id="3eb6d-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="proxy-vendors-with-built-in-skype-for-business-support-or-configuration-options"></a><span data-ttu-id="3eb6d-122">Fournisseurs de serveurs proxy avec options de configuration ou prise en charge de Skype Entreprise intégrées</span><span class="sxs-lookup"><span data-stu-id="3eb6d-122">Proxy vendors with built-in Skype for Business support or configuration options</span></span>

<span data-ttu-id="3eb6d-123">Cette section contiendra des informations sur les fournisseurs de serveurs proxy qui vendent des produits ou services dont l'utilisation avec le trafic Skype Entreprise s'est avérée efficace.</span><span class="sxs-lookup"><span data-stu-id="3eb6d-123">This section will contain information about proxy vendors who provide products or services that are proven to work successfully with Skype for Business traffic.</span></span>
  
<span data-ttu-id="3eb6d-124">Dans le cas d'organisations utilisant **Bluecoat Proxy Solutions**, un nouveau microprogramme a été publié et permet de résoudre divers problèmes liés aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="3eb6d-124">For organizations using **Bluecoat Proxy solutions**, a new firmware has been released which addresses several issues with:</span></span>
    
  - <span data-ttu-id="3eb6d-125">Interception SSL</span><span class="sxs-lookup"><span data-stu-id="3eb6d-125">SSL interception</span></span>
    
  - <span data-ttu-id="3eb6d-126">Vérifications OCSP/SRL</span><span class="sxs-lookup"><span data-stu-id="3eb6d-126">OCSP/SRL checks</span></span>
    
  - <span data-ttu-id="3eb6d-127">SIP sur TLS</span><span class="sxs-lookup"><span data-stu-id="3eb6d-127">SIP over TLS</span></span>
    
  - <span data-ttu-id="3eb6d-128">Prise en charge de TURN</span><span class="sxs-lookup"><span data-stu-id="3eb6d-128">support for TURN</span></span>
    
<span data-ttu-id="3eb6d-p104">La prise en charge native de Bluecoat pour Skype Entreprise peut être facilement activée et permet l'identification du trafic pertinent et une gestion adéquate.L'optimisation de l'authentification, des signaux et du flux du trafic multimédia est ainsi assurée et vous bénéficiez d'une excellente expérience utilisateur sans être préoccupé par d'éventuels problèmes liés à la sécurité.</span><span class="sxs-lookup"><span data-stu-id="3eb6d-p104">Bluecoat's native support for Skype for Business can easily be enabled, allowing for the identification of relevant traffic, and managing it appropriately. This ensures optimal authentication, signaling, and media traffic flow, to provide a great user experience without security concerns.</span></span>
    
<span data-ttu-id="3eb6d-131">Reportez-vous au lien suivant si Bluecoat Proxy fait partie de la topologie de votre réseau :https://support.symantec.com/en_US/article.DOC9757.html</span><span class="sxs-lookup"><span data-stu-id="3eb6d-131">Please refer to the following link if Bluecoat Proxy is a part of your network topology: https://support.symantec.com/en_US/article.DOC9757.html</span></span>

## <a name="related-topics"></a><span data-ttu-id="3eb6d-132">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="3eb6d-132">Related topics</span></span>

[<span data-ttu-id="3eb6d-133">Optimisation de votre réseau pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="3eb6d-133">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 