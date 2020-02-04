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
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Pour définir les propriétés sous paramètres externes, configurez ce qui suit :'
ms.openlocfilehash: 2936c910f2cfc1d7e9106e2dca7477f5e1d2860e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684757"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="2e4fe-103">Développeur des paramètres FQDN du serveur Edge pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2e4fe-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="2e4fe-104">Pour définir les propriétés sous **paramètres externes**, configurez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2e4fe-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="2e4fe-105">Activez les cases à cocher **activer les nom de domaine complet et adresse IP pour les conférences Web et A/V** , si vous voulez définir un nom de domaine complet et des adresses IP distincts pour les conférences Web et les appels audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="2e4fe-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2e4fe-106">Si vous choisissez de ne pas activer la case à cocher pour les adresses IP et FQDN distinctes, vous devez fournir des ports distincts pour chacun des trois services fournis par le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="2e4fe-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="2e4fe-107">Le seul nom de domaine complet à configurer est le FQDN associé au service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="2e4fe-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="2e4fe-108">Activez la case à cocher **un service Edge a/v est compatible NAT** si vous souhaitez que le service Edge a/v utilise une configuration et une adresse IP de traduction d’adresses réseau (NAT).</span><span class="sxs-lookup"><span data-stu-id="2e4fe-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="2e4fe-109">Pour les services Edge activés, vous tapez un **nom de domaine complet (FQDN) de pool** et un port sous **ports** .</span><span class="sxs-lookup"><span data-stu-id="2e4fe-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="2e4fe-110">Définissez le nom de domaine complet du pool de **services Edge d’accès** et un port qui identifie de manière unique le service.</span><span class="sxs-lookup"><span data-stu-id="2e4fe-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="2e4fe-111">Définissez le nom de domaine complet (FQDN) du pool de **services de conférence Web** (si vous ne sélectionnez pas d’adresse IP et de FQDN séparés pour les conférences Web et si a/V n’est pas sélectionné) et un port qui identifie de manière unique le service.</span><span class="sxs-lookup"><span data-stu-id="2e4fe-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="2e4fe-112">Définissez le nom de domaine complet (FQDN) du pool **de services A/v** (si vous ne sélectionnez pas d’adresse IP et de FQDN séparés pour les conférences Web et si a/V n’est pas sélectionné) et un port qui identifie de manière unique le service.</span><span class="sxs-lookup"><span data-stu-id="2e4fe-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="2e4fe-113">**OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2e4fe-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="2e4fe-114">**Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2e4fe-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="2e4fe-115">**Aide** : permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="2e4fe-115">**Help** Displays this help screen.</span></span>
  

