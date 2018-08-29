---
title: Expanseur des paramètres de noms de domaine complets du serveur Edge
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: Pour modifier ou spécifier les paramètres externes des serveurs Edge, vous devez d’abord déterminer si vous allez utiliser des adresses IP distinctes pour l’accès SIP (Session Initiation Protocol), le service Edge de conférence web et le service Edge audio/vidéo.
ms.openlocfilehash: 8f211bef1176d5836ec3cc89ad7c48eda707e702
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23263442"
---
# <a name="edge-server-fqdns-settings-expander"></a><span data-ttu-id="9f2df-103">Expanseur des paramètres de noms de domaine complets du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9f2df-103">Edge Server FQDNs Settings Expander</span></span>

<span data-ttu-id="9f2df-104">Pour modifier ou spécifier les **paramètres externes** des serveurs Edge, vous devez d’abord déterminer si vous allez utiliser des adresses IP distinctes pour l’accès SIP (Session Initiation Protocol), le service Edge de conférence web et le service Edge audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="9f2df-104">To edit or specify **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for Session Initiation Protocol (SIP) access, the Web Conferencing Edge service, and the Audio/Video Edge service.</span></span>

<span data-ttu-id="9f2df-p101">Si vous envisagez d’utiliser des adresses IP distinctes chaque fois, activez la case à cocher **Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et les fonctionnalités audio/vidéo**. Chaque service doit disposer d’un enregistrement d’hôte DNS (A) correspondant créé à cette fin.</span><span class="sxs-lookup"><span data-stu-id="9f2df-p101">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding Domain Name System (DNS) host (A) record created for it.</span></span>

<span data-ttu-id="9f2df-p102">Pour chacun des services côté externe, spécifiez un nom de domaine complet (FQDN) et un port associé. Par exemple, pour **Accès SIP**, vous pouvez utiliser sip.contoso.com avec le port 5061 associé.</span><span class="sxs-lookup"><span data-stu-id="9f2df-p102">For each of the external-facing services, specify a fully qualified domain name (FQDN) and an associated port. For example, for **SIP Access**, you might use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f2df-p103">Si vous sélectionnez des noms de domaine complets distincts pour chaque service côté externe, une valeur de port unique doit être associée à chacun de ces services. Par défaut, le SIP est associé au port 5061/TLS, le service Edge de conférence web, au port 444/TLS et le service Edge de conférence A/V, au port 443/TLS. Si vous apportez des modifications à l’un de ces paramètres, y compris en utilisant un nom de domaine complet et d’adresses IP ou des ports distincts, vous devez mettre à jour tous les autres services qui dépendent des valeurs configurées initialement.</span><span class="sxs-lookup"><span data-stu-id="9f2df-p103">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, SIP is on port 5061/TLS, the Web Conferencing Edge service is on port 444/TLS, and the A/V Conferencing Edge service is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="9f2df-p104">Si vous déterminez que votre organisation utilisera un nom de domaine complet et une adresse IP uniques pour les services côté externe, désactivez la case à cocher **Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et les fonctionnalités audio/vidéo**. Vous pouvez ensuite modifier les valeurs du nom de domaine complet du pool et du port **Accès SIP**, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="9f2df-p104">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f2df-114">Si vous apportez des modifications à l’un de ces paramètres, y compris en utilisant un nom de domaine complet et des adresses IP ou des ports distincts, vous devez mettre à jour tous les autres services qui dépendent des valeurs configurées initialement.</span><span class="sxs-lookup"><span data-stu-id="9f2df-114">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="9f2df-115">Pour plus d’informations sur la définition et la configuration des paramètres des services Edge, voir [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span><span class="sxs-lookup"><span data-stu-id="9f2df-115">For details about defining and configuring the settings for the Edge services, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>


