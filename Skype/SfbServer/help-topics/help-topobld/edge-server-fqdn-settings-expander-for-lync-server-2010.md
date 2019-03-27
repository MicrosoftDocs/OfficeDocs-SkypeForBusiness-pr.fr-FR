---
title: Développeur des paramètres FQDN du serveur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Pour définir les propriétés sous paramètres externes, configurez les options suivantes :'
ms.openlocfilehash: 3ebd98c17f7b32af72809375bd17e55514684e6d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882347"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="b76ef-103">Développeur des paramètres FQDN du serveur Edge pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b76ef-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="b76ef-104">Pour définir les propriétés sous **paramètres externes**, configurez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="b76ef-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="b76ef-105">Sélectionnez le **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** case à cocher si vous souhaitez définir distincts IP et nom complet du Pool des adresses pour la conférence web et audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="b76ef-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b76ef-106">Si vous choisissez de n’activez ne pas la case à cocher pour les adresses IP et le nom de domaine complet distinctes, vous devez fournir des ports distincts pour chacun des trois services fournis par le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b76ef-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="b76ef-107">Le seul nom de domaine complet qui consiste à configurer est le nom de domaine complet associé au service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="b76ef-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="b76ef-108">Sélectionnez le **A V Edge service / NAT activé** case à cocher si vous souhaitez A / adresse IP de traduction (NAT) et la configuration d’adresses service V Edge à utiliser un réseau.</span><span class="sxs-lookup"><span data-stu-id="b76ef-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="b76ef-109">Pour les services Edge activés, vous tapez un **Nom complet du Pool** et un port sous **Ports**</span><span class="sxs-lookup"><span data-stu-id="b76ef-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="b76ef-110">Définir le nom complet du Pool de **service Edge d’accès** et un port qui identifie le service.</span><span class="sxs-lookup"><span data-stu-id="b76ef-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="b76ef-111">Définir le nom complet du Pool de **service Edge de conférence Web** (si activer de séparer le nom de domaine complet et l’adresse IP pour les conférences web et A / V n’est pas sélectionnée) et un port qui identifie le service.</span><span class="sxs-lookup"><span data-stu-id="b76ef-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="b76ef-112">Définir le **A / V Edge service** nom complet du Pool (si activer de séparer le nom de domaine complet et l’adresse IP pour les conférences web et A / V n’est pas sélectionnée) et un port qui identifie de manière unique le service.</span><span class="sxs-lookup"><span data-stu-id="b76ef-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="b76ef-113">**OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b76ef-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="b76ef-114">**Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b76ef-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="b76ef-115">**Aide** : permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="b76ef-115">**Help** Displays this help screen.</span></span>
  

