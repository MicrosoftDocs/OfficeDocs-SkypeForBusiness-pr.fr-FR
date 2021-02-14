---
title: Développeur des paramètres FQDN du serveur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Pour définir les propriétés sous Paramètres externes, configurez les paramètres suivants :'
ms.openlocfilehash: 6075fab9dbc820b725beec8be4a674a828b4c7d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807094"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="6d270-103">Développeur des paramètres FQDN du serveur Edge pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6d270-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="6d270-104">Pour définir les propriétés sous **Paramètres externes,** configurez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6d270-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="6d270-105">Activez la case à cocher Activer un **FQDN** et une adresse IP distincts pour la conférence web et activez la case à cocher A/V si vous souhaitez définir des adresses IP et un FQDN de pool distincts pour la conférence web et l’audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="6d270-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6d270-106">Si vous choisissez de ne pas cocher la case pour des adresses IP et des noms de noms distincts, vous devez fournir des ports distincts pour chacun des trois services fournis par le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6d270-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="6d270-107">Le seul nom de domaine complet à configurer est le nom de domaine complet associé au service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="6d270-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="6d270-108">Activez la case à cocher nat pour le **service Edge A/V** si vous souhaitez que le service Edge A/V utilise une adresse IP de traduction d’adresses réseau (NAT) et une configuration.</span><span class="sxs-lookup"><span data-stu-id="6d270-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="6d270-109">Pour les services Edge activés, tapez un **FQDN** de pool et un port sous **Ports**</span><span class="sxs-lookup"><span data-stu-id="6d270-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="6d270-110">Définissez le FQDN du pool de **services Edge** d’accès et un port qui identifie le service de manière unique.</span><span class="sxs-lookup"><span data-stu-id="6d270-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="6d270-111">Définissez le FQDN du pool de **services Edge** de conférence Web (si activer un FQDN et une adresse IP distincts pour la conférence web et qu’A/V n’est pas sélectionné) et un port qui identifie le service de manière unique.</span><span class="sxs-lookup"><span data-stu-id="6d270-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="6d270-112">Définissez le FQDN du pool de **services Edge A/V** (si vous activez un FQDN et une adresse IP distincts pour la conférence web et qu’A/V n’est pas sélectionné) et un port qui identifie le service de manière unique.</span><span class="sxs-lookup"><span data-stu-id="6d270-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="6d270-113">**OK** permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="6d270-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="6d270-114">**Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="6d270-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="6d270-115">**Aide** permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="6d270-115">**Help** Displays this help screen.</span></span>
  

