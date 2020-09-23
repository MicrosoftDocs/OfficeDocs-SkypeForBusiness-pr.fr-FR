---
title: Développeur des paramètres FQDN du serveur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Pour définir les propriétés sous paramètres externes, configurez les éléments suivants :'
ms.openlocfilehash: 2de4b562d5b6a8b8ef9707d603fe5f4667893ba4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218245"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="7c3e7-103">Développeur des paramètres FQDN du serveur Edge pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7c3e7-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="7c3e7-104">Pour définir les propriétés sous **paramètres externes**, configurez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7c3e7-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="7c3e7-105">Activez la case à cocher **activer un nom de domaine complet et une adresse IP distincts pour la conférence Web et A/V** si vous voulez définir un nom de domaine complet et une adresse IP distincts pour la conférence Web et l’audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="7c3e7-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7c3e7-106">Si vous choisissez de ne pas activer la case à cocher pour un nom de domaine complet et une adresse IP distincts, vous devez fournir des ports distincts pour chacun des trois services fournis par le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="7c3e7-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="7c3e7-107">Le seul nom de domaine complet à configurer est le nom de domaine complet associé au service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="7c3e7-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="7c3e7-108">Activez la case à cocher le **service Edge a/v est activé pour NAT** si vous voulez que le service Edge a/v utilise une configuration et une adresse IP de traduction d’adresses réseau (NAT).</span><span class="sxs-lookup"><span data-stu-id="7c3e7-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="7c3e7-109">Pour les services Edge activés, tapez un **nom de domaine complet du pool** et un port sous **ports** .</span><span class="sxs-lookup"><span data-stu-id="7c3e7-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="7c3e7-110">Définissez le nom de domaine complet du pool de **service Edge d’accès** et un port qui identifie le service de manière unique.</span><span class="sxs-lookup"><span data-stu-id="7c3e7-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="7c3e7-111">Définissez le nom de domaine complet du pool de **service Edge de conférence Web** (si l’option Activer un nom de domaine complet et une adresse IP distincts pour la conférence Web et a/V n’est pas sélectionnée) et un port qui identifie de manière unique le service.</span><span class="sxs-lookup"><span data-stu-id="7c3e7-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="7c3e7-112">Définissez le nom de domaine complet du pool **de service Edge A/v** (si l’option Activer un nom de domaine complet et une adresse IP distincts pour la conférence Web et a/V n’est pas sélectionnée) et un port qui identifie de manière unique le service.</span><span class="sxs-lookup"><span data-stu-id="7c3e7-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="7c3e7-113">**OK** permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="7c3e7-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="7c3e7-114">**Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="7c3e7-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="7c3e7-115">**Aide** permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="7c3e7-115">**Help** Displays this help screen.</span></span>
  

