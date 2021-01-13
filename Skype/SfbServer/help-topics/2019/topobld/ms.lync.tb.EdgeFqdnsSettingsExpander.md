---
title: Expanseur des paramètres de noms de domaine complets du serveur Edge
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
ROBOTS: NOINDEX, NOFOLLOW
description: Pour modifier ou spécifier des paramètres externes pour les serveurs Edge, vous devez d’abord déterminer si vous allez utiliser des adresses IP distinctes pour l’accès SIP (Session Initiation Protocol), le service Edge de conférence Web et le service Edge audio/vidéo.
ms.openlocfilehash: 11b8ea534a332e756e8effc89fcefcf4a3197832
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822574"
---
# <a name="edge-server-fqdns-settings-expander"></a><span data-ttu-id="0200a-103">Expandeur des paramètres de noms de domaine complets du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="0200a-103">Edge Server FQDNs Settings Expander</span></span>

<span data-ttu-id="0200a-104">Pour modifier ou spécifier des **paramètres externes** pour les serveurs Edge, vous devez d’abord déterminer si vous allez utiliser des adresses IP distinctes pour l’accès SIP (Session Initiation Protocol), le service Edge de conférence Web et le service Edge audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="0200a-104">To edit or specify **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for Session Initiation Protocol (SIP) access, the Web Conferencing Edge service, and the Audio/Video Edge service.</span></span>

<span data-ttu-id="0200a-p101">Si vous envisagez d’utiliser des adresses IP distinctes à chaque fois, activez la case à cocher **Activer un nom de domaine complet et une adresse IP distincts pour la conférence Web et A/V**. Chaque service doit disposer d’un enregistrement d’hôte DNS (A) correspondant créé pour cela.</span><span class="sxs-lookup"><span data-stu-id="0200a-p101">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding Domain Name System (DNS) host (A) record created for it.</span></span>

<span data-ttu-id="0200a-p102">Pour chacun des services côté externe, spécifiez un nom de domaine complet (FQDN) et un port associé. Par exemple, pour **Accès SIP**, vous pouvez utiliser sip.contoso.com avec un port 5061 associé.</span><span class="sxs-lookup"><span data-stu-id="0200a-p102">For each of the external-facing services, specify a fully qualified domain name (FQDN) and an associated port. For example, for **SIP Access**, you might use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0200a-p103">Si vous sélectionnez des noms de domaine complets distincts pour chaque service côté externe, chacun de ces services devra avoir une valeur de port unique associée. Par défaut, SIP se situe sur le port 5061/TLS, le service Edge de conférence web se situe sur le port 444/TLS et le service Edge de conférence A/V se situe sur le port 443/TLS. Si vous apportez des modifications à l’un de ces paramètres, y compris l’utilisation d’un nom de domaine complet et d’adresses IP ou de ports distincts, vous devez mettre à jour tous les autres services qui s’appuient sur les valeurs initialement configurées.</span><span class="sxs-lookup"><span data-stu-id="0200a-p103">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, SIP is on port 5061/TLS, the Web Conferencing Edge service is on port 444/TLS, and the A/V Conferencing Edge service is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="0200a-p104">Si vous déterminez que votre organisation utilisera un nom de domaine complet et une adresse IP uniques pour les services côté externe, désactivez la case à cocher **Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et les fonctionnalités audio/vidéo**. Vous pouvez ensuite modifier les valeurs du nom de domaine complet du port et du pool **Accès SIP**, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="0200a-p104">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0200a-114">Si vous apportez des modifications à l’un de ces paramètres, y compris l’utilisation d’un nom de domaine complet et d’adresses IP ou de ports distincts, vous devez mettre à jour tous les autres services qui s’appuient sur les valeurs initialement configurées.</span><span class="sxs-lookup"><span data-stu-id="0200a-114">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="0200a-115">Pour plus d’informations sur la définition et la configuration des paramètres des services Edge, voir [Définir votre topologie Edge.](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)</span><span class="sxs-lookup"><span data-stu-id="0200a-115">For details about defining and configuring the settings for the Edge services, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>


